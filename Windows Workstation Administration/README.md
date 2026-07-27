# Windows Workstation Administration

## Overview
Configured and administered a Windows 11 virtual workstation to practice foundational Windows administration tasks.

The workstation was renamed using a consistent naming convention and configured with separate administrator and standard user accounts.

## Environment

- Host OS: Windows 11 Pro
- VM Platform: Oracle VirtualBox
- GuestOS: Windows 11 Pro
- Workstation Name: PC01

## Configuration
### Workstation Naming
The default computer name was changed to `PC01` to establish a consistent workstation naming convention. 

The `hostname` command was used to display the current computer name assigned to the system.

The `whoami` command was used to identify the current logged-in user account.

The `systeminfo` command was used to collect detailed system information, including the operating system, version, and virtualization environment. It was also used to verify that the workstation was running Windows 11 Pro and hosted within Oracle VirtualBox. 

**Example**

 `systeminfo | findstr /B /C:"OS Name" /C:"OS Version" /C:"System Manufacturer" /C:"System Model"`
- `findstr` filters command output by searching for specific text
- `/B` filters results that begin with the specified text
- `/C` searches for an exact phrase

### Local User Account Management
Created local accounts to simlulate different workstation access roles. The process included creating new user accounts, assigning users to appropriate lcoal groups, and removing unncessary accounts from the workstation.

**Configured accounts:**
- **Admin01**: dedicated administrator account
- **User01:** standard user account
- **User02:** standard user account

**Admin01** was added to the local **Adminstrators** group.
**User01** and **User02** were added to the local **Users** group.

**Commands:**
- `New-LocalUser` creates new local user accounts
- `Add-LocalGroupMember` assigns uers to local groups
- `Remove-LocalUser` removes unused local accounts

## Troubleshooting
### Computer Rename Access Denied
**Issue:** The computer rename command returned an "Access Denied" error.

**Cause:** The rename command was attempted from a Windows Terminal without elevated administrative privileges.

**Solution:** Terminal was reopened with administrator privileges and the computer rename command was completed successfully.

## Concepts Learned
### Local Users and Groups
Windows uses local groups to organize user permissions and privilges. Assigning users to appropriate groups provides a structured method for managing access. Local accounts can be created, modified, and removed. 

## Screenshots

### Windows Environment Verification
![Windows Verify](screenshots/Environment.png)

### Local Users and Groups Configuration
![User groups](screenshots/User%20groups.png)


