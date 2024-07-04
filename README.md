# Selenium-Learnings
What is Selenium?
Selenium refers to a suite of tools that are widely used in the testing community when it comes to cross-browser testing. Selenium cannot automate desktop applications; it can only be used in browsers. It is considered to be one of the most preferred tool suites for automation testing of web applications as it provides support for popular web browsers which makes it very powerful.

It supports a number of browsers (Google Chrome 12+, Internet Explorer 7,8,9,10, Safari 5.1+, Opera 11.5, Firefox 3+) and operating systems (Windows, Mac, Linux/Unix).

Selenium also provides compatibility with different programming languages – C#, Java, JavaScript, Ruby, Python, PHP. Testers can choose which language to design test cases in, thus making Selenium highly favorable for its flexibility.

Selenium Components
The Selenium test suite comprises four main components:


![image](https://github.com/Infiniti360/Selenium-Learnings/assets/173434189/28b015cb-e1ea-4891-b8ed-ab6709f91011)

Selenium IDE
Selenium IDE (Integrated Development Environment) is primarily a record/run tool. It is an Add-on or an extension available for both Firefox and Chrome that generates tests quickly through its functionality of record and playback. You don’t need to learn any test scripting language for authoring any functional tests.

Selenium RC
In the case of working with Selenium RC (Remote Control), one must have good knowledge of at least one programming language. This tool allows you to develop responsive design tests in any scripting language of your choice. Server and client libraries are the two main components of Selenium RC. Its architecture is complex and it has its limitations.

Selenium WebDriver
Selenium WebDriver is an enhanced version of Selenium RC. It was introduced in the market to overcome the limitation faced in Selenium RC. Though it is an advanced version of RC, its architecture is completely different from that of RC. Just like Selenium RC, Selenium WebDriver too supports multiple programming platforms to provide wider flexibility and requires knowing any one programming language.

Selenium Grid
Selenium Grid is a tool that is used for concurrent execution of test cases on different browsers, machines, and operating systems simultaneously. This tool makes Cross-browser compatibility testing very easy. There are two versions of the Selenium Grid – the older version is known as Grid 1 and the recent version is known as Grid 2.

Now let’s move on to the tutorial on Selenium WebDriver.

What is Selenium WebDriver? 
Selenium WebDriver is a web framework that permits you to execute cross-browser tests. This tool is used for automating web-based application testing to verify that it performs expectedly.

Selenium WebDriver allows you to choose a programming language to create test scripts. As discussed earlier, it is an advancement over Selenium RC to overcome a few limitations. Selenium WebDriver is not capable of handling window components, but this drawback can be overcome by using tools like Sikuli, Auto IT, etc.

Selenium WebDriver Framework Architecture
WebDriver Architecture is made up of four major components:

Selenium Client library
JSON wire protocol over HTTP
Browser Drivers
Browsers

![image](https://github.com/Infiniti360/Selenium-Learnings/assets/173434189/e32bd123-6388-415b-8cd3-f811d68448b6)


Selenium Client Libraries/Language Bindings

Selenium provides support to multiple libraries such as Ruby, Python, Java, etc as language bindings have been developed by Selenium developers to provide compatibility for multiple languages. For instance, if you want to use the browser driver in Python, use the Python Bindings. You can download all the supported language bindings of your choice from the official site of Selenium.


JSON Wire Protocol

JSON is an acronym for JavaScript Object Notation. It is an open standard that provides a transport mechanism for transferring data between client and server on the web. It provides support for various data structures like arrays and objects which makes it easier to read and write data from JSON.

JSON serves as a REST (Representational State Transfer) API that exchanges information between HTTP servers. Learn more about REST API for accessing Selenium

Browser Drivers

Selenium provides drivers specific to each browser and without revealing the internal logic of browser functionality, the browser driver interacts with the respective browser by establishing a secure connection. These browser drivers are also specific to the language which is used for test case automation like C#, Python, Java, etc.

![image](https://github.com/Infiniti360/Selenium-Learnings/assets/173434189/90f64e70-0a51-423d-917e-96300400d7b6)

Browser	BrowserDriver	OS Supported
Google Chrome / Chromium	ChromeDriver	Windows/macOS/Linux
Mozilla Firefox	GeckoDriver	Windows/macOS/Linux
Microsoft Edge	Microsoft Edge WebDriver	Windows/macOS/Linux
Safari	SafariDriver (in-built)	macOS High Sierra and newer
Internet Explorer	InternetExplorerDriver	Windows

When a test script is executed with the help of WebDriver, the following tasks are performed in the background:

An HTTP request is generated and it is delivered to the browser driver for every Selenium Command
The HTTP request is received by the driver through an HTTP server
All the steps/instructions to be executed on the browser is decided by an HTTP server
The HTTP server then receives the execution status and in turn sends it back to the automation scripts

Browsers

As discussed earlier, Selenium provides support for multiple browsers like Chrome, Firefox, Safari, Internet Explorer etc.

Basic Steps in a Selenium WebDriver Script
Create a WebDriver instance.
Navigate to a webpage.
Locate a web element on the webpage via locators in selenium.
Perform one or more user actions on the element.
Preload the expected output/browser response to the action.
Run test.
Record results and compare results from them to the expected output.

Benefits and Limitations of Selenium WebDriver
Benefits of Selenium WebDriver

. It is one of the most popular Open-Source tools and is easy to get started with for testing web-based applications. 
. It also allows you to perform cross browser compatibility testing.
. Supports multiple operating systems like Windows, Mac, Linux, Unix, etc.
. It provides compatibility with a range of languages, including Python, Java, Perl, Ruby, etc.
. Provides support for modern browsers like Chrome, Firefox, Safari, and Internet Explorer.
. Selenium WebDriver completes the execution of test scripts faster when compared to other tools
. More Concise API (Application Programming interface) than Selenium RC’s
. It also provides compatibility with iPhoneDriver, HtmlUnitDriver, and AndroidDriver
. Selenium Webdriver Browser Compatibility

Limitations of Selenium WebDriver

Support for new browsers is not readily available when compared to Selenium RC
For the automatic generation of test results, it doesn’t have a built-in command
How Selenium WebDriver Works
On a high-level, Selenium WebDriver works in three steps:

Test commands are converted into an HTTP request by the JSON wire protocol.
Before executing any test cases, every browser has its own driver, which initializes the server.
The browser then starts receiving the request through its driver.
Let’s take an example with the code snippet below:

WebDriver driver = new ChromeDriver ();
driver. get (https://www.browserstack.com)
As soon as you complete writing your code, execute the program. The above code will result in the launching of the Chrome browser which will navigate to the BrowserStack website.

Now let us understand what goes behind the scene when you click on Run until the launching of the Chrome Browser.

Once the program is executed, every line of code/script will get transformed into a URL. The JSON Wire protocol over HTTP makes this possible. Then this URL is passed to the browser drivers (in our example, the ChromeDriver). At this point, our client library (Python in our example) translates the code into JSON format and interacts with the ChromeDriver.

The URL after JSON conversion looks as follows:

https://localhost:8080/{"url":https://www.browserstack.com"}
To receive the HTTP requests, every Browser Driver uses an HTTP server. Once the browser driver receives the URL, it processes the request by passing it to the real browser over HTTP. And then, all your commands in the Selenium scripts will be executed.

Types of Requests

There are two types of requests you might be familiar with – GET and POST.

If it’s a GET request then it results in a response that will be generated at the browser end and it will be sent over HTTP to the browser driver and eventually, the browser driver with the help of JSON wire protocol sends it to the UI (Eclipse IDE).

How to use Selenium WebDriver in Java: Example

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.Test;
public class LoginAutomation {
@Test
public void login() {
System.setProperty("webdriver.chrome.driver", "path of driver");
WebDriver driver=new ChromeDriver();
driver.manage().window().maximize();
driver.get("https://www.browserstack.com/users/sign_in");
WebElement username=driver.findElement(By.id("user_email_Login"));
WebElement password=driver.findElement(By.id("user_password"));
WebElement login=driver.findElement(By.name("commit"));
username.sendKeys("abc@gmail.com");
password.sendKeys("your_password");
login.click();
String actualUrl="https://live.browserstack.com/dashboard";
String expectedUrl= driver.getCurrentUrl();
Assert.assertEquals(expectedUrl,actualUrl);
}
}


The code above does the following:

Create a Selenium WebDriver instance
Configure browser if required
Navigate to the required web page and locate the relevant web element
Perform action on the web element
Verify and validate the action
Selenium is not just limited to Browser Automation but also supports different testing levels such as Regression Testing, Cross Browser Testing, UI Testing, Database Testing, Visual Testing, and Headless Browser Testing.

On executing the above java code, Selenium will navigate to the Chrome browser and open the BrowserStack login page. Then, it will log in using the relevant credentials. It will also check the test case status using Assert and try to match the URL.

