# GitOps configuration generation approach

The gitops approach used in this repository uses ansible to generate configuration files that are then committed to separate configuration repositories.  This approach allows for consistent configuration between multiple environment lifecycles, as well as separating the gitops configuration sources for each environment.

### Pro's

- Ensures consistency in configuration between lifecycle environments via templating configuration files
- Can use 1 or more tools to generate configuration as long as the output can be captured as json or yaml manifests.
- Allows operational flexibility for troubleshooting different environments

### Cons's

- More difficult for unique configuration tree's in separate environments.
- Hotfixes applied directly to configuration repositories must be rolled into codified generation scripts immediately to ensure changes don't get lost.

## Test

Run the following to validate the inventory control of the lifecycle/environment:

``` bash
ansible-playbook validate.yml [-i <inventory file>]

eg:
ansible-playbook validate.yml -i inventory/dev
```
