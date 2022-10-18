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


## File : ecosystem.config.js  `pm2 init simple`

( on windows )

ecosystem.config.js

````
module.exports = {
  apps : [{
    name   : "app1",
    script : "app.py",
    instances : 4,
    watch : true,
    interpreter : "env\\Scripts\\python.exe"
  }]
}
````

## control command

````

# Start all applications
pm2 start ecosystem.config.js

# Stop all
pm2 stop ecosystem.config.js

# Restart all
pm2 restart ecosystem.config.js

# Reload all
pm2 reload ecosystem.config.js

# Delete all
pm2 delete ecosystem.config.js
````
