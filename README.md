🔅Create an ansible role myapache to configure Httpd WebServer.

🔅Create another ansible role myloadbalancer to configure HAProxy LB.

🔅Combine both of these roles controlling webserver versions

and solving challenge for host ip's addition dynamically over each ManagedNode in **HAProxy.cfg** file.

Create a working space for all the required files and roles

**Note : All commands are for RHEL8 Linux OS.**
```
mkdir /ws_task_15/
```

Prior to all the sub-tasks we need to declare **Role** in **ansible configuration file** 
> /etc/ansible/ansible.cfg  


##### **Sub-Task 1** : Create an ansible role myapache to configure Httpd WebServer.

**Step 1** : create a role "webserver".
```
ansible-galaxy role init webserver
```

**Step 2**: goto vars file in the role and declare the variables that we have to use in the playbook.


**Step 3** : then goto tasks file and write the code(tasks) in main.yml


**step 4** : goto files and paste the webpages that we need to deploy here


##### **Sub-Task 2** : Create another ansible role to configure HAProxy LB.

**Step 1**: create another role "haproxy" inside the same working space
```
ansible-galaxy role init haproxy
```

**Step 2** : goto vars directory and declare all the variables that we need in playbook


**Step 3** : Now goto tasks directory write down the code and "host name" in main.yml file


**Step 4** : goto templates directory and paste the "configured" haproxy configuration file.



##### **Sub-Task 3** : We need to combine both of these roles controlling webserver versions and solving challenge for host ip's addition dynamically over each Managed Node in HAProxy.cfg file."

**Step 1**: create a simple ansible-playbook (YML file) and call both the roles and the hosts.


**Step 2**: execute the playbook.

if the playbook executes successfully then

- The httpd service is running at the webserver(managed node) end.
- haproxy.cfg file at the server end will acquire the server IP dynamically.
- Webserver is Up and Active.

