Cette documentation contient les étapes nécessaires à la préparation de la livraison. Ces étapes peuvent être réalisées en amont de la livraison, mais nécessitent que les prérequis aient été remplis.

Sur le portail Azure, se rendre sur Entra - App registration Opens in new window or tab, et ouvrir l'application créée dans les prérequis. Appliquer les configurations suivantes:
1.1. Copier la valeur Application (client) ID pour une utilisation ultérieure
1.2. Sur la page de l'application, cliquer sur le menu App roles
1.3. Cliquer sur Create app role, avec le nom BYOD, le member type Users/Groups, et la valeur Access.Byod (bien respecter la casse).
image.png
1.4. Cliquer sur Apply
1.5. Sur la page de l'application, cliquer sur le menu Certificates & secrets
1.6. Cliquer sur New client secret dans le tab Client secrets (⚠️ si le secret expire, l'application cessera de fonctionner)
image.png
1.7. Copier la valeur du secret pour une utilisation ultérieure (⚠️ la valeur ne pourra pas être affichée à nouveau)

Créer une nouvelle branche releases/<client> depuis master

Initialiser la configuration du container registry : l'application est compilée dans une image docker, chaque version (pour chaque client) est compilée dans une image différente. La mise à disposition de l'application est faite au travers de Azure Container Registry. Chaque client peut accéder à toutes les versions des images de son repository, la segmentation entre les clients est réalisée à l'aide des Scope Maps (documentation) Opens in new window or tab
Registry tokens and scope maps

⚠ Attention

Azure Container Registry est actuellement hébergé sur un resource group à usage personnel). Une migration est à prévoir lors de l'industrialisation de la solution


3.1. Ouvrir le pipeline pipeline Docker Publish et cliquer sur le bouton Run pipeline
3.2. Rentrer le nom de branche releases/<client>, le nom de version privategpt-<client>, et le numéro de version désiré, en prenant soin de faire terminer la valeur du Patch par -alphaimage.png
3.3. Cliquer sur le bouton Run
3.4. Attendre l'exécution complète du pipeline, puis ouvrir le portail Azure et accéder au container registry (actuellement magellanpartnersregistry, situé sur le groupe de ressources (souscription - EN - Enterprise Solution Center - 00 sur le tenant EN - LAB).
3.5. Cliquer sur le menu Scope Maps, puis sur le bouton Add
image.png
3.6. Renseigner le nom du scope map <client>-pull, le repository du client privategpt-<client>, et sélectionner les permissions content/read et metadata/read. Cliquer ensuite sur Create.
image.png
3.7. Une fois le scope map créé, ouvrir le menu Tokens et cliquer sur Add. Renseigner la valeur <client>-pull-devops pour le token, et sélectionner le scope map <client>-pull. Valider avec Create.
image.png
3.8. Une fois le token créé, cliquer sur le token, puis sur le bouton image.png pour générer un mot de passe. Copier le mot de passe pour une utilisation ultérieure.
[Optionnel] Si la recherche sur le web est souhaitée par le client, déployer Bing Search manuellement (pas encore supporté par bicep)
4.1. Se rendre dans la partie "Bing Resources" de Azure
MicrosoftTeams-image (2).png
4.2. Ajouter une nouvelle ressource Bing Search
MicrosoftTeams-image (3).png
4.3. Remplir les informations avec la souscription et le ressource group préalablement créé
4.4. Sélectionner le Pricing tier S2
Bing-search-create.png
4.5 Cliquer sur Review + create, puis Create.
4.6 Une fois le service crée, allez dans le menu Keys and Endpoints, puis copier la valeur de Key 1 pour une utilisation ultérieure (⚠️ la valeur ne pourra pas être affichée à nouveau)

Appliquer sur la branche les personnalisations demandées par le client

Faire un commit / une PR sur la branche /releases/<client>.

relancer le pipeline Docker Publish comme dans l'étape 3.2, en supprimant cette fois-ci la valeur -alpha de la propriété Patch.

Dans le code source, dupliquer le fichier /infrastructure/parameters/magellan-gpt.parameters.json, et le renommer <client>-gpt.parameters.json. Sur ce fichier, insérer les valeurs suivantes :

applicationVersion: privategpt-<client>:<version>
AzureAdClientId: valeur du client Id récupérée à l'étape 1.1
AzureAdClientSecret: valeur du client secret récupéré à l'étape 1.7
containerRegistryPassword: valeur du mot de passe récupéré à l'étape 3.8
projectShortName: <client>
containerRegistryUser: <client>-pull-devops
AzureAdDomain: nom du tenant du client
BingSearchApiKey: valeur de la clé Bing Search récupérée dans l'étape 4.6. Si Bing Search n'est pas activé, entrer la valeur "-"
