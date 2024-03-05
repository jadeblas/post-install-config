<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1 align="center">osTicket - Post-Installation Configuration</h1>
This guide covers the post-installation configuration of osTicket, an open-source help desk ticketing system. It assumes you have completed the installation, set up login credentials, and performed cleanup on osTicket in your Virtual Machine environment as outlined in the previous tutorial <a href ="https://github.com/jadeblas/osticket-prereqs">"osTicket - Prerequisites and Installation"</a>.<br />

</br>

<h2>Environments and Technologies Used</h2>
<ul>
  <li>Microsoft Azure (Virtual Machines/Compute)</li>
  <li>Remote Desktop</li>
  <li>Internet Information Services (IIS)</li>
  <li>osTicket</li>
</ul>

</br>

<h2>Operating Systems Used</h2>
<ul>
  <li>Windows 10</li>
</ul>

</br>

<h2>Post-Installation Configuration Objectives</h2>
<ol>
  <li>Familiarize with the UI of osTicket</li>
  <li>Create and Configure Roles</li>
  <li>Create Tickets</li>
  <li>Create Agents and Users</li>
  <li>Set up Service Level Agreements (SLA Plans) in the ticketing system</li>
  <li>Configure Help Topics</li>
</ol>

</br>

<h2>Configuration Steps</h2>

<h3>Setting Up Roles, Departments, & Teams</h3>

<p>
  
<ul>
  <li><b>Note</b>: osTicket has two panels: <b>Agent Panel</b> and <b>Admin Panel</b>. You'll see the opposite panel displayed on the top right of the UI next to your user login name.</li>
  <ul>
    <li>For example, user "josh" is on the Agent Panel.</li>
    <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/d89242ae-72ae-46d8-a1d5-a361fcc1b5c8" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
  <li><b>Roles</b> grant permissions to Agents in their assigned Departments.</li>
  <ul>
    <li>In the <b>Admin Panel</b>, go to the <b>Agents</b> tab and select <b>Roles</b>, then click <b>Add New Role</b>.</li>
    <ul>
      <li><b>Note</b>: osTickets creates four default Roles (All Access, Expanded Access, Limited Access, and View Only).</li>
      <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/ad0f8d92-16f7-4ede-a78d-5b88b1a085a9" alt="Disk Sanitization Steps"/></li>
    </ul>
    <li>Name the new Role <b>Supreme Admin</b>, and click the <b>Permissions</b> tab to assign specific permissions. For "Supreme Admin," check every box under the <b>Tickets</b>, <b>Tasks</b>, and <b>Knowledgebase</b> tabs. Click <b>Add Role</b> to finish creating the role.</li>
    <ul>
      <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/3e0e641d-4ff2-49d8-9c64-59bb1d7a6493" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
  </ul>

  <li><b>Departments</b> are used to route and resolve tickets based on their importance or instructions.</li>
  <ul>
  <li>Still on the Agents tab, click on <b>Departments</b> and select <b>Add New Department</b>.</li>
  <ul>
    <li><b>Note</b>: osTicket also creates two default Departments (Maintenance and Support).</li>
    <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/41007487-0cc4-4efb-a224-994389660200" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
  <li>Name the Department <b>System Administrators</b> (leave everything else default for now), then click <b>Create Dept</b> to finalize.</li>
  <ul>
    <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/9d8e5892-dc2a-4894-9e0a-7614efcf411c" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
  </ul>

  <li><b>Teams</b> organize Agents from different Departments to handle specific issues and supersede Agents and their Departments' parameter rules.</li>
  <ul>
    <li>In the Agents tab, click on <b>Teams</b> and select <b>Add New Team</b>.</li>
    <ul>
    <li><b>Note</b>: osTicket also creates a default Team (Level I Support).</li>
    <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/c4f1d4fc-8354-49e1-b21d-f7988a6aef4c" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
    <li>Name the Team <b>Level II Support</b> and click <b>Create Team</b> to complete the process.</li>
    <ul>
      <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/fd5eb137-8262-44a8-a384-4376a7435705" height="80%" width="80%" alt="Disk Sanitization Steps"/></li> 
    </ul>
  </ul>
  
</ul>
  
</p>

</br>

<h3>Enabling Ticket Creation for All</h3>

<p>
  
<ul>
  <li>In the <b>Admin Panel</b>, navigate to the <b>Settings</b> tab and select <b>Users</b>. Ensure that <b>Registration Required</b> is unchecked. This allows anonymous ticket creation.</li>
  <ul>
    <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/dd5d8e87-b7cb-436d-9d24-0cf846bf2226" height="80%" width="80%" alt="Disk Sanitization Steps"/></li> 
  </ul>
</ul>
  
</p>

</br>

<h3>Adding Agents and Users</h3>

<p>
  
<ul>
  <li><b>Agents</b> (or Workers) are granted access to the help desk in osTicket to respond, resolve, and update ticket statuses.</li>
  
  <ul>
    <li>In the <b>Admin Panel</b>, go to the <b>Agents</b> tab and click <b>Add New Agent</b>.</li>
    <ul>
      <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/d666eee5-a7f7-4d08-b511-613dc0fb2dd7" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
    <li>In this tutorial, we'll create two new Agents, <b>Jane</b> and <b>John</b>. Keep a notepad ready to record login information. Set their usernames as <b>[name].doe</b> and both passwords as <b>Password1</b> for convenience (using our admin password from the installation tutorial).</li>
    <ul>
      <li>Enter the Agent's basic info and set their email address as <b>[name]@osticket.com</b>. Click <b>Set Password</b>.</li>
      <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/72d816eb-24d8-40e8-bbb6-66214c1c302d" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
      <li>Set the Agent's password to <b>Password1</b> and uncheck boxes to prevent password reset or change after login.</li>
      <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/c7b93495-c7f0-4c73-ad39-8af9586ab2b4" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
    <li>Go to the <b>Access</b> tab to set the Agent's <b>Primary Department</b> (mandatory) and optionally add <b>Extended Access</b> to access additional Departments.</li>
    <ul>
    <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/5574daff-0d82-4ce5-837e-8eaf3a858f89" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>

<li><b>Users</b> (or Customers) are creators and owners of tickets. They can track the status of their tickets using osTicket.</li>
  
  <ul>
    <li>In the <b>Agent Panel</b>, navigate to the <b>Users</b> tab and click <b>Add User</b>.</li>
    <ul>
      <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/20106b05-92f2-428e-a95e-5c2de9a36f01" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
    <li>In this tutorial, we'll create two new Users, <b>Ken</b> and <b>Karen</b>, and set up usernames, emails, and passwords similar to our Agents.</li>
    <ul>
      <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/f41712fc-39a6-41a3-a8e1-da0e86544a39" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
  </ul>
  
</ul>
  
</p>

</br>

<h3>Adding SLA Plans</h3>

<p>
  
<ul>
  <li><b>Service Level Agreements</b> or SLA Plans provide a timeframe for ticket closure. They can also be designated to specific Departments or Help Topics.</li>
  <li>In the <b>Admin Panel</b>, navigate to the <b>Manage</b> tab, then to <b>SLA</b>, and click <b>Add New SLA Plan</b>.</li>
  <ul>
    <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/01292f63-6bc8-461c-aa9a-4a591a4e8a59" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/7c800000-13a2-4854-8bd3-fd08e69bcc08" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
  <li>By default, osTicket includes the SLA Plan <b>Default SLA</b>. We will create three SLA Plans, each with its own timeframe for different ticket priorities:</li>
  <ol>
    <li>SEV-A with a <b>1 hour Grace Period, 24/7 Schedule</b>, suitable for critical business tickets</li>
    <li>SEV-B with a <b>4 hour Grace Period, 24/7 Schedule</b>, suitable for issues affecting employees</li>
    <li>SEV-C with an <b>8 hour Grace Period, business hours Schedule</b>, suitable for requests like equipment orders</li>
  </ol>
  <li>Example of creating SEV-A SLA Plan: click <b>Add Plan</b> to create the SLA Plan.</li>
  <ul>
    <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/4d287880-9b41-49c7-b43a-cf2a8fcf2536" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
</ul>
  
</p>

</br>

<h3>Configuring Help Topics</h3>

<p>
  
<ul>
  <li><b>Help Topics</b> streamline the ticket entry experience for users by helping them specify ticket info and determine the Department the ticket should go to.</li>
  <li>In the <b>Admin Panel</b>, go to the <b>Manage</b> tab and click <b>Add New Help Topic</b>.</li>
  <ul>
    <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/9613e9ed-711c-4380-89eb-524486bba51c" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
  <li>We will create four different Help Topics based on potential ticket severity, from highest to lowest priority:</li>
  <ol>
    <li>Business Critical Outage</li>
    <li>Personal Computer Issues </li>
    <li>Equipment Request</li>
    <li>Password Reset</li>
  </ol>
  <li>Example of entering credentials for the Help Topic "Equipment Request": click <b>Add Topic</b> to create the Help Topic.</li>
  <ul>
    <li><img src="https://github.com/jadeblas/post-install-config/assets/161860082/db80c223-b453-4bca-8f87-8bb191515795" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
  
</ul>
  
</p>

</br>

<h3>Further Reading and Manual</h3>
<ul>
  <li>For more information on osTicket features, refer to the official online documentation <a href= "https://docs.osticket.com/en/latest/index.html">here</a>.</li>
</ul>

<br/>
