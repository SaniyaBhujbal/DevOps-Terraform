\# DevOps Internship - Task 3



\## Infrastructure as Code (IaC) with Terraform



\### Objective



Provision a local Docker container using Terraform.



\### Tools Used



\* Terraform v1.16.5

\* Docker v29.8.1

\* Docker Provider v3.9.0

\* Nginx Docker Image



\### Terraform Configuration



The `main.tf` file uses the Docker provider to:



1\. Pull the `nginx:latest` Docker image.

2\. Create a Docker container named `terraform-nginx`.

3\. Map host port `8081` to container port `80`.



\### Commands Executed



```bash

terraform init

terraform plan

terraform apply

terraform state list

terraform destroy

```



\### Execution Results



\#### Terraform Init



Terraform was successfully initialized and the Docker provider was installed.



\#### Terraform Plan



The execution plan showed:



```text

Plan: 2 to add, 0 to change, 0 to destroy.

```



\#### Terraform Apply



The Nginx Docker container was successfully created.



```text

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.

```



The container was verified using:



```bash

docker ps

```



The container was running as:



```text

terraform-nginx

0.0.0.0:8081->80/tcp

```



The Nginx welcome page was also successfully accessed through:



```text

http://localhost:8081

```



\#### Terraform State



Terraform state was checked using:



```bash

terraform state list

```



Resources shown were:



```text

docker\_container.nginx

docker\_image.nginx

```



\#### Terraform Destroy



The infrastructure was successfully destroyed using:



```bash

terraform destroy

```



Result:



```text

Destroy complete! Resources: 2 destroyed.

```



The final `docker ps` confirmed that the Terraform-managed container was no longer running.



\### Outcome



Successfully provisioned, verified, inspected, and destroyed a local Docker container using Terraform Infrastructure as Code.



