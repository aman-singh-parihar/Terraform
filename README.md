# Terraform
## Concepts of terraform

### Terraform Block

- Configuring a terraform backend.
```terraform
terraform {
  backend "s3" {
    encrypt        = "true"
    dynamodb_table = "terraform_statelock"
    region         = "us-east-1"
    bucket         = "mybucket"
    key            = "path/to/my/key"
  }
}
```
- Specifying provider requirement.
- Specifying a required terraform version.
```terraform
terraform {
  required_version = ">= 1.0"
  required_providers {
    newrelic = {
      source  = "hashicorp/newrelic"
      version = ">= 2.0"
    }
    google = {
      source  = "hashicorp/google"
      version = "~> 3.0"
    }
    aws = {
      source  = "hashicorp/aws"
      version = "~> 3.0"
    }
  }
}
```

This block was introduced from 0.13 onwards.
![image](https://github.com/aman-singh-parihar/Terraform/assets/25799703/6e89b6c4-6108-46c8-a0cd-c070f14d6b36)



### Provider Block

- Terraform relies on providers to interact with the remote cloud services (aws, azure, gcp).
- Provider configurations belong to the root module.
- Terraform install the providers and use them to create/update resources on the remote cloud services.

### Resource Block

- Each resource block describes one or more infrastructure objects.
