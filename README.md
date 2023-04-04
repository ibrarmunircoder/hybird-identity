<h1 align="center">Hybird Identity Lab</h1>
<h4 align="center">Connect on-premises AD with Azure AD</h4>
<br>
Setting up Active Directory is a delicate process and this article offers a complete step by step guide on how to set it up on a **Windows Server 2022** machine.
<br>

### Prerequisites:

1. Microsoft Azure Account
2. Windows Server ISO file [Download Link](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022)
3. VirtualBox
4. Minimum Hardware (8GB RAM)

Let's define what is a hybird identity.

**Hybrid Identity** is the process of connecting your on-premises Active Directory with your Azure Active Directory. You do this to enable a single account to have access to resources on-premises and in the cloud.

## Azure AD Connect Authenication Methods

1. Password Hash Synchronization (PHS)
2. Pass-through Authentication (PTA)
3. Federated authentication

## How to install Active Directory Domain Services and promote to Domain Controller!

To install Active Directory Domain Services (ADDS) on a Windows Server 2022, follow
these steps:

1. Log in to your Windows Server 2022 as an administrator.
2. Open the Server Manager by clicking on the Server Manager icon on the taskbar, or
   by typing "Server Manager" in the Start menu.
3. In the Server Manager, click on the "Add roles and features" option in the dashboard.
4. In the "Add Roles and Features Wizard," click "Next" on the Before You Begin page.
5. On the "Installation Type" page, select "Role-based or feature-based installation," and
   click "Next."
6. On the "Server Selection" page, select the server you want to install ADDS on, and
   click "Next."
7. On the "Server Roles" page, select "Active Directory Domain Services," and click
   "Add Features" when prompted to add required features.
8. On the "Features" page, click "Next" without selecting any additional features.
9. On the "AD DS" page, review the information, and click "Next."
10. On the "Confirmation" page, review your selections, and click "Install" to start the
    installation.
11. Wait for the installation to complete, and then click "Close" on the "Results" page.
12. After the installation completes, you will see a notification to complete the AD DS
    Configuration Wizard. Click on "Promote this server to a domain controller" link to
    open the wizard.
13. In the wizard, select "Add a new forest" and enter the root domain name, and follow
    the prompts to configure the domain and the directory services.
14. When the configuration is complete, click "Finish" to close the wizard.
15. Reboot your server to complete the installation.

## How to Setup Remote Server Administration Tools on Staging Server!

To install Remote Server Administration Tools (RSAT) on a member server, follow these
steps:

1. Log in to your Windows Server 2022 as an administrator.
2. Join your Staging Server to existing domain.
3. Restart your server after joining the domain and login with Domain Admin account.
4. Open PowerShell as an administrator.
5. Run the following command to install the RSAT tools for Active Directory Domain
   Services:
   Install-WindowsFeature RSAT-ADDS -IncludemanagementTools
6. [Install Azure AD Connect Agent on this server](https://www.microsoft.com/en-us/download/details.aspx?id=47594)
7. [Follow the steps from Microsoft official documentation](https://learn.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connectinstall-express)

## How to Setup Remote Server Administration Tools on Sync Server!

To install Remote Server Administration Tools (RSAT) on a member server, follow these
steps:

1. Log in to your Windows Server 2022 as an administrator.
2. Join your Staging Server to existing domain.
3. Restart your server after joining the domain and login with Domain Admin account.
4. Open PowerShell as an administrator.
5. Run the following command to install the RSAT tools for Active Directory Domain
   Services:
   Install-WindowsFeature RSAT-ADDS -IncludemanagementTools
6. [Install Azure AD Connect Agent on this server](https://www.microsoft.com/en-us/download/details.aspx?id=47594)
7. [Follow the steps from Microsoft official documentation](https://learn.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connectinstall-express)

## Additional Resources

1. [Setup Active Directory Domain Services Step by Step](https://infrasos.com/how-to-setup-active-directory-on-windows-server-2022/)
2. [Hybird Identity](https://infrasos.com/how-hybrid-identity-with-azure-active-directory-ad-works/)

![VirtualBox Screenshot](/images/virtualbox.PNG)
![Sync Server Screenshot](/images/syncserver.PNG)
![Domain Controller Server Screenshot](/images/domain-controller.PNG)

## Azure Active Directory (Default) Syncronization Example

![Active Directory Server Screenshot](/images/azure-ad.PNG)
