<p align="center">
<img src="https://github.com/user-attachments/assets/5a3a196e-512c-4548-a80c-828bf0287693" height="30%" width="30%"/>
</p>

<h1>Software Deployment using Group Policy(GPO)</h1>
In this tutorial, we will use previous Advance Directory Labs to further evaluate the process for adding software to Client PCs using Group Policy.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Virtual Network inside Azure Resource Group
- RDP
- Powershell ISE(used to create Employees)

<h2>Operating Systems Used </h2>

- Windows 10 Pro (22H2)-Client 1
- Windows Server- DC-1(Domain Controller)


<h2>Software to install</h2>
-Mozilla Firefox
-Notepad ++

<h2>Active Directory Labs</h2>
   - [Creating Active Directory](https://github.com/gustygreen/Active-Directory.git)
   - [Configuring On-premises Active Directory for users](https://github.com/gustygreen/configure-ad)
   - [Managing Accounts and Group Policies](https://github.com/gustygreen/Group-Policy)


<h2>Actions and Observations</h2>

<p>
<img src="https://github.com/user-attachments/assets/70f2f67d-7876-4788-9802-a6119c9efd16" height="50%" width="50%"/>
</p>
<p>Azure setup</p>

<p>
<img src="" height="50%" width="50%"/>
</p>
<p>Software Installed</p>


<h2>Verify that software isn't installed</h2>
<p>
<img src="https://github.com/user-attachments/assets/342f2d7d-bd24-497d-9cc5-0f60e4ff3e35" height="50%" width="50%"/>
</p>
<p>
Login as a user and verify that there is no installed Mozilla Firefox or Notepad ++.
</p>

<h3>Software Installation Process</h3>
<p>
<img src="https://github.com/user-attachments/assets/4658fed1-c917-4043-afb6-3474b1c60490" height="50%" width="50%"/>
</p>
<p>
Go to Server Manager-Tools-Group Policy Management
</p>
<p>
<img src="https://github.com/user-attachments/assets/c4a684a8-4a25-4518-b8b0-0e44f3445182" height="50%" width="50%"/>
</p>
<p>
Right click mydomain.com. Select "Create a GPO in this domain, and Link it here..."
</p>

<p>
<img src="https://github.com/user-attachments/assets/0a25af92-21bc-48a9-8cca-8baa54b1554b" height="50%" width="50%"/>
</p>
<p>
Name the new GP "software_deployment". Click OK
</p>

<p>
<img src="https://github.com/user-attachments/assets/8d8f68a4-90ff-43c9-89fc-bf03e50b0b8e" height="50%" width="50%"/>
</p>
<p>
Right click the new software_deployment policy and select Edit.
</p>

<p>
<img src="https://github.com/user-attachments/assets/dccd9b33-aaee-41ec-816c-eb3a7b7e9f47" height="50%" width="50%"/>
</p>
<p>
Expand Computer Configuratio-Expan Policies-Expand Software Setting-Right click Software installation-Select New-Select Package.
</p>

<p>
<img src="https://github.com/user-attachments/assets/600e1494-043b-4741-8f24-77e8a0e6d4c3" height="50%" width="50%"/>
</p>
<p>
Select the shared folder for Software Deployment(\\dc-1\Software Deployment). Click Open.
</p>

<p>
<img src="https://github.com/user-attachments/assets/ed05f297-dfbe-4d84-8f17-e72505d53cdc" height="50%" width="50%"/>
</p>
<p>
Select the Firefox Setup MSI. Click Open.
</p>

<p>
<img src="https://github.com/user-attachments/assets/272a2404-a7a7-4722-9df2-cd031e97be76" height="50%" width="50%"/>
</p>
<p>
Click Assigned. Click OK.
</p>

<p>
<img src="https://github.com/user-attachments/assets/9366b8bd-683d-4633-98cf-7daf9221caff" height="50%" width="50%"/>
</p>
<p>
Mozilla Firefox will now be listed in the Software installation GPO.
</p>

<p>
<img src="https://github.com/user-attachments/assets/01228ce7-0953-4204-af04-27603f5595a8" height="50%" width="50%"/>
</p>
<p>
Follow the same steps to add Notepad ++ to the Software installation GPO list.
</p>


<p>
<img src="https://github.com/user-attachments/assets/b006d3a1-0295-446a-b7e5-b4772799d0a8" height="50%" width="50%"/>
</p>
<p>
<img src="https://github.com/user-attachments/assets/c4a684a8-4a25-4518-b8b0-0e44f3445182" height="50%" width="50%"/>
</p>
<p>
Firefox will now be in the Software Installation Policy
</p>

<p>
 <img src="https://github.com/user-attachments/assets/91d783d6-ae52-47a3-bf09-d9edf8dc86c2"  height="50%" width="50%"/>
</p>
<p> 
Do the same steps to add Notepad ++. Both programs should now be in the Groups Software Installation folder.
</p>

<p>
 <img src="https://github.com/user-attachments/assets/91d783d6-ae52-47a3-bf09-d9edf8dc86c2"  height="50%" width="50%"/>
</p>
<p> 
Right click Firefox-Select Deployment tab-Click "Uninstall this application when it falls out of the scop of management."-Click Apply-Click OK.
</p>
<p>
This will uninstall the program if the user or pc is moved to a different OU, the policy is deleted, or the GPO is removed.
Do the same process for Notepad ++.
</p>

<p>
 <img src="https://github.com/user-attachments/assets/91d783d6-ae52-47a3-bf09-d9edf8dc86c2"  height="50%" width="50%"/>
</p>
<p> 
Right click Firefox-Select Deployment tab-Click "Uninstall this application when it falls out of the scop of management."-Click Apply-Click OK.
</p>
<p>
This will uninstall the program if the user or pc is moved to a different OU, the policy is deleted, or the GPO is removed.
Do the same process for Notepad ++.
</p>


<h3>Install to client-1</h3>

<p>
<img src="https://github.com/user-attachments/assets/9fcf814a-d364-4e7c-813b-584a2ce3dbd6"  height="50%" width="50%"/>
</p>
<p> 
As Admin RDP to client-1-Go to Start-Select Run. Type in "gpupdate /force". Select Enter.(This will update the Group Policy for the Domain.)
</p>

<h3>Verify software installed on client-1.</h3>

<p>
 <img src="https://github.com/user-attachments/assets/a479815a-6f7c-4fa8-9aea-8f78f4b7c079"  height="50%" width="50%"/>
</p>
<p> 
RDP into Client-1 as an Employee and verify that you can now see both Mozilla Firefox and Notepad ++ as selectable apps.
</p>
