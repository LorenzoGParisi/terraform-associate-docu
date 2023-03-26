[Back](../commands.md) [Home](../../index.md)
# TERRAFORM INIT

**What does it do?**

Initializes backend, downloads the necessary provider plugins and modules.

It creates:
- .terraform/...

- .terraform.lock.hcl

```
.terraform
├── modules
│   └── modules.json
└── providers
    └── registry.terraform.io
        └── hashicorp
            ├── google
            │   └── 4.58.0
            │       └── linux_amd64
            │           └── terraform-provider-google_v4.58.0_x5
            ├── kubernetes
            │   └── 2.17.0
            │       └── linux_amd64
            │           └── terraform-provider-kubernetes_v2.17.0_x5
            └── null
                └── 3.2.1
                    └── linux_amd64
                        └── terraform-provider-null_v3.2.1_x5

```

**When it must be executed?**

To initialize a directory for the first time and when adding or removing modules, providers, or backend configurations.

```
╷
│ Error: Module not installed
│ 
│   on main.tf line 6:
│    6: module "network" {
│ 
│ This module is not yet installed. Run "terraform init" to install all modules required by this configuration.
```

**Warning:** 
- init doesn't creates state file.
- init doesn't creates anything if there isn't any provider, resource or existing module blocks in the working directory.
- init doesn't creates .terraform.lock.hcl and .terraform/provider/... when there isn't at least a provider or a real provider resource blocks.
- init doesn't creates .terraform/modules/modules.json if there isn't a real module source in the configuration.
- If a provider block isn't declared but his resource is, .terraform/providers/... and terraform.lock.hcl is created anyway.