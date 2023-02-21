# Katalon Studio Automation-Framework (Testbits)
Collection of informations regarding Katalon Studio Automation Framework and Tools used. You can refer more about Katalon Studio in the official [documentation](https://docs.katalon.com/docs) 


## Common Processes Template for Mobile (Test Case / Common)


### Get TAC Number
```groovy

import android.telephony.TelephonyManager

// Get a reference to the TelephonyManager
TelephonyManager telephonyManager = getSystemService(TelephonyManager.class)

// Get the TAC number
String tac = telephonyManager.getDeviceId().substring(0, 8)

// Print the TAC number
println "TAC number: " + tac

```
- First, we import the android.telephony.TelephonyManager class, which provides access to information about the telephony services on the device.
- Next, we get a reference to the TelephonyManager by calling the getSystemService method with the TelephonyManager.class argument.
- We then get the device ID by calling the getDeviceId method on the TelephonyManager. The device ID is a string that uniquely identifies the device, and the first 8 characters of the device ID represent the TAC number.
- We extract the TAC number by calling the substring method on the device ID string with the arguments 0 and 8.
- Finally, we print the TAC number using the println statement.

Note: The getDeviceId method is deprecated as of Android 10, and in some cases may return null. You can use the getImei or getMeid methods as alternatives, but note that these may also be deprecated or restricted on newer versions of Android. It's important to check the relevant Android documentation and handle any exceptions that may be thrown.

     
You can then use this template for multiple web applications by simply providing the values for url, username, and password as variables in your test case.

## Guidelines on how to use the Beginner Project Framework

## Tools Used in this Framework
1. [Katalon Studio Enterprise](https://katalon.com/katalon-studio)
2. [Jenkins](https://www.jenkins.io/)
3. [SelectorsHub](https://selectorshub.com/)
4. [GitHub](https://github.com/)
5. [Jira](https://www.atlassian.com/software/jira)
