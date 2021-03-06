---
title: "Remote Desired Capabilities" 
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/remote-desired-capabilities.html 
redirect_from:
    - "/display/KD/Remote+Desired+Capabilities/"
    - "/display/KD/Remote%20Desired%20Capabilities/"
    - "/x/KAzR/"
    - "/katalon-studio/docs/remote-desired-capabilities/"
description: 
---
There will be cases you need to connect and execute your tests on remote environments such as Selenium Grid and Katalium Server or cloud services such as Kobiton, SauceLabs or BrowserStacks. Katalon Studio does support this remote execution.

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/remote-desired-capabilities/Remote-desired-capabilities.png)

Please refer to some documents below as examples how to pass in desired capabilities from these providers:

1. [Kobiton](https://docs.katalon.com/katalon-studio/docs/desired-capabilities-for-kobiton-devices.html)
2. [SauceLabs](/display/KD/SauceLabs+Integration)
3. [BrowserStack](/display/KD/BrowserStack+Integration)
4. [Katalium Server](https://docs.katalon.com/katalium-server/docs/katalium-server-katalon-studio-remote-machine.html)

Note that this Remote option is applied for all executions which support this kind of remote execution, so you can apply them in this option as well.

> Code sample can be found in this project: [https://github.com/katalon-studio-samples/tips-and-tricks](https://github.com/katalon-studio-samples/tips-and-tricks)

Starting with **Katalon Studio version 6.3.0**, when Appium is set as `Remote server type`,  the **Appium Driver** option is available for you to choose between *Android Driver* and *iOS Driver*.
Then this selection is used for launching the correct Appium Driver to connect to Cloud Devices.