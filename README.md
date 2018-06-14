# DevOps And Automation Tech Stack
This repository notes the technology stack of my experience as a DevOps and Automation Architect. It was created on 2018 May 28th and only content table was there at the beginning. But I will gradually update and complete valuable notes and links.

* [Test Automation](https://github.com/lannyzhujin/DevOps_And_Automation_Tech_Stack#test_automation)
    * Framework
        * RobotFramework
        * Cucumber
        * Junit
        * TestNG
    * API Automation
        * SoapUI
    * Unit Test
    * Code static scan
        * SonarQube
        * ESLint
    * Web UI Automation
        * Selenium / WebDriver
        * Chromium
        * Puppeteer
    * Mobile
        * Appium
    * Android 
        * Simulator
    * iOS
        * Xcode

* [Infrastructure Automation](https://github.com/lannyzhujin/DevOps_And_Automation_Tech_Stack#infrastructure-automation)
    * Ansible
    * Terraform

* [CI/CD](https://github.com/lannyzhujin/DevOps_And_Automation_Tech_Stack#cicd)
    * Jenkins
    * Ubran Code
    * Visual Studio Team Services

* [Container](https://github.com/lannyzhujin/DevOps_And_Automation_Tech_Stack#container)
    * Docker
    * Kubernetes

* [Cloud](https://github.com/lannyzhujin/DevOps_And_Automation_Tech_Stack#cloud)
    * AWS
    * Azure
    * PolyCloud

* [Frontend](https://github.com/lannyzhujin/DevOps_And_Automation_Tech_Stack#frontend)
    * jQuery
    * React
    * Broswser
         * Layout Engine
         * XPath
         * DevTool Protocol

* [Program Language](https://github.com/lannyzhujin/DevOps_And_Automation_Tech_Stack#program-language)
    * Java
    * Python
    * JavaScript
    * Bash Shell
    * Windows Batch/Power Shell

* [Security Test](https://github.com/lannyzhujin/DevOps_And_Automation_Tech_Stack#security-test)
    * OWASP
       * XSS
    * Kali Linux
    * Burp
    

# Test_Automation
##  Framework
### RobotFramework
[RobotFramework resource file](https://github.com/lannyzhujin/RobotFramework_Cheat_sheet) is created for generic web page automation. It extends the selenium keywords such as "Open Chrome Headless" and "Wait Exists And Click Element".

[Salesforce DEMO](https://github.com/lannyzhujin/SFDC_Automation) is created for demostrating the selenium and appium automation UItest capability.

Run RobotFramework on Python API level
```
#-*- coding:utf-8 -*-

from robot.api import TestSuite
from robot.api import ResultWriter    
if __name__ == "__main__":    
	# Creat your Suite
	suite = TestSuite("Google search your keyword")        
	
	# import SeleniumLibrary
	suite.resource.imports.library("SeleniumLibrary")        
	
	# Create test：Open Chrome Browser
	test_01 = suite.tests.create("Open Chrome Browser")
	test_01.keywords.create("Open Browser", 
			args=["http://www.google.com", "Chrome"])
	test_01.keywords.create("Title Should Be", 
			args=["Google"])        

	test_02 = suite.tests.create("Google Search")
	test_02.keywords.create("Input Text", 
			args=["id=lst-ib", "Trump Kim"])
	test_02.keywords.create("Click Button", args=["//input[@name='btnK']"])
	test_02.keywords.create("Sleep", args=["5s"])        
			
	test_03 = suite.tests.create("Result Assertion")
	test_03.keywords.create("Title Should Be", 
			args=["Trump Kim - Google Search"])        
			
	test_04 = suite.tests.create("Complete Search")
	test_04.keywords.create("Close All Browsers")        
	
	# Run your test here
	result = suite.run(critical="Google Search", output="output.xml")        
	
	# Reporting
	ResultWriter(result).write_results(report="report.html", 
			log="log.html")
```

### Cucumber
[One Cucumber](https://github.com/lannyzhujin/OneCucumber) is an automation test framework for APPs developed by PhoneGap. ONE Cucumber gherkin script will work on both of your iOS and Android APPs, so it is named as "OneCucumber". Only deploy and tested under MAC OSX.

### Junit
### TestNG

## API_Automation
### SoapUI

## Unit Test

## Code static scan
### SonarQube
### ESLint

## Web UI Automation
### Selenium / WebDriver
Add browser console reading interface for robotframework [selenium2library](https://github.com/lannyzhujin/Selenium2Library)
### Chromium
### Puppeteer

## Mobile
### Appium
Extend robotframework [appliumlibrary](https://github.com/serhatbolsu/robotframework-appiumlibrary) keywords of "is_visible", "wait_until_element_is_visible" and "check_visibility".

## Android 
### Simulator

## iOS
### Xcode

# Infrastructure Automation
## Ansible
## Terraform

# CI/CD
## Jenkins

## Ubran Code

## Visual Studio Team Services

# Container
## Docker

## Kubernetes

# Cloud
## AWS

## Azure

## PolyCloud

# Frontend
## jQuery

## React

## Broswser
### Layout Engine
 Engine    |    License    |   Embeded in 
-----------|---------------|--------------
Gecko | Mozilla Public | Firefox
Blink | GNU LGPL, BSD-style | Chrome, Chromium, Opera
EdgeHTML | Proprietary | Microsoft Edge
WebKit | GNU LGPL, BSD-style  |  Safari 
Trident | Proprietary | Internet Explorer

Please see the [List of web browsers](https://en.wikipedia.org/wiki/List_of_web_browsers) for full engine list and [Comparison of browser engines](https://en.wikipedia.org/wiki/Comparison_of_browser_engines) for browser marketshare.

### XPath
### DevTool Protocol

# Program Language
## Java

## Python
Class variable scope
```
class Animal(object):
  """Makes cute animals."""
  is_alive = True
  def __init__(self, name, age):
    self.name = name
    self.age = age

zebra = Animal("Jeffrey", 2)
giraffe = Animal("Bruce", 1)
zebra.is_alive = False

print zebra.name, zebra.age, zebra.is_alive
#Jeffrey 2 False

print giraffe.name, giraffe.age, giraffe.is_alive
#Bruce 1 True
```

Class Inheritage and method overwrite
```
class Employee(object):
  """Models real-life employees!"""
  def __init__(self, employee_name):
    self.employee_name = employee_name

  def calculate_wage(self, hours):
    self.hours = hours
    return hours * 20.00

# Add your code below!
class PartTimeEmployee(Employee):
  def calculate_wage(self, hours):
    self.hours = hours
    return hours*12
  
  def full_time_wage(self, hours):
    return super(PartTimeEmployee, self).calculate_wage(hours)
  
Robbin = PartTimeEmployee("Robbin")
print Robbin.full_time_wage(3)
```


## JavaScript

## Bash Shell

## Windows Batch/Power Shell

# Security Test
## OWASP
### XSS

## Kali Linux

## Burp
    

