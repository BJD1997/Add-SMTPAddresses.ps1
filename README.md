# Add-SMTPAddresses.ps1
PowerShell script to perform bulk adding of new SMTP addresses to Office 365 mailboxes.

This PowerShell script will add new SMTP addresses to existing Office 365 mailbox users for a new domain. This script fills the need to make bulk email address changes in Exchange Online when Email Address Policies are not available.

Results are output to a text log file.

# Modifications made by me [(BJD1997)](https://github.com/BJD1997)

- -Check if Exchange Online managemet module is installed, if not install it.
- -Check if there is an active connection with Exchange Online, if not the run Connect-ExchangeOnline

## Parameters

- -Domain, The new domain name to add SMTP addresses to each Office 365 mailbox user.
- -MakePrimary, Specifies that the new email address should be made the primary SMTP address for the mailbox user.
- -Commit, Specifies that the changes should be committed to the mailboxes. Without this switch no changes will be made to mailboxes but the changes that would be made are written to a log file for evaluation.

## EXAMPLES
```
.\Add-SMTPAddresses.ps1 -Domain office365bootcamp.com
```
This will perform a test pass for adding the new alias@office365bootcamp.com as a secondary email address
to all mailboxes. Use the log file to evaluate the outcome before you re-run with the -Commit switch.

```
.\Add-SMTPAddresses.ps1 -Domain office365bootcamp.com -MakePrimary
```
This will perform a test pass for adding the new alias@office365bootcamp.com as a primary email address
to all mailboxes. Use the log file to evaluate the outcome before you re-run with the -Commit switch.

```
.\Add-SMTPAddresses.ps1 -Domain office365bootcamp.com -MakePrimary -Commit
```
This will add the new alias@office365bootcamp.com as a primary email address
to all mailboxes.

```
.\Add-SMTPAddresses.ps1 -Domain office365bootcamp.com -Commit
```
This will add the new alias@office365bootcamp.com as alias email address
to all mailboxes.

## More Information
https://practical365.com/add-smtpaddresses-ps1-bulk-add-smtp-addresses-to-office-365-mailbox-users/

## Credits
Written by: Paul Cunningham

Modified by: Bauke-Jan Davids

Find me on:

* Twitter:	https://twitter.com/bjdavids97
* LinkedIn:	https://www.linkedin.com/in/bauke-jan-d-b40aa0116/
* Github:	https://github.com/BJD1997


Additional contributors:
- Scott Buchanan [GitHub](https://github.com/scottsb) | [Website](https://buchanan.works/)

Additional references:

- Tim McMichael's blog post: [Wayback Machine](https://web.archive.org/web/20160115155810/http://blogs.technet.com/b/timmcmic/archive/2015/05/17/office-365-bulk-update-email-addresses.aspx) | [Microsoft Technet Archive](https://docs.microsoft.com/nl-nl/archive/blogs/timmcmic/office-365-bulk-update-email-addresses)
