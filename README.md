
<img width="708" height="484" alt="AD PHOTO" src="https://github.com/user-attachments/assets/d80ccf85-b85c-4057-acb5-8b797accbe1d" />

# Active Directory Deployment (Domain Setup + Client Integration)

## Project Summary

### Description
This project is a hands-on **Active Directory implementation and walkthrough** demonstrating how to:
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

## Demonstration

---

## Part 1: Active Directory Installation & Domain Setup

### Step 1: Install Active Directory Domain Services

1. Log into **Domain Controller**
2. Open **Server Manager** 
3. Click **Add Roles and Features**
4. Select:
   - Next, Next, Next
   - Active Directory Domain Services
   - Add Features
   - Next, Next, Next
   - Check box "Restart the destination Server Automatically if Required" 
5. Complete installation

<img width="902" height="961" alt="Screenshot 2026-03-23 161229" src="https://github.com/user-attachments/assets/a7143b67-5fd8-4611-9e5e-06afa7ebe265" />
<img width="1906" height="735" alt="Screenshot 2026-03-23 161252" src="https://github.com/user-attachments/assets/5e984676-8a26-4d51-8771-13db2a0de5f8" />
<img width="505" height="453" alt="Screenshot 2026-03-23 161309" src="https://github.com/user-attachments/assets/9764e919-ac05-4554-8ef5-3aa6c5f75850" />
<img width="1917" height="1078" alt="Screenshot 2026-03-23 161436" src="https://github.com/user-attachments/assets/d7d292ff-28c4-4133-ab4f-48549c78a74a" />
<img width="1218" height="914" alt="Screenshot 2026-03-23 161513" src="https://github.com/user-attachments/assets/edbe0ad0-9a93-4c53-bcd0-f81d3569423c" />
<img width="727" height="521" alt="Screenshot 2026-03-23 162420" src="https://github.com/user-attachments/assets/84586bf7-41bd-4c34-ae10-141c186cb95e" />
<img width="728" height="519" alt="Screenshot 2026-03-23 162432" src="https://github.com/user-attachments/assets/f21172a4-1a44-431e-a2fa-029ba105f317" />
<img width="733" height="520" alt="Screenshot 2026-03-23 162440" src="https://github.com/user-attachments/assets/86fca9dd-f1c7-4129-b016-2ee59a4c39c9" />
<img width="729" height="520" alt="Screenshot 2026-03-23 162756" src="https://github.com/user-attachments/assets/00e4a6da-0220-4d64-a40c-d23eb674c44b" />
<img width="808" height="578" alt="Screenshot 2026-03-23 162140" src="https://github.com/user-attachments/assets/985defae-87d0-4722-ab20-395fcefb806a" />


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
