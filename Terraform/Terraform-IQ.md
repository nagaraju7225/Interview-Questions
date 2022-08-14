Terraform Interview Questions:-
-----------------------------
#### Explain core Terraform end-to-end workflow to deploy and delete resources in Azure or aws cloud?

Ans: Workflow:-
1. **Write:-** Author insfrastructure as code
2. **INIT:-** Intialize working directory containing Terraform configuration files 
3. **Validate:-** Validate Terraform configuration files for syntactical and internal consistent
4. **Plan:-** Preview changes before applying
5. **Apply:-** Provision reproducible infrastructure
6. **Destroy:-** Delete Terraform managed infrastructure

`Terraform fmt` command is used to rewrite Terraform configuration to a canonical formal

#### We have existing Terraform infrastructure created in Azure/AWS cloud , now one particular resource needs to be re-created ,whenever we do the next **Apply**?

**Terraform Taint:-**

+ Terraform taint command informs Terraform that a particular object has become degaraded or damaged and needed to be replaced in next **Apply**

+ terraform state list
+ terraform taint "resource_name" (check the resource status in .tfstate file)
+ terraform apply
+ Terraform taint command is deprecated use **-replace** option with terraform apply instead terrform apply -replace="resource_name"

#### Explain or walk-through step by step process to secure **.tfstate** file and by making it readily available for other developers within the team?

**Terraform Backends:-**

```terraform 
terrform {
   backend "azurerm" {
      resource_group_name = "StorageAccount-ResourceGroup"
      storage_account_name = "abacd234"
      container_name = "tfstate"
      key = "prod.terraform.tfstate"
   }
}
```
#### Explain the various type of META-Arguments in terraform and their benefits?

+ Meta-Arguments changes the default behaviours of Terraform Configuration
   + depends_on
   + count
   + for_each
   + provider
   + lifecycle

#### who creates the **terraform.tfstate.backup** file and under which scenario it is created?
   + Backup state file is automatically created, when terrraform destroy command is executed 
   + The above is done to restore infrastructure to the same state, prior running terraform destroy command
   


   
   