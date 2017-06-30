# Automatic session logging with iPhython

I would like to log all iPython console output so if I am onto somtyhing and I close the console, I can go back and see what I was doing.
Easily done: 
1. From Preferences, navigate to **Build, Execution, Deployment** -> Console
  * tick the *use iPython if available option*
2. move to *python console*
  * add these few lines in the starting script
```
import time
logname = time.strftime('ipython-logs-%y-%m-%d--%T-logs')
%logstart -o $logname
```
This will log the output of the ipython session - that's what the `-o` option is for - and save it to a file with the current timestamp, e.g. `ipython-logs-17-06-30--16:02:31`
