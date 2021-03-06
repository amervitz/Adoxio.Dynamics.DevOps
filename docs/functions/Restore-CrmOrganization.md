
# Restore-CrmOrganization

## Synopsis
Creates a new on-premise CRM organization on a local CRM server by restoring from a backup.

## Description
This function creates a new on-premise CRM organization on a local CRM server by restoring a backup of an existing CRM organization database.

## Parameters
| Parameter  | Type | Description | Required? | Default Value |
|---|---|---|---|---|
| Name | String | The name of the database and organization to create | true | |
 | SqlServerName | String | The name of the SQL server to perform database restore operations on | true | |
 | SqlBackupFile | String | The file path to the SQL backup file of an organization to restore | true | |
 | SqlDataFile | String | The file path to the new SQL database data file to create | true | |
 | SqlLogFile | String | The file path to the new SQL database log file to create | true | |
 | Force | SwitchParameter | Overwrites an existing database and organization if one with the same name already exists | false | False |

## Examples

## Example 1
This example creates a CRM organization named 'contoso' by restoring a database backup file 'new_MSCRM.bak'.
```powershell
Restore-CrmOrganization -Name contoso -SqlServerName dyn365.contoso.com -SqlBackupFile 'C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\MSSQL\Backup\new_MSCRM.bak' -SqlDataFile 'C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\MSSQL\DATA\contoso_MSCRM.mdf' -SqlLogFile 'C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\MSSQL\DATA\contoso_MSCRM_log.ldf'
```

## Example 2
This example replaces an existing CRM organization with the -Force parameter.
```powershell
Restore-CrmOrganization -Name contoso -SqlServerName dyn365.contoso.com -SqlBackupFile 'C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\MSSQL\Backup\new_MSCRM.bak' -SqlDataFile 'C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\MSSQL\DATA\contoso_MSCRM.mdf' -SqlLogFile 'C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\MSSQL\DATA\contoso_MSCRM_log.ldf' -Force
```
