# User Offboarding Procedure

## Overview

In this lab, I performed a standard user offboarding procedure in Active Directory on a Windows Server 2019 domain controller (Houtech). This involved creating a dedicated "Disabled Users" OU, removing the departing user from their department security group, moving their account into the Disabled Users OU, disabling the account, resetting the password, and setting an account expiration date — following the common best practices for securely deactivating a former employee's account.

# Objectives


- Create a dedicated "Disabled Users" OU to hold offboarded accounts
- Identify the departing user's account and review its properties
- Remove the user from their department security group
- Move the user's account into the Disabled Users OU
- Disable the user's account to immediately block sign-in
- Reset the account password to a new, unknown value as an added security measure
- Set an account expiration date to enforce a hard cutoff
- Confirm the account was fully offboarded and now sits isolated in Disabled Users


## Process

1 — Creating the Disabled Users OU
Opened Active Directory Users and Computers on Houtech and created a new Organizational Unit named "Disabled Users" directly under Houtech.local, with "Protect container from accidental deletion" checked, to serve as a holding location for offboarded accounts.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20163657.png?raw=true)

2 — Disabled Users OU created
Confirmed the new Disabled Users OU appeared under Houtech.local alongside the existing Builtin, Computers, Department, Domain Controllers, ForeignSecurityPrincipals, Managed Service Accounts, and Users containers, currently empty with no items to show.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20163710.png?raw=true)

3 — Reviewing the user's General properties
Opened the Properties for the user Christopher Brown on the General tab, reviewing his first name, last name, and display name, to confirm this was the correct account to offboard.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20164034.png?raw=true)

4 — Checking group membership
Switched to the Member Of tab on Christopher Brown's Properties and saw he belonged to #Finance_Department and Domain Users, with Domain Users set as the primary group — identifying which security group needed to be removed as part of the offboarding.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20164100.png?raw=true)

5 — Removing the user from their department group
Selected #Finance_Department in the Member Of list and clicked Remove, which prompted a "Remove user from group" confirmation dialog asking whether to remove Christopher Brown from the selected group.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20164116.png?raw=true)

6 — Confirming removal from the group
Opened the #Finance_Department group's Properties and viewed the Members tab, listing Daniel Wilson, Mattew Tylor, and Matthew Taylor as remaining members, confirming Christopher Brown had been successfully removed from the group.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20172540.png?raw=true)

7 — Moving the account to Disabled Users
Right-clicked Christopher Brown's account and selected Move, opening the Move dialog showing the OU tree (Builtin, Computers, Department, Disabled Users, Domain Controllers, ForeignSecurityPrincipals, Managed Service Accounts, Users) to relocate the account into the Disabled Users OU.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20170244.png?raw=true)

8 — Disabling the account
Right-clicked Christopher Brown's account inside the Disabled Users OU and opened the context menu, showing options including Disable Account, Reset Password, Move, and Delete, and selected Disable Account to immediately prevent the user from signing in.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20170303.png?raw=true)

9 — Account disabled confirmation
A confirmation dialog appeared stating "Object Christopher Brown has been disabled," verifying the account was successfully disabled.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20170346.png?raw=true)

10 — Opening the Reset Password dialog
Right-clicked the account and selected Reset Password, opening the Reset Password dialog with empty New Password and Confirm Password fields, to invalidate the user's previous credentials.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20170400.png?raw=true)

11 — Entering the new password
Entered and confirmed a new password in the Reset Password dialog, leaving "User must change password at next logon" unchecked since the account was already disabled.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20170434.png?raw=true)

12 — Password reset confirmation
A confirmation dialog appeared stating "The password for Christopher Brown has been changed," verifying the password reset was successful.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20170444.png?raw=true)

13 — Setting an account expiration date
Opened the Account tab on Christopher Brown's Properties and set the Account Expires option to "End of: Friday, July 10, 2026," establishing a firm expiration date for the disabled account rather than leaving it set to Never.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20172836.png?raw=true)

14 — Final verification
Reviewed the Disabled Users OU one final time, showing Christopher Brown's account as a User object listed inside it, confirming the account was fully removed from its department group, disabled, password-reset, given an expiration date, and relocated — completing the offboarding process.

![image alt](https://github.com/Hamedadams01/User-Offboarding-Procedure/blob/main/Screenshot%202026-07-03%20170453.png?raw=true)

Summary
