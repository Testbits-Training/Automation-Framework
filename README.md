# Katalon Studio Automation-Framework (Testbits)
Collection of informations regarding Katalon Studio Automation Framework and Tools used. You can refer more about Katalon Studio in the official [documentation](https://docs.katalon.com/docs) 

## Hybrid Test Automation Framework (Katalon Studio)
<img width="951" alt="Picture1" src="https://user-images.githubusercontent.com/120165538/211730216-4ac34e1a-b965-46c0-bc48-f89ff9cbd119.png">

Enterprises find it hard to boost their testing teams' speed without compromising product quality. Built on the hybrid test automation framework, the Katalon Testing Platform offers testing professionals the complete set of testing solutions to test software and applications. 
With the purpose of removing the need to build frameworks and reinvent the wheel using open-source libraries, the Katalon Testing Platform brings the community:

| Hybrid Test Automation Framework    | <p style="text-align:center">Description<p>         |
| -------------------------           | ----------- |
| Page-Object Model Design           |  Reuse and recycle all created test objects, profiles and cases       |
| Record-and-Playback Testing         | Capture, view object properties and generate tests based on every action taken on the System Under Test    |
| Keyword-Driven Testing              | Jam-packed library of built-in keywords to 2x the speed of designing test steps and actions |
| Data Driven Testing                 | Test against a combination of CSV/Excel files, internal databases and external databases ( Oracle SQL, SQL Server or databases with JDBC drivers)      |

You can read more in this [resource](https://katalon.com/resources-center/blog/test-automation-framework) by Katalon

## KS Beginner Project Framework
### Project Structure
```
- Profiles
- Test Cases
    - Common
- Object Repository
- Test Suites
- Data Files
- Checkpoints
- Keywords
    - (default package)
- Test Listeners
- Reports
- TestOps
    - Test Runs
    - Test Run Types
    - Releases
- Include
    - config
        - log.properties
    - features
    - scripts
        - groovy
            - (default package)
```


## Common Processes Template (Test Case / Common)
### Login Template
```groovy
import static com.kms.katalon.core.testobject.ObjectRepository.findTestObject
import com.kms.katalon.core.webui.keyword.WebUiBuiltInKeywords as WebUI
import com.kms.katalon.core.model.FailureHandling as FailureHandling

WebUI.openBrowser('${url}')
WebUI.maximizeWindow()

WebUI.navigateToUrl('${url}')

WebUI.setText(findTestObject('Object Repository/Page_Login/txt_Username'), '${username}')
WebUI.setText(findTestObject('Object Repository/Page_Login/txt_Password'), '${password}')
WebUI.click(findTestObject('Object Repository/Page_Login/btn_Login'))

WebUI.verifyElementPresent(findTestObject('Object Repository/Page_Home/welcome_message'), FailureHandling.CONTINUE_ON_FAILURE)

WebUI.closeBrowser()
```

This template assumes that you have already defined the following test objects in your Object Repository:

- txt_Username: a text field for entering the username
- txt_Password: a text field for entering the password
- btn_Login: a button for submitting the login form
- welcome_message: an element that is present on the homepage and serves as a verification that the login was successful

### Upload Template
```groovy

import static com.kms.katalon.core.testobject.ObjectRepository.findTestObject
import com.kms.katalon.core.webui.keyword.WebUiBuiltInKeywords as WebUI
import com.kms.katalon.core.model.FailureHandling as FailureHandling

WebUI.openBrowser('${url}')
WebUI.maximizeWindow()

WebUI.navigateToUrl('${url}')

WebUI.uploadFile(findTestObject('Object Repository/Page_Register/input_file'), 'C:\\Folder\\file.txt')

WebUI.closeBrowser()
```
- input_file: a text field for uploading the file
- C:\\Folder\\file.txt: Name of file that want to uapload include its directory
    
### Download Template
```groovy

import static com.kms.katalon.core.testobject.ObjectRepository.findTestObject
import com.kms.katalon.core.webui.keyword.WebUiBuiltInKeywords as WebUI
import com.kms.katalon.core.model.FailureHandling as FailureHandling

WebUI.openBrowser('${url}')
WebUI.maximizeWindow()

WebUI.navigateToUrl('${url}')

WebUI.downloadFile(findTestObject('Object Repository/Page_Dwonload/download_file'), 'path/to/downloads')

WebUI.verifyDownloadedFile('Object Repository/Page_Dwonload/download_file', 'path/to/downloads', 'file.txt', 'text/plain')

WebUI.closeBrowser()
```
    
- download_file: URL for uploading the file
- path/to/downloads: Location of directory to store downloading file
     
You can then use this template for multiple web applications by simply providing the values for url, username, and password as variables in your test case.

## Guidelines on how to use the Beginner Project Framework

## Tools Used in this Framework
1. [Katalon Studio Enterprise](https://katalon.com/katalon-studio)
2. [Jenkins](https://www.jenkins.io/)
3. [SelectorsHub](https://selectorshub.com/)
4. [GitHub](https://github.com/)
5. [Jira](https://www.atlassian.com/software/jira)
