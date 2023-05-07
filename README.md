# Deploying an Azure Resource Group using Terraform

## Introduction

Using this repository you will be able to deploy an [AWS S3 Bucket](https://https://docs.aws.amazon.com/s3/index.html) using [Terraform](https://developer.hashicorp.com/terraform/docs). You will use a module, variables, and outputs to accomplish this deployment.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

## Prerequisites

Before you get started with deploying the solution, you must install the
following prerequisites:

1. [Azure Command Line Interface (Azure CLI)](https://learn.microsoft.com/en-us/cli/azure/) 
    -- for instructions, see [How to Install the Azure 
    CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)

1.  [Terraform](https://developer.hashicorp.com/terraform/docs)
    -- for instructions, see [Install Terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)

## Deploying the solution

The below steps deploy the reference implementation in Azure.

To deploy run the following commands from a
terminal session:

1.  Download code from GitHub repo 
    (<https://github.com/JoeTringali/terraform-aws-s3-bucket>).

2.  Edit the terraform.tfvars file to include the name of the S3 bucket to be created:

```
name     = "my-s3-bucket"
```

3. Initialize the working directory:

```
  terraform init
```

4.  Make sure `providers.tf` is formatted correctly:

```
  terraform fmt
```

5. See what it's expecting for the S3 bucket:

```
  terraform plan
```
> You should then see what the outputs will produce.

6.  Deploy your resource group:

```
  terraform apply
```

7. Enter `yes` at the prompt. It will then take a few minutes to finish running.

8. Monitor the progress and wait for the completion of the ```terraform apply``` command before
proceeding.

9. Confirm that the resource group deployed:

```
  terraform state list
```

10. Check the returned list of resources to ensure the S3 bucket was successfully deployed.

11. In the [AWS Console browser window](https://aws.amazon.com/console/), navigate to **S3** and confirm that your S3 bucket is listed.

## Cleanup

To avoid ongoing charges for resources you created, run the following command from a
terminal session:

```
  terraform apply -destroy 
```

or 

```
  terraform destroy
```
