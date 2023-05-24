# Deploying an AWS S3 Bucket using Terraform

## Introduction

Using this repository you will be able to deploy an [AWS S3 Bucket](https://https://docs.aws.amazon.com/s3/index.html) using [Terraform](https://developer.hashicorp.com/terraform/docs). You will use a module, variables, and outputs to accomplish this deployment.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

## Prerequisites

Before you get started with deploying the solution, you must install the
following prerequisites:

1. [AWS Command Line Interface (AWS CLI)](https://aws.amazon.com/cli/)
    -- for instructions, see [Installing the AWS
    CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html)

1.  [Terraform](https://developer.hashicorp.com/terraform/docs)
    -- for instructions, see [Install Terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)

## Deploying the solution

The below steps deploy the reference implementation in AWS.

To deploy run the following commands from a
terminal session:

1.  Download code from GitHub repo 
    (<https://github.com/JoeTringali/terraform-aws-s3-bucket>).

1.  Edit the terraform.tfvars file to include the name of the S3 bucket to be created:

    ```
      name     = "my-s3-bucket"
    ```

1. Initialize the working directory:

    ```
      terraform init
    ```

1.  Make sure `providers.tf` is formatted correctly:

    ```
      terraform fmt
    ```

1. See what it's expecting for the S3 bucket:

    ```
      terraform plan
    ```
    > You should then see what the outputs will produce.

1.  Deploy your S3 bucket:

    ```
      terraform apply
    ```

1. Enter `yes` at the prompt. It will then take a few minutes to finish running.

1. Monitor the progress and wait for the completion of the ```terraform apply``` command before
proceeding.

1. Confirm that the S3 bucket deployed:

    ```
      terraform state list
    ```

1. Check the returned list of resources to ensure the S3 bucket was successfully deployed.

1. In the [AWS Console browser window](https://aws.amazon.com/console/), navigate to **S3** and confirm that your S3 bucket is listed.

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
