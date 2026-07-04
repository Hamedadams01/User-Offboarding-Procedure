# User-Offboarding-Procedure


# Overview
This project documents the process of offboarding a terminated or departing employee in Active Directory, ensuring the account is disabled, restricted, and secured without permanently deleting data.
# Objectives

- Disable account access immediately
- Remove group memberships tied to active roles
- Reset credentials to prevent unauthorized logins
- Relocate the account for easier administrative tracking
- Set an account expiration date for compliance

# Step-by-Step

- I created a new Organizational Unit named "Disabled Users" under Houtech.local, checking "Protect container from accidental deletion" to prevent it from being removed by mistake.
- I opened Active Directory Users and Computers and confirmed the new OU was empty and ready to receive offboarded accounts.
- I located the departing employee (Christopher Brown) under the Finance Department OU and opened his Properties dialog.
- I went to the Member Of tab and saw he belonged to #Finance_Department and the default Domain Users group.
- I selected #Finance_Department and clicked Remove, confirming "Yes" on the prompt to strip his department-level access.
- I right-clicked the user and selected Move, then selected the Disabled Users OU as the destination container.
- I right-clicked the account again and selected Disable Account, confirming the system message: "Object Christopher Brown has been disabled."
- I opened Reset Password and set a new password the user doesn't know, adding an extra layer of security beyond just disabling the account.
- I confirmed the system message: "The password for Christopher Brown has been changed."
- I opened the Account tab and set an account expiration date (End of: July 10, 2026) instead of leaving it set to Never, so the account would automatically deactivate further.
- I did a final check of the Disabled Users OU and confirmed Christopher Brown now appeared there, fully offboarded.

# Conclusion

- The account was disabled, stripped of group access, and moved to a dedicated OU
- Password was reset to prevent any residual access using old credentials
- An account expiration date was added as a final safeguard
- This process creates a clean, auditable offboarding trail suitable for compliance review
