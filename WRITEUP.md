# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*
- *Analyze costs, scalability, availability, and workflow*
- *Choose the appropriate solution (VM or App Service) for deploying the app*
- *Justify your choice*

#### Comparing VMs and App Services:
*Virtual Machines:*
- **Costs**: A VM is generally more expensive than an App Service.
- **Scalability**: Can be scaled if needed via Virtual Machine Scale Sets or Load Balancing
- **Availability**: Can be assured via grouping of multiple VMs
- **Workflow**: Disadvantages regarding the workflow because we have to take care about the OS, special installations and configurations needed

*App Services*
- **Costs**: A Web App can be used in SKU F1, producing no costs, which is good for an MVP (Dev/Test). Will be more expensive if we need to scale for another tier, e.g. prod.
- **Scalability**: Can be scaled both vertically by adding more resources such as RAM or horizontally by increasing the number of VM instances if needed, the latter is Auto-Scaling.
- **Availability**: Horizontal scaling also increases the availability
- **Workflow**: Smooth workflow because we don't have to take care about the infrastructure

#### Choosing an option
I would opt for an App Service here. The purpose is an article CMS. We can assume that only little users will use it in the beginning. Thus, we also don't need much storage, neither for relational nor for unstructured data.
If the number of users increases the advantages regarding auto-scaling are a huge advantage. Additionally we have no requirements for special images or software nor for special security demands as we are not talking about confidential data of a company.

### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 

If the App was written not in Python but in another language like Kotlin or Rust, we couldn't use an App Service anymore. Also, if we would have special needs regarding the OS or security concerns we should opt fo a Virtual Machine, as the configuration of the OS is up to us there.