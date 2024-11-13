# Active Directory Configuration

Configuring Active Directory is a critical step in building a secure, organized, and manageable network environment. This guide provides comprehensive steps to install, configure, and secure Active Directory in Windows Server environments.

## Prerequisites
Before beginning the Active Directory installation, ensure the following prerequisites:
- A Windows Server machine (2016 or later).
- A static IP address and proper DNS configuration.
- Administrative privileges on the server.

## Installing Active Directory Domain Services (AD DS)

### Step 1: Install AD DS Role
1. Open **Server Manager**.
2. Click on **Manage** > **Add Roles and Features**.
3. In the wizard, select the **Active Directory Domain Services** role and click **Next** to continue the installation.

### Step 2: Promote the Server to a Domain Controller
After the installation, the next step is to promote the server to a domain controller:
1. Open **Server Manager** and click the notification flag in the top right corner.
2. Click on **Promote this server to a domain controller**.
3. Choose **Add a new forest** and enter your root domain name (e.g., `corp.local`).
4. Set the **Directory Services Restore Mode (DSRM)** password, which is used for disaster recovery.

### Step 3: Complete the Configuration
1. Configure the **NetBIOS name**, which is the legacy name used by older systems.
2. Choose the domain and forest functional levels (e.g., Windows Server 2016).
3. Review the settings, and click **Next** to begin the promotion.
4. The server will reboot after promotion to apply the changes.

## Creating and Managing Active Directory Objects

### 1. **Creating Organizational Units (OUs)**
Organizational Units are used to organize users, groups, and computers into logical containers:
- Open **Active Directory Users and Computers (ADUC)**.
- Right-click the domain, choose **New** > **Organizational Unit**, and name the OU appropriately.

### 2. **Creating Users**
1. Open **Active Directory Users and Computers (ADUC)**.
2. Right-click the **Users** container or an OU, select **New** > **User**.
3. Fill in user details (e.g., first name, last name, username).
4. Set the initial password, and choose whether the user must change it at the next logon.

### 3. **Creating Groups**
1. Open **ADUC**.
2. Right-click the OU or **Users** container, choose **New** > **Group**.
3. Specify the group name, scope, and type (e.g., security group or distribution group).

## Integrating Active Directory with Other Services

### 1. **DNS Integration**
Active Directory relies heavily on DNS for locating domain controllers and other network services. Ensure your server is configured with a **static IP** and points to itself as the primary DNS server.

### 2. **Group Policy Configuration**
Group Policies allow administrators to manage security and configuration settings across all domain-joined computers. You can apply group policies via **Group Policy Management Console (GPMC)**.

- Open **GPMC**.
- Right-click the domain or OU, select **Create a GPO in this domain**, and then configure it.
  
### 3. **Time Synchronization**
Time synchronization is crucial for domain authentication. Ensure all domain controllers are synchronized to a reliable time source, such as an internal NTP server or **Windows Time Service**.

## Best Practices
- Use **strong passwords** and **multi-factor authentication** for domain administrator accounts.
- Keep the domain controllers up to date with the latest security patches.
- Regularly back up Active Directory to protect against data loss.

By following these configuration steps, you'll have a fully functioning and secure Active Directory environment ready for managing users, computers, and network resources.
