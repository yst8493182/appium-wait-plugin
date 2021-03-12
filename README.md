# appium-wait-plugin

This is an Appium plugin designed to wait for element to be present.

## Prerequisite

Appium version 2.0

## Installation - Server

Install the plugin using Appium's plugin CLI, either as a named plugin or via NPM:

```
appium plugin install element-wait
appium plugin install --source=npm appium-element-wait
```

## Installation - Client

No special action is needed to make things work on the client side. Just keep sending in your unprefixed caps!

## Activation

The plugin will not be active unless turned on when invoking the Appium server:

```
appium --plugins=element-wait
```

### Example


Before wait-plugin 

```
wait = new WebDriverWait(driver, 30);
wait.until(presenceOfElementLocated(MobileBy.AccessibilityId("login"))).click();
wait.until(presenceOfElementLocated(MobileBy.AccessibilityId("slider1")));
driver.findElementByAccessibilityId("slider1").click();
WebElement slider = wait.until(presenceOfElementLocated(MobileBy.AccessibilityId("slider")));
WebElement slider1 = wait.until(presenceOfElementLocated(MobileBy.AccessibilityId("slider1")));
```


After wait-plugin 

```
driver.findElementByAccessibilityId("login").click();
driver.findElementByAccessibilityId("slider1").click();
driver.findElementByAccessibilityId("login").sendKeys('Hello');
```
