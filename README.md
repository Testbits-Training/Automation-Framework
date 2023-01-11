# Katalon Studio Automation-Framework (Testbits)
Collection of informations regarding Katalon Studio Automation Framework and Tools used. You can refer more about Katalon Studio in the official [documentation](https://docs.katalon.com/docs) 

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

You can then use this template for multiple web applications by simply providing the values for url, username, and password as variables in your test case.

## Guidelines on how to use the Beginner Project Framework

## Tools Used in this Framework
1. [Katalon Studio Enterprise](https://katalon.com/katalon-studio)
2. [Jenkins](https://www.jenkins.io/)
3. [SelectorsHub](https://selectorshub.com/)
4. [GitHub](https://github.com/)
5. [Jira](https://www.atlassian.com/software/jira)
