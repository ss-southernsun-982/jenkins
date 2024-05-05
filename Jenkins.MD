## Setup jenkins server

Note: using **ngrok** to public host because git hub webhook only access public domain. If you use localhost:8080, you can not triiger any commit from git hub

**Step1:**

Install plugin:

1. Docker
2. Docker pipeline
3. Github integration

**Step2:**

Config git hub server

Manager jenkins -> System -> Find Github server

* Name: type name do you want
* API url using default
* Credentials key: add your serect key token in github

Config node server:

Manager jenkins -> Nodes

Click Build-In-Node change label to **master**

**Step3:**

Add new credential docker
