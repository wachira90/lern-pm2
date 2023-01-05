# set log path

##  pm2.json

````
{
  "apps": [{
    "name": "app",
    "script": "./index.js",
    "error_file": "/var/log/app/error.log",
    "out_file": "/var/log/app/out.log"
  }]
}
````
