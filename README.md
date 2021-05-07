# Java-Infared-REST-API-for-Android  
  
A app that runs on your phone as a REST API server so that you can remotely access the IR blaster (on phones equipped with them).  
  
## Usage  
  
### Either through your browser or through a REST API client  
 http://your-ip-here:8080/sendIRcmd/your-ir-cmd-goes-here  
## Example  
  
### (This powers off an LG TV):   
    http://192.168.1.33:8080/sendIRcmd/340,171,21,21,21,21,21,65,21,22,21,22,21,21,21,21,21,21,21,64,21,64,21,21,21,65,21,65,21,64,21,64,21,64,21,21,21,21,21,21,21,65,21,22,21,22,21,21,21,22,21,65,21,65,21,64,21,21,21,64,21,65,21,65,21,64,21,1554,340,86,21,3677  
  
## Where to get the IR Codes  
  
1. Search for your device or a similar device by the same manufacturer on https://sourceforge.net/p/lirc-remotes/code/ci/master/tree/remotes/ and download the .conf file.  
2. Install IRScrutinizer from http://www.harctoolbox.org/IrScrutinizer.html  
3. Open IrScrutinizer and click on the import tab  
4. Use the Load File/URL to load the .conf file you've downloaded  
5. Go to the export tab   
6. Check the sendir Option  
7. Click on Export Raw Remote  
8. Now you get a filepath (Like C:\Users\username\Documents\IrScrutinizer) in the lower part of the app, open this file.  
9. The file should look something like this:  
  
```  
KEY_POWER  
0000 006D 0022 0002 0155 00A8 0017 003E 0017 003E 0017 0014 0017 0014 0017 003E 0017 003E 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 0014 0017 003E 0017 003E 0017 003E 0017 003E 0017 003E 0017 003E 0017 003E 0017 003E 0017 068B 0155 0054 0017 0E2F  
+8984 -4432 +600 -1626 +600 -1626 +600 -527 +600 -527 +600 -1626 +600 -1626 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -527 +600 -1626 +600 -1626 +600 -1626 +600 -1626 +600 -1626 +600 -1626 +600 -1626 +600 -1626 +598 -44083  
+8986 -2212 +598 -95553  
900A 006C 0000 0001 3300 00FF  
sendir,1:1,1,38000,1,69,341,168,23,62,23,62,23,20,23,20,23,62,23,62,23,20,23,20,23,20,23,20,23,20,23,20,23,20,23,20,23,20,23,20,23,20,23,20,23,20,23,20,23,20,23,20,23,20,23,20,23,62,23,62,23,62,23,62,23,62,23,62,23,62,23,62,23,1675,341,84,23,3631  
  ```  
 
10. Look at the line starting with + and - numbers and replace the + and - with commas with no spaces so it looks like this, when you add it to the URL:
```
http://192.168.1.218:8080/sendIRcmd/8984,4432,600,1626,600,1626,600,527,600,527,600,1626,600,1626,600,527,600,527,600,527,600,527,600,527,600,527,600,527,600,527,600,527,600,527,600,527,600,527,600,527,600,527,600,527,600,527,600,527,600,527,600,1626,600,1626,600,1626,600,1626,600,1626,600,1626,600,1626,600,1626,598,44083 
```  
  
## Credits  
  
Originally by https://github.com/ecs87 updated to work with newer Gradle and Android Studio and removed Samsung specific code.