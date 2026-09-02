[← Back to main README](../README.md)

# Part 7: Creating and Managing OUs, Users, and Group Policy

## Create Organizational Units (OUs)

An **Organizational Unit (OU)** is a container within Active Directory used to organize users, computers, and groups — typically mirroring departments or teams — so that permissions and policies can be applied to logical groups of objects.

1. Go to **Server Manager** → **Tools** → **Active Directory Users and Computers**.
2. Right-click the domain (`homelab.local`) → **New** → **Organizational Unit**.
3. Name it (e.g., `Sales`).
4. Repeat this for each department, e.g. `Tech`, `HR`, `QA`.

> **Note — Deleting an OU:** OUs are protected from accidental deletion by default. To delete one, go to **View** → enable **Advanced Features**, then right-click the OU → **Properties** → **Object** tab → uncheck **Protect object from accidental deletion**. You can now delete it normally.

## Create Users

1. Navigate to the OU you want the user to belong to.
2. Either click the **Add User** icon in the toolbar, or right-click the OU → **New** → **User**.
3. Fill in the user's details and set an initial password.

## Relax the Default Password Policy (Lab Only)

Managing a unique, complex password for every lab user account gets impractical fast, so for this lab environment we'll relax the default domain password policy:

1. Go to **Tools** → **Group Policy Management**.
2. Expand **Forest** → **Domains** → `homelab.local`.
3. Right-click **Default Domain Policy** → **Edit**.
4. Navigate to **Computer Configuration** → **Policies** → **Windows Settings** → **Security Settings** → **Account Policies** → **Password Policy**.
5. Set the following:
   - **Enforce password history**: `0`
   - **Minimum password age**: `0`
   - **Minimum password length**: `0`
   - **Password must meet complexity requirements**: `Disabled`

> **Warning:** These settings remove essentially all password protection and should **never** be used outside of an isolated lab environment.

> **Reminder:** Any time you change a Group Policy, run `gpupdate /force` from an elevated terminal on the target machine to apply the change immediately instead of waiting for the normal refresh interval.

## Common User Management Tasks

- **Reset a password:** Right-click the user → **Reset Password**.
- **Disable an account:** Right-click the user → **Disable Account**.
- **Set an account expiration date** (useful for temp employees): Double-click the user → **Account** tab → under **Account expires**, set the expiration date.
- **Restrict logon hours:** Double-click the user → **Account** tab → **Logon Hours** → set allowed login windows.

## Enforce Logon Hour Restrictions via Group Policy

Setting logon hours on a user account restricts *when* they can log in, but by default it won't kick them off automatically if their session is already active when their allowed hours end. To enforce an automatic logoff:

1. Go to **Tools** → **Group Policy Management**.
2. Expand **Forest** → **Domains** → `homelab.local`.
3. Right-click **Default Domain Policy** → **Edit**.
4. Navigate to **Computer Configuration** → **Windows Settings** → **Security Settings** → **Local Policies** → **Security Options**.
5. Enable **Network security: Force logoff when logon hours expire**.
6. Run `gpupdate /force` to apply the change.

---

