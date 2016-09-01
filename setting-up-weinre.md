####Steps to set up weinre

######To install, 
```npm install -g weinre```

1. To run, 
```weinre --boundHost 192.168.1.2 --httpPort 8080```
Where, 192.168.1.2 is your host IP and 8080 is port where you want to run weinre.

2. Add the below snippet in index.html of your app,
```<script src="http://192.168.1.2:8080/target/target-script-min.js"></script>```
Where, 192.168.1.2 is your host IP and 8080 is port where you want to run weinre.

3. Run the application on target device and open this url in browser, ```http://192.168.1.2:8080```
