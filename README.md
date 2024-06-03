# Azure_Kubectl_tool_installer.ado
Use this template for installing a specific version of kubectl binary on agents in Azure Devops Pipeline.

## Parameters:

The pipeline requires the following parameters to be defined:


| Name  | Displayname | type | Default | Values | Opional/Required | Comments |
| ------------- | ------------- | :-------------: | :-------------: | ------------- | :-------------: | ------------- |
| kubectlVersion | Kubectl Version Spec | string | latest | | Required | Specifies the version of kubectl to install. The acceptable values are latest or any semantic version string, e.g. 1.15.0. |


--------------------------------------------------------------------------------------------------------------------------------------------------

These parameters provide multiple use case options for the template, enable/disable flags for the utilization of different templates as per the requirements.


## Use Cases

You can directly call a particular template as per the requirement. for example: 

  ```yaml
  # azure-pipeline.yml
  resources:
  repositories:
    - repository: Template
      type: github
      name: your_username/Azure_Kubectl_tool_installer.ado
      ref: <respective branch name>
      endpoint: 'githubServiceConnectioNname'

  steps:
  # passing the parameters
  - template: Azure_Kubectl_tool_installer.yml
    parameters:
      kubectlVersion: '${{parameters.kubectlVersion}}' 
  ```
  
Make sure to adjust the repository name, branch name, and parameter values according to your project's requirements.
