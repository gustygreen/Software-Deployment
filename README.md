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
<img src="https://github.com/user-attachments/assets/c4a684a8-4a25-4518-b8b0-0e44f3445182" height="50%" width="50%"/>
</p>
<p>
Go to Server Manager-Tools-Group Policy Management
</p>
<p>
<img src="https://github.com/user-attachments/assets/c4a684a8-4a25-4518-b8b0-0e44f3445182" height="50%" width="50%"/>
</p>
<p>
Go to Server Manager-Tools-Group Policy Management
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

<h3>Install to client-1</h3>
<p>
 <img src="https://github.com/user-attachments/assets/e429dd6f-341e-4635-a31e-cb121b7ee64d"  height="50%" width="50%"/>
</p>
<p> 
Right click on the software(Firefox)-Select Deployment tab-Check Install this application at logon. Select Basic under Installation user interface options. Click Apply, OK.
</p>
<p>
 <img src="https://github.com/user-attachments/assets/64c9458b-3cdb-4912-8330-51b98be90dd0"  height="50%" width="50%"/>
</p>
<p> 
Do the same for Notepad ++. Close out all windows on DC.
</p>

<p>
<img src="https://github.com/user-attachments/assets/9fcf814a-d364-4e7c-813b-584a2ce3dbd6"  height="50%" width="50%"/>
</p>
<p> 
Go to Start-Select Run. Type in "gpupdate /force". Select Enter.(This will update the Group Policy for the Domain.)
</p>

<h3>Verify software installed on client-1.</h3>

<p>
 <img src="https://github.com/user-attachments/assets/e429dd6f-341e-4635-a31e-cb121b7ee64d"  height="50%" width="50%"/>
</p>
<p> 
RDP onto client-1 as an employee.
</p>
<p>
 <img src="https://github.com/user-attachments/assets/64c9458b-3cdb-4912-8330-51b98be90dd0"  height="50%" width="50%"/>
</p>
<p> 
Verify that you can now see both Mozilla Firefox and Notepad ++ as selectable apps.
</p>
