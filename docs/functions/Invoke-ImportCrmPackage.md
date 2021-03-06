
# Invoke-ImportCrmPackage

## Synopsis
Imports a package to a Microsoft Dynamics CRM instance.

## Description
The `Invoke-ImportCrmPackage` cmdlet imports a package to a CRM instance. Internally it registers the necessary Package Deployer
cmdlets prior to invoking the `Import-CrmPackage` cmdlet. See help for `Import-CrmPackage` for additional information on importing packages.

## Parameters
| Parameter  | Type | Description | Required? | Default Value |
|---|---|---|---|---|
| PackageDeployerFolder | String | Specifies the path to the Package Deployer folder. | false | "$(GetPackageDeployerFolder)" |
| PackageFolder | String | The folder path to the package to import. | false | "$(GetPackageDeployerFolder)\Adoxio.Dynamics.ImportPackage" |
| PackageName | String | The name of the assembly (.dll) containing the package definition. | false | Adoxio.Dynamics.ImportPackage.dll |
| CrmConnectionParameters | Hashtable | A `[hashtable]` of parameters to construct a `[Microsoft.Xrm.Tooling.Connector.CrmServiceClient]` object. See `Get-CrmConnection` for the available parameters. | true | |

## Examples

## Example 1
```powershell
$CrmConnectionParameters = @{
    OrganizationName = 'contoso'
    ServerUrl = 'http://dyn365.contoso.com'
    Credential = [PSCredential]::new("contoso\administrator", ("pass@word1" | ConvertTo-SecureString -AsPlainText -Force))
}

Invoke-ImportCrmPackage -CrmConnectionParameters $CrmConnectionParameters
```

## Example 2
```powershell
$CrmConnectionParameters = @{
    OrganizationName = 'contoso'
    ServerUrl = 'http://dyn365.contoso.com'
    Credential = [PSCredential]::new("contoso\administrator", ("pass@word1" | ConvertTo-SecureString -AsPlainText -Force))
}

Invoke-ImportCrmPackage -PackageDeployerFolder C:\Dynamics365SDK\Tools\PackageDeployer -PackageFolder C:\Dynamics365SDK\Tools\PackageDeployer -PackageName Adoxio.Dynamics.ImportPackage.dll -CrmConnectionParameters $CrmConnectionParameters
```
