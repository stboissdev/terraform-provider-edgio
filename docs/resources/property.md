---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "edgio_property Resource - terraform-provider-edgio"
subcategory: ""
description: |-
  
---

# edgio_property (Resource)

Use the `edgio_property` resource to:
* Create a new property.
* Update an existing property.
* Delete a property.

Learn more about the property resource in the [Edgio API documentation](https://docs.edg.io/applications/v7/basics/properties).

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
variable "organization_id" { type = string }

provider "edgio" {
  client_id     = var.client_id
  client_secret = var.client_secret
}

resource "edgio_property" "my_property" {
  organization_id = var.organization_id
  slug = "edgio-property-example"
}

output "added_property" {
  value = edgio_property.my_property
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `organization_id` (String)
- `slug` (String)

### Read-Only

- `created_at` (String)
- `id` (String) The ID of this resource.
- `id_link` (String)
- `updated_at` (String)