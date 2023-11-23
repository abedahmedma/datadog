Steps to do to get most of DataDog 

= Architecture 
= Components to master in DataDog 
= Terraform 
= Code to steps 
= Queries of DataDog 

========================
To learn : 
= 
Github Advanced security
Okta

=======================
= Components to master in DataDog (without explanation, in keywords only)

using the simplified  hierarchical structure, use │   ├── 
=======================
Components of "DataDog" ..
=======================
use simplified hierarchical structure
=======================
use │   ├──  with 6 levels
instead 
=======================
Example of each (using the simplified hierarchical structure)
=======================
using the simplified  hierarchical structure, use │   ├── 

Configure the app registration


Création de l'application
Pour la connexion des utilisateurs ainsi que l'attribution des rôles, GPT 4 Enterprise utilise une application Azure AD.

Se rendre sur Entra - Users Opens in new window or tab
Cliquer sur New user, puis Invite external user
Renseigner les informations des comptes devant administrer l'application
Cliquer sur Invite

Se rendre sur Entra - App registration Opens in new window or tab
Cliquer sur register an application
Nom de l'app registration: SPN_<application>
Sélectionner le mode single tenant
Laisser vide le champ Redirect URI (il sera modifié plus tard)

Dans le menu Owners
Cliquer sur Add owners
Sélectionner les comptes qui doivent pouvoir administrer l'application
Cliquer sur Select

Dans le menu API permissions
Cliquer sur Grant admin consent for <tenant>
Cliquer sur Yes