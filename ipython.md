# Automatic session logging with iPhython

I would like to log all iPython console output so if I am onto somtyhing and I close the console, I can go back and see what I was doing.
Easily done: 
1. From Preferences, navigate to **Build, Execution, Deployment** -> Console
  * tick the *use iPython if available option*
  ![alt text](https://user-images.githubusercontent.com/24324516/27742465-a2ea7a88-5db0-11e7-8d54-c6f88406563d.png) "use iPython"

2. move to *python console*
  * add these few lines in the starting script
```
import time
logname = time.strftime('ipython-logs-%y-%m-%d--%T-logs')
%logstart -o $logname
```
![alt text](https://user-images.githubusercontent.com/24324516/27742258-df5bb8f2-5daf-11e7-912b-5ffa430d3573.png "starting script")
This will log the output of the ipython session - that's what the `-o` option is for - and save it to a file with the current timestamp, e.g. `ipython-logs-17-06-30--16:02:31`
