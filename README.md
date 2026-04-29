# terraform-static-registry

A GitHub Pages implementation of the Terraform provider registry protocol.

## Usage

```terraform
# main.tf

terraform {
  required_providers {
    aws = {
      source = "registry.wallcrayon.com/hashicorp/aws"
    }
  }
}
```

```console
$ terraform init

Initializing provider plugins found in the configuration...
- Finding latest version of registry.wallcrayon.com/hashicorp/aws...
- Installing registry.wallcrayon.com/hashicorp/aws v6.42.0...
- Installed registry.wallcrayon.com/hashicorp/aws v6.42.0 (signed by HashiCorp)

Initializing the backend...


Terraform has created a lock file .terraform.lock.hcl to record the provider
selections it made above. Include this file in your version control repository
so that Terraform can guarantee to make the same selections by default when
you run "terraform init" in the future.

Terraform has been successfully initialized!

$ terraform providers lock -platform=windows_386 -platform=freebsd_arm

- Fetching registry.wallcrayon.com/hashicorp/aws 6.42.0 for windows_386...
- Retrieved registry.wallcrayon.com/hashicorp/aws 6.42.0 for windows_386 (signed by HashiCorp)
- Fetching registry.wallcrayon.com/hashicorp/aws 6.42.0 for freebsd_arm...
- Retrieved registry.wallcrayon.com/hashicorp/aws 6.42.0 for freebsd_arm (signed by HashiCorp)
- Obtained registry.wallcrayon.com/hashicorp/aws checksums for windows_386; Additional checksums for this platform are now tracked in the lock file
- Obtained registry.wallcrayon.com/hashicorp/aws checksums for freebsd_arm; Additional checksums for this platform are now tracked in the lock file

Success! Terraform has updated the lock file.

Review the changes in .terraform.lock.hcl and then commit to your
version control system to retain the new checksums.

$ terraform providers

Providers required by configuration:
.
└── provider[registry.wallcrayon.com/hashicorp/aws]
```
