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
echo '{' >> config.development.json
echo '  "server": {' >> config.development.json
echo '    "host": "0.0.0.0",' >> config.development.json
echo '    "port": 3000' >> config.development.json
echo '  },' >> config.development.json
echo '  "cluster": false,' >> config.development.json
echo '    "api": {' >> config.development.json
echo '    "host": "127.0.0.1",' >> config.development.json
echo '    "port": 3000' >> config.development.json
echo '  }' >> config.development.json
echo '}' >> config.development.json
cp ./config.development.json ./config.production.json




```

```JSon
{
  "server": {
    "host": "localhost",
    "port": 3000
  },
  "cluster": false,
    "api": {
    "host": "127.0.0.1",
    "port": 3000
  }
}
```



* Sur la configuration : https://docs.dadi.cloud/web/6.1#configuration

