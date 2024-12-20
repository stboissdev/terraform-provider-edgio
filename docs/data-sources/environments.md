---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "edgio_environments Data Source - terraform-provider-edgio"
subcategory: ""
description: |-
  
---

# edgio_environments (Data Source)

Use the `edgio_environments` data source to retrieve a list of environments from the Edgio API.

Learn more about the environments in the [Edgio API documentation](https://docs.edg.io/applications/v7/basics/environments).

## Example Usage

```terraform
terraform {
  required_providers {
    edgio = {
      source = "Edgio/edgio"
      version = "0.1.0"
    }
  }
}

variable "client_id" { type = string }
variable "client_secret" {  type = string }
variable "property_id" { type = string }

provider "edgio" {
  client_id     = var.client_id
  client_secret = var.client_secret
}

data "edgio_environments" "my_environments" {
  item_count = 100
  property_id = var.property_id
}

output "environments" {
  value = data.edgio_environments.my_envirovments.environments
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `property_id` (String) The ID of the property to filter environments by.

### Read-Only

- `environments` (Attributes List) (see [below for nested schema](#nestedatt--environments))
- `item_count` (Number) The total number of environments.

<a id="nestedatt--environments"></a>
### Nested Schema for `environments`

Read-Only:

- `created_at` (String) The environment's creation date and time (UTC).
- `default_domain_name` (String) The default domain name for the environment.
- `dns_domain_name` (String) The DNS domain name for the environment.
- `http_request_logging` (Boolean) Indicates if HTTP request logging is enabled for the environment.
- `id` (String) The environment's system-defined ID.
- `legacy_account_number` (String) The legacy account number for the environment.
- `name` (String) The name of the environment.
- `only_maintainers_can_deploy` (Boolean) Indicates if only maintainers can deploy to the environment.
- `pci_compliance` (Boolean) Indicates if the environment is PCI compliant.
- `property_id` (String) The ID of the property associated with the environment.
- `updated_at` (String) The environment's last modification date and time (UTC).