# Example: Configuring Active Directory Domain and Users on Windows Server

In this example, we will walk through the configuration of a new Active Directory domain, the creation of users and groups, and the application of a Group Policy in a Windows Server environment.

## Prerequisites
- Windows Server 2016 or later.
- A static IP address and correct DNS configuration.
- Administrative privileges on the server.

## Steps

### 1. **Install Active Directory Domain Services**
- Open **Server Manager** > **Manage** > **Add Roles and Features**.
- Select **Active Directory Domain Services (AD DS)**, and click **Next** to install.
  
### 2. **Promote Server to Domain Controller**
1. After installation, click the **Promote this server to a domain controller** link.
2. Choose **Add a new forest** and specify the domain name (e.g., `corp.local`).
3. Set the **DSRM password** for recovery.

### 3. **Create Users and Groups**
1. Open **Active Directory Users and Computers** (ADUC).
2. Right-click **Users** > **New** > **User**.
3. Fill in user information (username, password) and set account options.
4. For group creation, right-click **Users** > **New** > **Group**.
5. Assign users to groups and delegate necessary permissions.

### 4. **Apply Group Policy**
- Open **Group Policy Management**.
- Right-click the domain > **Create a GPO** and link it to the domain.
- Configure settings, such as password policies or desktop configurations.

## Testing the Configuration
1. **Ping** the domain controller to ensure network connectivity.
2. Test the user login process on a client machine by logging in with the newly created credentials.

## Conclusion
This example demonstrates the fundamental steps for setting up Active Directory in a Windows Server environment. From domain creation to user management, these steps lay the groundwork for a fully functional and secure AD environment.
