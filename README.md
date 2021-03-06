# NoSync.ps1 - Script to verify users who do not access AD and Exchange

Powershell script to which identifies users who do not access AD or exchange for a certain time and creates a new attribute to facilitate their identification.

it also checks if any of the users who have the attribute filled in have returned to using the services of exchang / AD and remove the attribute.

all changes are reported through logs.

## Utilities

This script can be used to:

- check the amount of inactive and active users
- verify users who do not need licenses
- disable users who no longer access company services
- etc..

## Usage 

Create paste for logs.
check the dates that will be used as a parameter : 

$lastDate - variable used so that new users or vacationers for example do not enter the list affected by the script.
$days - variable used to determine the number of days the script will use to check if the user will receive or lose the NoSync attribute.

Set-ADObject $temp1 -Add @{"extensionAttribute15" = "NoSync"} - it is possible to change the attribute name and the attribute as needed.

## Parameters 

- **-clear**, checks if users who already have the "NoSync" parameter have accessed AD or exchange.

## Examples

    .\NoSync.ps1 
    
adds the "NoSync" parameter to users who do not access AD and Exchange at a specified time.
    
    .\NoSync.ps1 -clear
    
adds the "NoSync" parameter to users who have not accessed AD and Exchange for more than 6 months and checks whether users who already have the "NoSync" parameter have accessed AD or exchange at a certain time.
    
### Credits

Written by: Caio de Amorim Pereira




    
    
