# postman-newman-task

## If you want to use newman on your local machine, before installing make sure that:

Node.js is installed (v 14 or higher), link:"https://nodejs.org/en/";

Git is installed (v 2.37.2), link:"https://git-scm.com/downloads";
## Clone repository
In the beginning you may clone repo by using command:
```bash
git clone https://github.com/IlyaKosts/postman-newman-task.git
```
Or you can download the archive.
## Run our tests (Using Postman)
   We have several collections here, lets devide them:
     
   Needs local test server:
     
    store.collection.json;
     
    store.postman_collection.json;
     
   No need for local test server:
     
    petstore.collection.json;
     
    petstore.postman_collection.json;
   
   First of all, in case, when we need local test server - we should install such dependency:

```bash
npm i yaml-server
```
(Yeah, we already have "node_madules" package, so it's not necesurry to run previouse command. BUT! In order to avoid any errors, I still recommend installing this dependency again.)

Then, in order to lauch our local test server, use this:
```bash
npm run tern-on-api
```
If you see any errors - then use this:
```bash
npm run start-serv
```
After that you should see in terminal something like this (mayby not 100% same but mostly):
![ Alt text](https://raw.githubusercontent.com/softchris/yaml-server/HEAD/yaml-server.png)

Then, you'll need to import one of mentioned before collections (those which needs local server), how to do that you may read here:
"https://learning.postman.com/docs/getting-started/importing-and-exporting-data/"
(Also, there will be info about how to export collections.)

Then you'll need just to choose request and run it (send). Or you can click on package and click on "Run" button - by that way you will run all test in the package (or collection).

In case, if you will choose collections, wich have no need in local server (for example: petstore.postman_collection.json) then you just import collection and go on.

## Run our tests (Using Newman)

First of all, in that case, we need to install newman:
```bash
npm install -g newman
```
To run collections (ONLY those collections, which have no need in local server), you should use such coomands in our case:
```bash
newman run etstore.postman_collection.json
```
Or (Speeking of which, you will understand here, why I didn't use this collection in pipeline):
```bash
newman run mycollection.json
```
The process should looks something like this:
![ Alt text](https://assets.postman.com/postman-docs/newman-running-in-terminal.gif)

In case, if you want to run collections which needs local server, you should:
 - Install dependency:
 ```bash
npm i yaml-server
```
 - Open second window with terminal and set the directory;
 - Launch local test server(in one of the windows):
 ```bash
npm run start-serv
```
 Or (depends on, which one will work correctly)
 ```bash
npm run tern-on-api
```
 - Run collections:
 ```bash
newman run store.collection.json
``` 
Or
```bash
newman run store.postman_collection.json
```
All information was taken from the resources: "https://learning.postman.com/docs", "https://www.npmjs.com/package/yaml-server".
