# BACKEND

Initialized during the execution of terraform init.

```
terraform {
  backend "remote" {
    organization = "example_corp"

    workspaces {
      name = "my-app-prod"
    }
  }
}

```

&nbsp;

**Backend changed**

- -reconfigure  

  Update backend with a new empty state file.

- -migrate-state (optional: -force-copy)

  Update backend and copies existing state in the new backend.

&nbsp;

**Backend access credentials**

Some backends allow providing access credentials directly as part of the configuration

  - Best practice for backend that needs access credentials is to set them through environment variables and not inside the backend block. Because these will be saved in a shared state file.

Partial Backend Configuration happens when you didn't provide all required configuration in .tf file but decide to pass them in different ways:

  - terraform init -backend-config=PATH

  - terraform init -backend-config="KEY=VALUE"

  - interactively (if some bk conf miss, terraform will ask you for the required values)

&nbsp;

**Backend types**

- **STANDARD**
---

Limited functionalities, self-managed and minimal security features.

| Backend Type | Multiple Environments | Multiple Users | State Locking | Remote State |
| ------------ | :------------------: | :------------: | :-----------: | :----------: |
| local        |          `✗`          |       `✗`       |      `✗`       |      `✗`      |
| remote       |         ✓          |      ✓       |      ✓      |      ✓     |



- **ENHANCHED**
---

Addictional functionalities, managed and advanced security features.

| Backend Type | Multiple Environments | Multiple Users | State Locking | Remote State |
| ------------ | :------------------: | :------------: | :-----------: | :----------: |
| azurerm      |         ✓          |      ✓       |      ✓      |      ✓     |
| cos          |          `✗`          |      ✓       |      ✓      |      ✓     |
| consul       |          `✗`          |      ✓       |      ✓      |      ✓     |
| gcs          |          `✗`          |      ✓       |      ✓      |      ✓     |
| http         |          `✗`          |       `✗`       |      `✗`       |      `✗`      |
| kubernetes  |         ✓          |      ✓       |      ✓      |      ✓     |
| oss          |          `✗`          |       `✗`       |      `✗`       |      `✗`      |
| pg           |         ✓          |      ✓       |      ✓      |      ✓     |
| s3           |         ✓          |      ✓       |      ✓      |      ✓     |

&nbsp;

**Warning:** 
  - When applying a plan that you previously saved to a file, Terraform uses the backend configuration stored in that file instead of the current backend settings.