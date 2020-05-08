# AWS Roles and Permissions for Project Cloud

This module creates AWS IAM roles and attaches permissions to those roles. The IAM roles are used by other common modules like the backend and the frontend.

## Example
```hcl
module "roles-and-permissions" {
  source                          = "git::https://github.com/marcoberger/project-cloud-roles-permissions.git"
  
  s3_bucket_frontend_id           = "dev-jedis-project-cloud-frontend-w5an7q"
  origin_access_identity_iam_arn  = "arn:aws:iam::cloudfront:user/CloudFront Origin Access Identity E3HD5R7Z1RT5O"

  region                          = "eu-central-1"
  team                            = "teamName"
  project                         = "projectName"
  environment                     = "development"
}
```

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| s3_bucket_frontend_id | The ID of the S3 bucket that contains the frontend | list | n/a | yes |
| origin_access_identity_iam_arn | The ARN of the CloudFront Origin Access Identity | string | n/a | yes |
| region | The AWS region used by the AWS provider | string | `"eu-central-1"` | no |
| team | The name of the team | string | `"jedis"` | no |
| project | The name of the project | string | `"project-cloud"` | no |
| environment | The name of the environment | string | `"dev"` | no |

## Outputs

| Name | Description |
|------|-------------|
| - | - |
