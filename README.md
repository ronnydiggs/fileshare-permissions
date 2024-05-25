<p align="center">
<img src="https://github.com/ronnydiggs/fileshare-permissions/assets/64152064/610a2f57-2eec-4063-bc67-c0d01f396c93" width="250"/>
</p>

<h1>Network File Shares and Permissions - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the Network File Shares and Permissions lab. 
Need to have AD installed on a domain controller and a client VM before proceeding.
Check the Configuring Active Directory Lab.
<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Client VM
- Active Directory VM

<h2>Operating Systems Used </h2>

- Windows 10</b> 
- Windows Server 2022</b> 

<h2>Create File shares with varying permissions </h2>

<p>
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/9b898efa-c5ed-4d6f-b5ec-28fbecd57694" width="400"/>
<img src="https://github.com/ronnydiggs/fileshare-permissions/assets/64152064/460674f4-1672-4f72-960f-1ec5efa7773b" width="400"/>
</p>
<p>
Log into DomainController (20.62.172.190) as the domain admin account (mydomain.com\ronny)
</p>
<p>
Log into Client1 (20.51.184.132) as a random user (mydomain.com\wera.ram)
</p>
<br />

<p>
<img src="https://github.com/ronnydiggs/fileshare-permissions/assets/64152064/50765d42-f676-4203-8603-73ebfebda18e" width="500"/>
</p>
<p>
On the Domain controller, create 4 folders to test access: read-access, write-access, no-access, accounting
</p>
<br />

<p>
<img src="https://github.com/ronnydiggs/fileshare-permissions/assets/64152064/e2fb199d-21e1-4c7f-a2c9-2bb17a5c3761" width="400"/>
<img src="" width="400"/>
</p>
<p>
Assign permission types to each folder corresponding with its name. Read to read-access. Read/Write to write-access. Domain Admins to no-access. Note the \\DomainControlle\ for the next step.
</p>
<br />

<h2>Attempt to access files as non-admin user</h2>

<p>
<img src="https://github.com/ronnydiggs/fileshare-permissions/assets/64152064/87ea030a-e962-425d-802e-4dc9e657d999" width="400"/>
</p>
<p>
On Client 1, go to start run "\\DomainControlle". Each folder has access permission set for any user within the domain.
</p>
<br />

<h2>Test access in a security group</h2>

<p>
<img src="https://github.com/ronnydiggs/fileshare-permissions/assets/64152064/a43376ee-ae86-43e3-84bf-6216c7b7cfbb" width="400"/>
</p>
<p>
Create an organizational unit "_ACCOUNTANTS" with a security group "ACCOUNTANTS".
</p>
<br />

<p>
<img src="https://github.com/ronnydiggs/fileshare-permissions/assets/64152064/a5263375-093d-4082-8075-ed5d9cfa6986" width="400"/>
</p>
<p>
On Domain Controller, add some users to the ACCOUNTANTS security group and make access Read/Write.
</p>
<br />

<p>
<img src="https://github.com/ronnydiggs/fileshare-permissions/assets/64152064/127d7949-b298-4a9a-9166-ee7902e483a4" width="400"/>
</p>
<p>
On Client 1, log in to users within the ACCOUNTANTS security group and test access to the accounting folder. Log in to users not in the security group and test access. Only the users within the security group can access the accounting folder.
</p>
<br />
