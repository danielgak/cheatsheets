## Initializing terraform

```sh
terraform init 

terraform init -upgrade # modules/provider update

terraform get # download and install modules
```

## Changes

```sh
terraform plan 
# -out=<file>  # output to file
# -target <resource> # for a specifc module/resource
# -replace <resource> # to replace a specific resource
# -var '<key>=<value>' # set value for input values
# -refresh-only # inspect resource drif without updating the state file

terraform apply 
# <file> # using a plan file
# -target <resource> # update a specific resource
# -replace <resource> # force the replacement
# -auto-approve # skip interactive approval
```

## Inspecting output values

```sh
terraform output # show all output values
# -json # format
# <name> # specify output value
# -raw <name> # specify output value without quotes
```

## Managing state

```sh
terraform show # current state 
# <file> # plan file
# -json <file> # format

terraform state list # show all resources in the state file
terraform state show <resource> # show details about a resource
terraform state mv <source> <dest> # r
terraform state rm <resource> # remove a resource from the state file
terraform state replace-provider <from> <to> # replace provider for resources in the state

terraform import <resource> <remote_id> # import existing infra to Terraform

terraform state pull # pull current state and output to stdout
```

## Destroying infra

```sh
terraform destroy
# -target <resource> # specify a resource
```

## Formating and validation

```sh
terraform validate # check if config is valid
terraform fmt # apply std style
# -check # non-zero exit isreturned if fmt will change something
```

## Cloud & Remote auth

```sh
terraform login 
terraform login <hostname> 

terraform logout
terraform logout <hostname>
```

## Workspaces

```sh
terraform workspace list 
terraform workspace show # current
terraform workspace select <name> # change
terraform workspace new <name> # create a new one
terraform workspace delete <name> 
```

## Other

```sh
terraform version
terraform -help 
terraform -help <command>

terraform providers # show the providers required for this configuration
terraform force-unlock <lock-id> # release a stuck lock
terraform console # interactive prompt mainly to try expressions
terraform graph | dot -Tpng > graph.png # generate a visual graph of Terraform resources
```

## Referencing 

```sh
<resource_type>.<name> # to a managed resource
var.<name> # to an input variable
local.<name> # Reference to a local value
module.<module_name> # Reference to a child module
data.<data_type>.<name> # Reference to a data source
```

## Expresions

```sh
condition ? true : false # ternary
<resource_type>.<name>[*].<attribute> # list of values for th given attribute of all instances of a resource
```

## Meta-arguments

```sh
# over resources

depends_on # explicitly specify resource dependencies
count  # create multiple instances of a resource
for_each # create an instance of a resource for each element in a map or set
provider # specify a provider configuration block to use for this resource
lifecycle # configure the behavior of a resource over its
create_before_destroy # create the new resource before destroying the old one

# over lifecycle

prevent_destroy # prevent Terraform from destroying the resource
ignore_changes # ignore changes to specific resource attributes
```