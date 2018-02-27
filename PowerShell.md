---
layout: page
title: PowerShell
---

A small collection of simple PowerShell commands and scripts that I use periodically and have found useful.


## Get Active Directory Account Disabled
~~~
Search-ADAccount -UsersOnly -AccountDisabled | 
Get-ADUser -Properties Name, DistinguishedName, LastLogonDate | 
Select Name, DistinguishedName, LastLogonDate | 
Export-CSV C:\Users\User\Desktop\AccountDisabled.csv -NoTypeInformation
~~~

## Get Active Directory Account Expired
~~~
Search-ADAccount -UsersOnly -AccountExpired | 
Get-ADUser -Properties Name, DistinguishedName, LastLogonDate | 
Select Name, DistinguishedName, LastLogonDate | 
Export-CSV C:\Users\User\Desktop\AccountExpired.csv -NoTypeInformation
~~~

## Get Active Directory Account Never Expires
~~~
Search-ADAccount -UsersOnly -PasswordNeverExpires | 
Get-ADUser -Properties Name, LastLogonDate | 
Select Name, LastLogonDate | 
Export-Csv C:\Users\User\Desktop\AccountNeverExpires.csv -NoTypeInformation
~~~

## Get Active Directory Accounts with Password Expired
~~~
Get-ADUser -Filter 'PasswordExpired -eq $true'
~~~

## Get Active Directory Inactive Users 90 Days
~~~
Search-ADAccount -AccountInactive -TimeSpan 90.00:00:00 -UsersOnly | 
Select -Property Name,LastLogonDate | 
Export-CSV C:\Users\User\Desktop\InactiveAccounts.csv
~~~

~~~
Search-ADAccount -UsersOnly -AccountInactive -TimeSpan 90 | 
?{$_.enabled -eq $True} | 
Get-ADUser -Properties Name | 
Select Name | 
Out-File C:\Users\User\Desktop\90DayInactiveAccts.txt
~~~

~~~
Search-ADAccount -UsersOnly -AccountInactive -TimeSpan 90 | 
?{$_.enabled -eq $True} | 
Get-ADUser -Properties Name | 
Select Name | 
measure | 
Out-File -append C:\Users\User\Desktop\90DayInactiveAccts.txt
~~~

## Get Active Directory Locked Out Users
~~~
Search-ADAccount -LockedOut
~~~

## Get Active Directory OU List

~~~
Get-ADObject -Filter { ObjectClass -eq 'organizationalunit' } | 
Out-File C:\Users\User\Desktop\OrganizationalUnits.txt
~~~

~~~
Get-ADObject -Filter { ObjectClass -eq 'organizationalunit' } | 
measure | 
Out-File -append C:\Users\User\Desktop\OrganizationalUnits.txt
~~~

## Get SHA256 Hash of file
~~~
Get-FileHash C:\Users\test\Desktop\test.txt
~~~

