# lern-pm2
lerning pm2

## run app command

````
pm2 start app.py --name app1 --interpreter python
````

## run with 4 or max instances 

````
pm2 start app.py -i 4 --name app1 --interpreter python

pm2 start app.py -i max --name app1 --interpreter python

````

## nano processes.json

````
module.exports = {
  apps : [{
    script    : "app.js",
    instances : "max",
    exec_mode : "cluster"
  }]
}


pm2 start processes.json

````



## You can do it using PM2 with restart-delay (5 min=300000 msec):
````
$ pm2 start app.py --name covid19-5minInt restart-delay 300000
````

## Or, you can do it using PM2 with cron (5min = '*/5 * * * *'')
````
$ pm2 start app.py --name covid19-5minInt --cron '*/5 * * * *' --no-autorestart
````
