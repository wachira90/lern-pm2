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

## nano process.json

````
module.exports = {
  apps : [{
    script    : "app.js",
    instances : "max",
    exec_mode : "cluster"
  }]
}
````
