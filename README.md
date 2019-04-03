# dadi-cms

A try out of dadi api scalable CMS headless https://github.com/dadi/api https://github.com/dadi/web

* https://docs.dadi.cloud/api/4.4#creating-an-api
* https://www.npmjs.com/package/@dadi/api
* https://www.npmjs.com/package/@dadi/web


Tests it on https://www.katacoda.com/courses/nodejs/playground 


## dadi-api

* En utilisant `dadi-cli` : 

```JavaScript
npm install @dadi/cli -g

# mkdir my-api
cd my-api
dadi api new my-api
cd my-api
```

* En incluant `dadi-api` dans une application `NodeJS` existante : 

```JavaScript
export SSH_URI_OF_NODE_APP_GIT_REPO=ccc
mkdir myproject/
cd myrpoject/
git clone $SSH_URI_OF_NODE_APP_GIT_REPO .
npm install --save @dadi/api
```

## dadi-web

* En incluant `dadi-web` dans une application `NodeJS` existante : 

```JavaScript
export SSH_URI_OF_NODE_APP_GIT_REPO=ccc
mkdir myproject/
cd myrpoject/
git clone $SSH_URI_OF_NODE_APP_GIT_REPO .

npm install --save @dadi/api

npm install --save @dadi/web

npm start
``` 
