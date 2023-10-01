## Semantic Versioning :mage:

The project will use semantic versioning for it's tagging. [semver.org](https://semver.org/)

The general format is **MAJOR.MINOR.PATCH**, for example, `1.0.1` 

- **MAJOR** version when you make incompatible API changes
- **MINOR** version when you add functionality in a backward compatible manner
- **PATCH** version when you make backward compatible bug fixes

Additional labels for pre-release and build metadata are available as extensions 
to the MAJOR.MINOR.PATCH format.


## Install Terrform CLI

### Consideration for Terraform CLI Changes
The Terraform CLI installation has changed due to GPG keying changes. Refer to the latest install CLI instructions via Terraform documentation. 
[Install Terraform CLI](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli) 

### Considerations for Linux Distribution

This project is built against Ubuntu. Check your Linux distribution and change accordingly to needs. [How to check OS version in Linux](https://www.cyberciti.biz/faq/find-linux-distribution-name-version-number/)


```
$ cat /etc/os-release

PRETTY_NAME="Ubuntu 22.04.3 LTS"
NAME="Ubuntu"
VERSION_ID="22.04"
VERSION="22.04.3 LTS (Jammy Jellyfish)"
VERSION_CODENAME=jammy
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=jammy```

#### Shebang Considerations

A Shebang pronounced (Sha-bang) tells the bash script what program that will interprate the script. Eg of script `#! /usr/bin/env bash`



### Refactoring into Bash Script

When figing the Terraform CLI gpg depreciation issues we created a new Terraform CLI bsh script. The bash script is located here: [./bin/install_terraform_cli](./bin/install_terraform_cli)
- This will. keep Gitpod Task File([./gitpod.yml].gitpod.yml) tidy. 
- Allow us an easier to debug and execute Terraform CLI manualy.
- Allow better portability for other projects that need to install terrafrom cli.


#### Linux  Permission Considerations
[Change Permissions](https://en.wikipedia.org/wiki/Chmod)

To make our bash script executable we need to change linux permission for the fix to be executable at the user level ```chmod u+x ./bin/install_terraform_cli```


#### Github Lifecycle (Before, Init, Command)



https://www.gitpod.io/docs/configure/workspaces/tasks




