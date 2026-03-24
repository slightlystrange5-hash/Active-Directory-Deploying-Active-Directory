
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

1. Navagate to the FLag icon in the top right of Server manager
2. Click **Promote this server to a domain controller**
3. Select:
   - **Add a new forest**
4. Root domain name: mysomain.com

5. Set Directory Services Restore Mode (DSRM) password (Password1)
6. Complete installation and reboot

<img width="1914" height="1071" alt="Screenshot 2026-03-23 163040" src="https://github.com/user-attachments/assets/eeff7c86-fe11-4d2e-a6e2-4db6284559ba" />
<img width="933" height="565" alt="Screenshot 2026-03-23 163105" src="https://github.com/user-attachments/assets/e3a68d5f-71e4-487b-9e84-cb9c927e695e" />
<img width="1302" height="859" alt="Screenshot 2026-03-23 163310" src="https://github.com/user-attachments/assets/862d3e7d-6f08-4d34-8fa5-1af1ec2f69ee" />
<img width="990" height="770" alt="Screenshot 2026-03-23 163529" src="https://github.com/user-attachments/assets/39613b15-e961-4540-be72-ca422fdc21d5" />
<img width="969" height="749" alt="Screenshot 2026-03-23 163605" src="https://github.com/user-attachments/assets/20b7537b-91b5-46b0-978b-c90058103ca0" />
<img width="955" height="699" alt="Screenshot 2026-03-23 163722" src="https://github.com/user-attachments/assets/baf87628-b480-4b4c-855c-4548a239c7ed" />

---

### Step 3: Log into Domain

After restart:

- Login as: mydomain.com\labuser

<img width="1891" height="533" alt="Screenshot 2026-03-23 164006" src="https://github.com/user-attachments/assets/37e1ac0c-cff5-46f2-8d68-a9652ac0ec05" />
<img width="535" height="482" alt="Screenshot 2026-03-23 164016" src="https://github.com/user-attachments/assets/c5d8f1dc-2a34-4470-afb2-ccc88921f2d4" />
<img width="494" height="566" alt="Screenshot 2026-03-23 164021" src="https://github.com/user-attachments/assets/7852f76c-880e-4836-8dad-89128ee12a2b" />
<img width="529" height="618" alt="Screenshot 2026-03-23 164048" src="https://github.com/user-attachments/assets/99e72fa4-884e-4e90-aea3-f008c20118da" />


---

## Create Domain Admin User & Organizational Units

### Step 4: Open Active Directory Users and Computers (ADUC)

- Navigate to: Tools → Active Directory Users and Computers

---
s
### Step 5: Create Organizational Units (OUs)

Create the following OUs:
- `_EMPLOYEES`
- `_ADMINS`

<img width="909" height="806" alt="Screenshot 2026-03-23 164335" src="https://github.com/user-attachments/assets/18ab875f-8d29-4870-bf75-7bf58980eaf2" />
<img width="1058" height="824" alt="Screenshot 2026-03-23 164916" src="https://github.com/user-attachments/assets/b0edb7f1-42d1-4a2a-8d98-c2decf720762" />
<img width="1298" height="725" alt="Screenshot 2026-03-23 165003" src="https://github.com/user-attachments/assets/3e0bcf2d-b497-4fdb-bbb4-1627129e4dd2" />
<img width="976" height="768" alt="Screenshot 2026-03-23 165055" src="https://github.com/user-attachments/assets/b026f13f-cd3a-4efc-9490-999388a40073" />
<img width="601" height="463" alt="Screenshot 2026-03-23 165129" src="https://github.com/user-attachments/assets/abda8a46-d7dd-41a9-9e25-5d8fb84f113e" />
<img width="748" height="659" alt="Screenshot 2026-03-23 165205" src="https://github.com/user-attachments/assets/0a72aeeb-3e9a-4318-b38c-67db8a108be7" />
<img width="893" height="627" alt="Screenshot 2026-03-23 165230" src="https://github.com/user-attachments/assets/971da048-9d00-4eb5-8d44-50842c2ed950" />
<img width="562" height="553" alt="Screenshot 2026-03-23 165249" src="https://github.com/user-attachments/assets/8e44d596-f56f-4e5d-b0c2-c95433d91a4f" />


---

### Step 6: Create Admin User

1. Inside `_ADMINS`, create a new user:
 - Name: Jane Doe
 - Username:
   ```
   jane_doe
   ```
 - Password:
   ```
   Cyberlab123!
   ```

<img width="826" height="867" alt="Screenshot 2026-03-23 165326" src="https://github.com/user-attachments/assets/6ad3bb43-7ece-416b-8d99-d2f2fae6816b" />
<img width="661" height="510" alt="Screenshot 2026-03-23 165404" src="https://github.com/user-attachments/assets/cd21dcaf-01a0-41ed-9b9f-39a21d09be3e" />
<img width="806" height="645" alt="Screenshot 2026-03-23 165438" src="https://github.com/user-attachments/assets/70f18ef2-750f-4e97-830d-f8e7420b1918" />
<img width="734" height="625" alt="Screenshot 2026-03-23 165458" src="https://github.com/user-attachments/assets/c99e025c-84ea-4507-9f43-5b4879682053" />


---

### Step 7: Assign Domain Admin Privileges

1. Open **Properties** of `jane_admin`
2. Go to **Member Of**
3. Add: Domain Admins

<img width="606" height="592" alt="Screenshot 2026-03-23 165527" src="https://github.com/user-attachments/assets/6991820b-dd20-4f25-a7ce-1a0fa0365e8a" />
<img width="572" height="627" alt="Screenshot 2026-03-23 165604" src="https://github.com/user-attachments/assets/145070b1-228a-4b1b-badc-236c33e61195" />
<img width="542" height="696" alt="Screenshot 2026-03-23 165625" src="https://github.com/user-attachments/assets/f992c593-64ad-494e-aba6-ad245e602f75" />
<img width="828" height="759" alt="Screenshot 2026-03-23 165649" src="https://github.com/user-attachments/assets/c26b083d-bf4b-41c5-87b1-fcd514abac43" />
<img width="700" height="681" alt="Screenshot 2026-03-23 165657" src="https://github.com/user-attachments/assets/23300071-13da-4c7e-97d7-267d3861d033" />


---

### Step 8: Login as Admin User

- Log out of DC-1
- Log back in as: mydomain.com\jane_admin

<img width="1912" height="1029" alt="Screenshot 2026-03-23 165724" src="https://github.com/user-attachments/assets/d7d85bb3-3d97-4e3c-8622-54b07f51a25f" />
<img width="1892" height="827" alt="Screenshot 2026-03-23 165746" src="https://github.com/user-attachments/assets/b2d84244-2691-4141-ad25-8fc4b9cc3add" />
<img width="540" height="485" alt="Screenshot 2026-03-23 165754" src="https://github.com/user-attachments/assets/59a4e1d8-5b76-4178-b17c-af63d797aaf6" />
<img width="511" height="583" alt="Screenshot 2026-03-23 165802" src="https://github.com/user-attachments/assets/8b84331e-7d1e-4420-b8b0-1cad8e9cdf13" />
<img width="495" height="598" alt="Screenshot 2026-03-23 170314" src="https://github.com/user-attachments/assets/f21644a2-fe0c-42e4-b6d7-4505fbf0705a" />

---

## Join Client Machine to Domain

### Step 9: Join Client-1 to Domain

1. Log into **Client-1** as: labuser
2. Open: System Properties → Change Settings → Domain
3. Enter: mydomain.com
4. Log in with jane_admin credentials
5. Restart the machine

<img width="1646" height="638" alt="Screenshot 2026-03-23 171507" src="https://github.com/user-attachments/assets/bcd0a283-02fc-4186-af48-76fce014703d" />
<img width="469" height="439" alt="Screenshot 2026-03-23 171530" src="https://github.com/user-attachments/assets/0b4c34e8-e44f-4d88-8b56-f65f444e2ffe" />
<img width="911" height="810" alt="Screenshot 2026-03-23 171616" src="https://github.com/user-attachments/assets/373eb25d-8cda-46d1-8f44-7998aec24869" />
<img width="489" height="495" alt="Screenshot 2026-03-23 172132" src="https://github.com/user-attachments/assets/d6f147fc-cc99-439d-870c-36ab695a6fbc" />
<img width="570" height="543" alt="Screenshot 2026-03-23 172214" src="https://github.com/user-attachments/assets/5680d6c0-7d29-419b-8a6a-38c77cf23d6b" />
<img width="1908" height="1013" alt="Screenshot 2026-03-23 172254" src="https://github.com/user-attachments/assets/8515709c-820f-409b-b280-7533cdae97bc" />
<img width="1901" height="997" alt="Screenshot 2026-03-23 172421" src="https://github.com/user-attachments/assets/c7d2a68a-108b-4419-969d-604b01cdeab8" />
<img width="1905" height="1016" alt="Screenshot 2026-03-23 172431" src="https://github.com/user-attachments/assets/0a803a38-ee54-4888-a580-2c7f75ab0f9f" />
<img width="1908" height="1008" alt="Screenshot 2026-03-23 172450" src="https://github.com/user-attachments/assets/f9562e2a-12d5-4a05-8f8e-f4acef247c47" />


---

### Step 10: Verify Client in ADUC

1. Log into DC-1
2. Open ADUC
3. Confirm: Client-1 appears under Computers

<img width="913" height="810" alt="Screenshot 2026-03-23 173050" src="https://github.com/user-attachments/assets/fb431df7-5412-46bf-a7eb-b56edfa19009" />
<img width="1012" height="736" alt="Screenshot 2026-03-23 173123" src="https://github.com/user-attachments/assets/a12492be-5884-4c4b-850a-46e84eadac36" />
<img width="1098" height="792" alt="Screenshot 2026-03-23 173134" src="https://github.com/user-attachments/assets/beafd1e4-d3d2-4b88-8036-e0b4db90ebaa" />


---

### Step 11: Create Client OUs

1. Create new OU: _CLIENTS
2. Move **Client-1** into `_CLIENTS`

<img width="732" height="463" alt="Screenshot 2026-03-23 173435" src="https://github.com/user-attachments/assets/6fa53b35-4824-4832-a7ed-b51d78210acb" />
<img width="866" height="724" alt="Screenshot 2026-03-23 173521" src="https://github.com/user-attachments/assets/25e6ca85-a231-4036-a4dd-761148c428ae" />
<img width="666" height="554" alt="Screenshot 2026-03-23 173542" src="https://github.com/user-attachments/assets/37827003-30b6-4d87-98f0-cd8bd5d0bce5" />
<img width="748" height="538" alt="Screenshot 2026-03-23 173614" src="https://github.com/user-attachments/assets/f2b2ad67-c811-4c38-a192-5cbfbd5b691a" />
<img width="650" height="580" alt="Screenshot 2026-03-23 173625" src="https://github.com/user-attachments/assets/39f32fc8-4cf3-4bf6-abf6-cc5202c5f281" />
<img width="622" height="648" alt="Screenshot 2026-03-23 173650" src="https://github.com/user-attachments/assets/8f8a3df8-2b81-4914-9703-96f893a8f09a" />


---s

## Part 2: Remote Desktop & User Management

---

## Step 12: Enable Remote Desktop for Domain Users

1. Log into Client-1 as: mydomain.com\jane_admin
2. Open: System Properties → Remote Desktop
3. Enable: Allow remote connections
4. Add: Domain Users

<img width="1910" height="758" alt="Screenshot 2026-03-23 214907" src="https://github.com/user-attachments/assets/79ef332a-c9bd-4777-87e1-4070842182bc" />
<img width="491" height="465" alt="Screenshot 2026-03-23 214917" src="https://github.com/user-attachments/assets/32833cb4-414a-425f-88b9-561782aa20f7" />
<img width="498" height="585" alt="Screenshot 2026-03-23 214920" src="https://github.com/user-attachments/assets/84003b1e-4054-48d8-8c84-4fc56514219d" />
<img width="498" height="585" alt="Screenshot 2026-03-23 214920" src="https://github.com/user-attachments/assets/036420a0-860f-4f42-a24f-2e62513d047f" />
<img width="479" height="657" alt="Screenshot 2026-03-23 215040" src="https://github.com/user-attachments/assets/591de33e-1de1-4bcf-9441-79565f7679fc" />
<img width="852" height="802" alt="Screenshot 2026-03-23 215237" src="https://github.com/user-attachments/assets/28adcca6-c547-41d9-bc7c-137e020bdab5" />
<img width="452" height="504" alt="Screenshot 2026-03-23 215254" src="https://github.com/user-attachments/assets/4e154c1e-05c7-4829-a6be-72aa0a53aaa3" />
<img width="446" height="504" alt="Screenshot 2026-03-23 215320" src="https://github.com/user-attachments/assets/98a2558d-214f-4acc-851f-0ddeecd815c7" />
<img width="426" height="505" alt="Screenshot 2026-03-23 215404" src="https://github.com/user-attachments/assets/efee1e8f-3d44-4839-8368-4177fa2f6b93" />
<img width="594" height="513" alt="Screenshot 2026-03-23 215414" src="https://github.com/user-attachments/assets/76c7008d-bad0-4474-915a-3dd6647d4749" />
<img width="474" height="540" alt="Screenshot 2026-03-23 215433" src="https://github.com/user-attachments/assets/3a01f47b-ba8b-4835-9fe5-1ad83dd2bacd" />


---

## Step 13: Bulk User Creation with PowerShell

### Open PowerShell ISE as Administrator

1. Log into DC-1 as `jane_admin`
2. Open: PowerShell ISE (Run as Administrator)

---

### Step 14: Run User Creation Script

1. Run Script provided here, https://raw.githubusercontent.com/slightlystrange5-hash/Active-Directory-Deploying-Active-Directory/refs/heads/main/SCRIPT


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
