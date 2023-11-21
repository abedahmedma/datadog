# Datadog provider
provider "datadog" {
  api_key = "YOUR_API_KEY"
}

# Datadog Monitor
resource "datadog_monitor" "example_monitor" {
  name                  = "Example Monitor"
  type                  = "metric alert"
  query                 = "avg(last_5m):sum:system.cpu.idle{*} by {host} > 90"
  message               = "CPU usage is too high!"
  escalation_message    = "Escalating the issue."
  notify_no_data        = true
  no_data_timeframe     = 60
  thresholds {
    critical = 90
    warning  = 80
  }
}

# Datadog Dashboard
resource "datadog_dashboard" "example_dashboard" {
  title = "Example Dashboard"
  layout {
    type   = "ordered"
    height = 3
    width  = 3
    x      = 1
    y      = 1
  }
  widgets {
    type    = "timeseries"
    title   = "CPU Usage"
    queries = ["avg(last_1h):sum:system.cpu.idle{*} by {host}"]
  }
}

# Datadog Synthetics Test
resource "datadog_synthetics_test" "example_synthetics_test" {
  name       = "Example Synthetics Test"
  type       = "browser"
  frequency  = 300
  locations  = ["aws:us-east-1", "aws:us-west-2"]
  request {
    method  = "GET"
    url     = "https://example.com"
    timeout = 30
  }
}

# Datadog Alert
resource "datadog_alert" "example_alert" {
  name                   = "Example Alert"
  type                   = "metric alert"
  query                  = "avg(last_5m):sum:system.load.5{host:host0} by {host} > 1.5"
  message                = "Load average is too high!"
  escalation_message     = "Escalating the issue."
  notify_no_data         = true
  thresholds {
    critical = 1.5
    warning  = 1.0
  }
}

======================================
======================================
# Datadog Metrics Metadata
resource "datadog_metric_metadata" "example_metric_metadata" {
  name        = "custom.example_metric"
  type        = "gauge"
  description = "Example custom metric for Terraform"
  short_name  = "example_metric"
  unit        = "count"
  per_unit    = "second"
  integration = "custom_integration"
  interval    = 60
  tags        = ["environment:production", "team:dev"]
}



=========================================

# Datadog Integration
resource "datadog_integration" "example_integration" {
  name  = "example_integration"
  kind  = "webhook"
  config {
    url = "https://example.com/webhook"
  }
}

# Datadog AWS Integration
resource "datadog_aws_integration" "example_aws_integration" {
  account_id = "YOUR_AWS_ACCOUNT_ID"
  role_name  = "DatadogIntegrationRole"
}

# Datadog GCP Integration
resource "datadog_gcp_integration" "example_gcp_integration" {
  type               = "service_account"
  project_id         = "YOUR_GCP_PROJECT_ID"
  private_key_id     = "YOUR_GCP_PRIVATE_KEY_ID"
  private_key        = "YOUR_GCP_PRIVATE_KEY"
  client_email       = "YOUR_GCP_CLIENT_EMAIL"
  client_id          = "YOUR_GCP_CLIENT_ID"
  client_x509_cert_url = "YOUR_GCP_CERT_URL"
}

# Datadog Azure Integration
resource "datadog_azure_integration" "example_azure_integration" {
  tenant_id      = "YOUR_AZURE_TENANT_ID"
  client_id      = "YOUR_AZURE_CLIENT_ID"
  client_secret  = "YOUR_AZURE_CLIENT_SECRET"
}

# Datadog Slack Integration
resource "datadog_slack_integration" "example_slack_integration" {
  channel = "#example_channel"
}

# Datadog Jira Integration
resource "datadog_jira_integration" "example_jira_integration" {
  base_url = "https://your-jira-instance.com"
  username = "your_jira_username"
  password = "your_jira_password"
}

# Datadog PagerDuty Integration
resource "datadog_pagerduty_integration" "example_pagerduty_integration" {
  routing_key = "YOUR_PAGERDUTY_ROUTING_KEY"
}

# Datadog ServiceNow Integration
resource "datadog_servicenow_integration" "example_servicenow_integration" {
  instance_url = "https://your-servicenow-instance.com"
  username     = "your_servicenow_username"
  password     = "your_servicenow_password"
}

# Datadog Chatbot Integration
resource "datadog_chatbot_integration" "example_chatbot_integration" {
  name        = "example_chatbot"
  api_key     = "YOUR_CHATBOT_API_KEY"
  room        = "example_room"
}

# Datadog Webhook Integration
resource "datadog_webhook_integration" "example_webhook_integration" {
  name  = "example_webhook"
  url   = "https://example.com/webhook"
  method = "POST"
}

# Datadog OpsGenie Integration
resource "datadog_opsgenie_integration" "example_opsgenie_integration" {
  api_key = "YOUR_OPSGENIE_API_KEY"
}

============================================


# Datadog Logs Index
resource "datadog_logs_index" "example_logs_index" {
  name   = "example_logs_index"
  query  = "source:web"
  retention {
    type  = "time"
    value = 30
  }
}

# Datadog Logs Pipeline
resource "datadog_logs_pipeline" "example_logs_pipeline" {
  name = "example_logs_pipeline"
  processors {
    extract_from_json {
      field_names = ["message"]
    }
  }
}

# Datadog Logs Metric
resource "datadog_logs_metric" "example_logs_metric" {
  name         = "example_logs_metric"
  query        = "count_over_time(sum:my.metric{*}, '1h')"
  group_by     = ["env"]
  aggregation  = "count"
  type         = "count"
}

# Datadog Logs Archive
resource "datadog_logs_archive" "example_logs_archive" {
  name       = "example_logs_archive"
  query      = "source:web"
  destination {
    type        = "s3"
    bucket      = "your-s3-bucket"
    path_prefix = "logs/"
  }
}

# Datadog Logs Integration
resource "datadog_logs_integration" "example_logs_integration" {
  name  = "example_logs_integration"
  type  = "logset"
  query = "source:web"
}

# Datadog Logs Index Order
resource "datadog_logs_index_order" "example_logs_index_order" {
  name      = "example_logs_index_order"
  indexes   = ["example_logs_index"]
  order     = 1
}

# Datadog Logs Parser
resource "datadog_logs_parser" "example_logs_parser" {
  name       = "example_logs_parser"
  pattern    = "ERROR %{DATA:log_message}"
  subparsers {
    grok {
      name   = "log_message"
      source = "log_message"
    }
  }
}



======================================

# Datadog Role
resource "datadog_role" "example_role" {
  name        = "example_role"
  description = "Example role for Terraform"
  permissions = [
    "read:dashboard",
    "write:monitor",
  ]
}

# Datadog User
resource "datadog_user" "example_user" {
  handle = "example_user"
  name   = "Example User"
  email  = "example.user@example.com"
}

# Datadog User Application Key
resource "datadog_user_application_key" "example_user_app_key" {
  name   = "example_user_app_key"
  user_id = datadog_user.example_user.id
}

# Datadog User Invite
resource "datadog_user_invite" "example_user_invite" {
  emails = ["new.user@example.com"]
}

# Datadog User Member
resource "datadog_user_member" "example_user_member" {
  user_id   = datadog_user.example_user.id
  group_ids = [datadog_role.example_role.id]
}

# Datadog User Role
resource "datadog_user_role" "example_user_role" {
  user_id = datadog_user.example_user.id
  role_id = datadog_role.example_role.id
}




======================================


# Datadog Dashboard List
resource "datadog_dashboard_list" "example_dashboard_list" {
  name = "Example Dashboard List"
}

# Datadog Notebook
resource "datadog_notebook" "example_notebook" {
  name     = "Example Notebook"
  content  = <<-EOT
    cells:
      - type: markdown
        content: "## Example Notebook"
      - type: query
        content: "metrics(\"system.cpu.idle{*}\").mean().over(\"*\")"
  EOT
}

# Datadog Screenboard
resource "datadog_screenboard" "example_screenboard" {
  board_title = "Example Screenboard"
  widgets {
    type = "timeseries"
    height = 3
    width = 3
    x = 1
    y = 1
    time {
      live_span = "1h"
    }
    title = "CPU Usage"
    queries = [
      "avg(last_1h):sum:system.cpu.idle{*} by {host}"
    ]
  }
}

======================================

# Datadog Organization
resource "datadog_organization" "example_organization" {
  name        = "Example Organization"
  description = "This is an example organization."
}

# Datadog Security Monitor
resource "datadog_security_monitor" "example_security_monitor" {
  name        = "Example Security Monitor"
  description = "This is an example security monitor."
  query       = "status:open"
  tags        = ["environment:production", "team:security"]
}

# Datadog IP Range
resource "datadog_ip_range" "example_ip_range" {
  name       = "Example IP Range"
  start_ip   = "192.168.0.1"
  end_ip     = "192.168.0.255"
  priority   = 1
  note       = "This is an example IP range."
}


# Datadog Logs Index
resource "datadog_logs_index" "example_logs_index" {
  name   = "example_logs_index"
  query  = "source:web"
  retention {
    type  = "time"
    value = 30
  }
}

# Datadog Logs Pipeline
resource "datadog_logs_pipeline" "example_logs_pipeline" {
  name = "example_logs_pipeline"
  processors {
    extract_from_json {
      field_names = ["message"]
    }
  }
}

# Datadog Logs Metric
resource "datadog_logs_metric" "example_logs_metric" {
  name         = "example_logs_metric"
  query        = "count_over_time(sum:my.metric{*}, '1h')"
  group_by     = ["env"]
  aggregation  = "count"
  type         = "count"
}

# Datadog Logs Archive
resource "datadog_logs_archive" "example_logs_archive" {
  name       = "example_logs_archive"
  query      = "source:web"
  destination {
    type        = "s3"
    bucket      = "your-s3-bucket"
    path_prefix = "logs/"
  }
}




# Datadog Logs Integration
resource "datadog_logs_integration" "example_logs_integration" {
  name  = "example_logs_integration"
  type  = "logset"
  query = "source:web"
}

# Datadog Logs Index Order
resource "datadog_logs_index_order" "example_logs_index_order" {
  name      = "example_logs_index_order"
  indexes   = [datadog_logs_integration.example_logs_integration.id]
  order     = 1
}

# Datadog Logs Parser
resource "datadog_logs_parser" "example_logs_parser" {
  name       = "example_logs_parser"
  pattern    = "ERROR %{DATA:log_message}"
  subparsers {
    grok {
      name   = "log_message"
      source = "log_message"
    }
  }
}

# Datadog Metric Query
resource "datadog_metric_query" "example_metric_query" {
  query      = "avg(last_5m):sum:system.cpu.idle{*} by {host}"
  display_name = "CPU Usage"
}

# Datadog AWS Integration
resource "datadog_aws_integration" "example_aws_integration" {
  account_id = "YOUR_AWS_ACCOUNT_ID"
  role_name  = "DatadogIntegrationRole"
  access_key = "YOUR_AWS_ACCESS_KEY"
  secret_key = "YOUR_AWS_SECRET_KEY"
}

# Datadog GCP Integration
resource "datadog_gcp_integration" "example_gcp_integration" {
  type               = "service_account"
  project_id         = "YOUR_GCP_PROJECT_ID"
  private_key_id     = "YOUR_GCP_PRIVATE_KEY_ID"
  private_key        = "YOUR_GCP_PRIVATE_KEY"
  client_email       = "YOUR_GCP_CLIENT_EMAIL"
  client_id          = "YOUR_GCP_CLIENT_ID"
  client_x509_cert_url = "YOUR_GCP_CERT_URL"
}



# Datadog Azure Integration
resource "datadog_azure_integration" "example_azure_integration" {
  tenant_id      = "YOUR_AZURE_TENANT_ID"
  client_id      = "YOUR_AZURE_CLIENT_ID"
  client_secret  = "YOUR_AZURE_CLIENT_SECRET"
}

# Datadog Slack Integration
resource "datadog_slack_integration" "example_slack_integration" {
  channel = "#example_channel"
  api_key = "YOUR_SLACK_API_KEY"
}

# Datadog Jira Integration
resource "datadog_jira_integration" "example_jira_integration" {
  base_url = "YOUR_JIRA_BASE_URL"
  username = "YOUR_JIRA_USERNAME"
  password = "YOUR_JIRA_PASSWORD"
}

# Datadog PagerDuty Integration
resource "datadog_pagerduty_integration" "example_pagerduty_integration" {
  routing_key = "YOUR_PAGERDUTY_ROUTING_KEY"
}



# Datadog ServiceNow Integration
resource "datadog_servicenow_integration" "example_servicenow_integration" {
  instance_url = "YOUR_SERVICENOW_INSTANCE_URL"
  username     = "YOUR_SERVICENOW_USERNAME"
  password     = "YOUR_SERVICENOW_PASSWORD"
}

# Datadog Chatbot Integration
resource "datadog_chatbot_integration" "example_chatbot_integration" {
  name    = "example_chatbot"
  api_key = "YOUR_CHATBOT_API_KEY"
  room    = "example_room"
}

# Datadog Webhook Integration
resource "datadog_webhook_integration" "example_webhook_integration" {
  name  = "example_webhook"
  url   = "YOUR_WEBHOOK_URL"
  method = "POST"
}

# Datadog OpsGenie Integration
resource "datadog_opsgenie_integration" "example_opsgenie_integration" {
  api_key = "YOUR_OPSGENIE_API_KEY"
}
