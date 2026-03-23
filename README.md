# Active Directory Home Lab Deployment (Domain Setup + Client Integration)

## Project Summary

### Description
This project is a hands-on **Active Directory lab implementation and walkthrough** demonstrating how to:
- Install and configure Active Directory Domain Services (AD DS)
- Promote a Domain Controller
- Create and manage users and Organizational Units (OUs)
- Join a client machine to the domain
- Enable Remote Desktop access for domain users
- Automate bulk user creation using PowerShell

This project simulates a real-world enterprise environment and showcases foundational system administration skills.

### Languages Used
- PowerShell (for bulk user creation)

### Environments Used
- Windows Server (Domain Controller - DC-1)
- Windows 10/11 (Client Machine - Client-1)

### Technologies / Services Used
- Active Directory Domain Services (AD DS)
- Active Directory Users and Computers (ADUC)
- Remote Desktop
- Group Policy concepts (introductory)
- PowerShell ISE

---

## Media

> NOTE: Replace image placeholders with your screenshots.

### Example:
![AD Installation](images/ad-install.png)
![OU Structure](images/ou-structure.png)
![Client Joined](images/client-joined.png)
![PowerShell Script](images/powershell-users.png)

---

## Demonstration

---

## Part 1: Active Directory Installation & Domain Setup

### Step 1: Install Active Directory Domain Services

1. Log into **DC-1**
2. Open **Server Manager**
3. Click **Add Roles and Features**
4. Select:
   - Active Directory Domain Services
5. Complete installation

📸 *Screenshot Placeholder*  
![AD DS Install](images/ad-ds-install.png)

---

### Step 2: Promote Server to Domain Controller

1. Click **Promote this server to a domain controller**
2. Select:
   - **Add a new forest**
3. Root domain name: mysomain.com

4. Set Directory Services Restore Mode (DSRM) password
5. Complete installation and reboot

📸 *Screenshot Placeholder*  
![Domain Setup](images/domain-setup.png)

---

### Step 3: Log into Domain

After restart:

- Login as: mydomain.com\labuser

📸 *Screenshot Placeholder*  
![Domain Login](images/domain-login.png)

---

## Create Domain Admin User & Organizational Units

### Step 4: Open Active Directory Users and Computers (ADUC)

- Navigate to: Tools → Active Directory Users and Computers

---

### Step 5: Create Organizational Units (OUs)

Create the following OUs:
- `_EMPLOYEES`
- `_ADMINS`

📸 *Screenshot Placeholder*  
![OU Creation](images/ou-creation.png)

---

### Step 6: Create Admin User

1. Inside `_ADMINS`, create a new user:
 - Name: Jane Doe
 - Username:
   ```
   jane_admin
   ```
 - Password:
   ```
   Cyberlab123!
   ```

📸 *Screenshot Placeholder*  
![User Creation](images/user-creation.png)

---

### Step 7: Assign Domain Admin Privileges

1. Open **Properties** of `jane_admin`
2. Go to **Member Of**
3. Add: Domain Admins
📸 *Screenshot Placeholder*  
![Domain Admin Assignment](images/domain-admin.png)

---

### Step 8: Login as Admin User

- Log out of DC-1
- Log back in as: mydomain.com\jane_admin

---

## Join Client Machine to Domain

### Step 9: Join Client-1 to Domain

1. Log into **Client-1** as: labuser
2. Open: System Properties → Change Settings → Domain
3. Enter: mydomain.com
4. Restart the machine

📸 *Screenshot Placeholder*  
![Join Domain](images/join-domain.png)

---

### Step 10: Verify Client in ADUC

1. Log into DC-1
2. Open ADUC
3. Confirm: Client-1 appears under Computers

📸 *Screenshot Placeholder*  
![Client in AD](images/client-ad.png)

---

### Step 11: Create Client OU

1. Create new OU: _CLIENTS
2. Move **Client-1** into `_CLIENTS`

📸 *Screenshot Placeholder*  
![Client OU](images/client-ou.png)

---

## Part 2: Remote Desktop & User Management

---

## Step 12: Enable Remote Desktop for Domain Users

1. Log into Client-1 as: mydomain.com\jane_admin
2. Open: System Properties → Remote Desktop
3. Enable: Allow remote connections
4. Add: Domain Users

📸 *Screenshot Placeholder*  
![Remote Desktop](images/remote-desktop.png)

---

## Step 13: Bulk User Creation with PowerShell

### Open PowerShell ISE as Administrator

1. Log into DC-1 as `jane_admin`
2. Open: PowerShell ISE (Run as Administrator)

---

### Step 14: Run User Creation Script

1. Create a new script file
2. Paste your provided script
3. Run the script

Expected outcome:
- Multiple users created in `_EMPLOYEES`

📸 *Screenshot Placeholder*  
![PowerShell Script](images/script-run.png)

---

### Step 15: Verify Users in ADUC

1. Open ADUC
2. Navigate to: _EMPLOYEES OU
3. Confirm users are created

📸 *Screenshot Placeholder*  
![Users Created](images/users-created.png)

---

### Step 16: Test User Login

1. Log into **Client-1**
2. Use one of the created accounts: mydomain.com<username>
3. Enter password from script

📸 *Screenshot Placeholder*  
![User Login](images/user-login.png)

---
