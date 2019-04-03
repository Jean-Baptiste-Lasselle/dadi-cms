# dadi-cms

A try out of dadi api scalable CMS headless https://github.com/dadi/api https://github.com/dadi/web

* https://docs.dadi.cloud/web
* https://docs.dadi.cloud/api
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

# some config whatever itis,to connect it to dadi/api instance
npm install --save @dadi/web

npm start
``` 


* Mais je préfère utiliser dadi-cli pour générer l'application web avcec le layout standard conçut par l'équipe `dadi.cloud` : 


```JavaScript
npm install @dadi/cli -g

dadi web new unprojetparticulier
cd unprojetparticulier
cp ./config/config.development.json ./config/config.development.generated.json
rm -f ./config/config.development.json
echo '{' >> ./config/config.development.json
echo '  "server": {' >> ./config/config.development.json
echo '    "host": "0.0.0.0",' >> ./config/config.development.json
echo '    "port": 3000' >> ./config/config.development.json
echo '  },' >> ./config/config.development.json
echo '  "cluster": false,' >> ./config/config.development.json
echo '    "api": {' >> ./config/config.development.json
echo '    "host": "127.0.0.1",' >> ./config/config.development.json
echo '    "port": 3000' >> ./config/config.development.json
echo '  }' >> ./config/config.development.json
echo '}' >> ./config/config.development.json
cp ./config/config.development.json ./config/config.production.json

```

* Well here you go with a resonable config starter : 

```JSon
{
  "app": {
    "name": "Mon Projet Fort Particulier"
  },
  "global" : {
    "baseUrl": "http://de.particulier.fr"
  },
  "server": {
    "host": "0.0.0.0",
    "port": 3000
  },
  "cluster": false,
    "api": { /* But what you want, is to split api and web into two separate containers, which will scale up as micro-services */ 
    "enabled": false,
    "host": "0.0.0.0",
    "port": 3001
  }
}
```



* Sur la configuration : https://docs.dadi.cloud/web/6.1#configuration


Première impressions : woua ça marche bien dis donc... super architecure, tooling... ça sent le gagnant.

