Selenium Commands every Developer or Tester must know

Selenium is indisputably one of the most preferred tools when it comes to test automation for any software. It is widely used for functional testing and cross browser testing of websites. It is very popular among the QAs because Selenium WebDriver is compatible with leading programming languages like Python, Java, Ruby to facilitate browser automation of popular browsers like Chrome, Firefox, Edge, etc. This means that QAs can quickly write Selenium test cases in their preferred language.

Besides being flexible in terms of programming language, Selenium framework also has firm community support from contributors across the world.

Being proficient in Selenium is a necessity for any QA who intends to run frequent and extensive automated tests. For this purpose, it is essential to master the specific basic Selenium commands and methods. These commands are simple functions or methods defined in several object-oriented programming languages.

This article aims at highlighting basic Selenium commands that are used to perform actions on a web browser.

Navigational Selenium Commands
Listed below are the basic Navigation commands in Selenium that one should be aware of.

1. Navigate To Commands
To navigate to a particular webpage URL, one can use either of the following commands:

Using get method

driver.get (“https://www.browserstack.com”) ;
Using the navigate method

driver.navigate().to("https://www.browserstack.com/selenium");
2. Forward Command

The forward command navigates the browser forward by one page recorded in the browsing history.

driver.navigate().forward();
3. Back Command

The back command instructs the browser to redirect to the immediate previous webpage.

driver.navigate().back();
4. The Refresh Command

The Refresh command instructs the browser to reload or refresh the current web page.

driver.navigate().refresh();

Selenium Commands to search for specific Web Elements
For QAs to automate tests for a specific web page, it’s vital for scripts to identify the right elements on a web page to interact with. To identify specific elements on a web page, QAs can use the findElement() in Selenium command. It can be implemented with the following syntax:

WebDriver driver = driver.findElement (By.id(“text-box”));
The above method returns the specific web element that has text-box as a value of the id attribute. Additionally, there are multiple locators in Selenium that can be used to locate specific elements on a web page. Their function is similar to the “id locator” used in the code snippet above. These locators are as follows:

By.id
By.Name
By.CSS Selectors
By.classname
By.Link Text
By.PartialLinktext
Read More about locators in Selenium

Commands to handle frames in Selenium Webdriver
Frames in HTML can be used to divide a web-page vertically or horizontally. It is mainly used for displaying external content on a target web page, for example, an advertisement for any online programming course on a web page. To interact with any web element present within any frame, one needs to switch to that particular frame. This allows the user to identify elements present on that page and write tests accordingly.

QAs can switch between frames using the Switch.frame() function. The switch function can be implemented using three different locators: By.index, By.id, By WebElement. Refer to the commands below:

By Index
driver.switchTo().frame(1);
Switches to the frame with index number 1

By Id
driver.switchTo().frame(“resultframe”);
Switches the frame where the value of id attribute is resultframe

By Web Element
WebElement iframeElement = driver.findElement(By.id("resultframe"));
driver.switchTo().frame(iframeElement);
The WebElement command above identifies the web element and then passes it through the iframe element object.

Basic Get commands used in the Browser
Get commands or methods help QAs or developers to fetch specific parameters on the target webpage to be tested. Let’s quickly go through some basic Get commands in Selenium.

getCurrentUrl() – This command returns the URL of the currently active web page in the browser.
getPageSource() – This command helps in getting the entire HTML source code of the open web page.
getTitle() – This command can be used for displaying the title of the current web page.

Wait commands in Selenium
Wait commands in Selenium enable the QAs to pause the execution of test cases for a specified length time. These commands help in observing and troubleshooting errors that may arise due to time variations or any lags.

Implicit wait commands: These commands instruct the WebDriver to wait for a specified time before throwing an exception. Refer to the command below.
driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
Explicit wait commands: These commands instruct the WebDriver to wait until a particular condition occurs before executing further scripts.
WebDriverWait wait = new WebDriverWait(driver,30);

What is a Selenium WebElement?
A WebElement, in this case, a WebElement in Selenium is essentially an HTML element on a website. HTML documents consist of HTML elements. Each HTML element consists of a start tag and an end tag. The content lies between the tags.

Syntax

<start tag> content </end tag>

HTML elements can contain other elements. Every HTML document carries such HTML elements.
WebElement Selenium WebDriver methods apply to almost all DOM elements on a web page.
Each WebElement is represented in Selenium via the WebElement interface – which is used by Selenium to interact with visible and invisible elements on the web page.
Every Selenium WebDriver method either returns a value or returns null/void (AKA no value). The WebElement class in Selenium WebDriver works the same way.

Here’s an example of a WebElement in Selenium command:

WebElement element = driver.findElement(By.id(“UserName“));
This command returns either the element being searched for or returns null/void.

All actions on any WebElement will always populate against any element, regardless of whether an action is valid on the element or not.

List of Selenium WebElement Commands
1. sendKeys() command
sendKeys command allows the user to type content automatically into an editable field while executing tests. These fields are web elements that can be identified using locators like element id, name, class name, etc.

Syntax:

element.sendKeys(“text”);

This method uses CharSequence as a parameter. It returns nothing. It works with text entry elements such as INPUT and TEXTAREA.

Code:

// Create WebElement
WebElement elesendKeys = driver.findElement(By.id("TextBox"));
// Perform sendKeys operation
elesendKeys.sendKeys("Cheese");
// OR
// Send value to particular WebElement e.g: Textbox.
driver.findElement(By.id("TextBox")).sendKeys("Cheese");
Read More: Quick XPath Locators Cheat Sheet

2. isDisplayed() command
The isDisplayed command in Selenium verifies if a particular element is present and displayed. If the element is displayed, then the value returned is true. If not, then the value returned is a NoSuchElementFound exception.

Syntax:

element.isDisplayed();

The code below verifies if an element with the id attribute value next is displayed.

boolean eleSelected= driver.findElement(By.xpath("xpath")).isDisplayed();

Full code:

WebElement element = driver.findElement(By.id("UserName"));
boolean status = element.isDisplayed();
//Or can be written as
boolean status = driver.findElement(By.id("UserName")).isDisplayed();
Note: If an element is present on a web page but its property is set to hidden, the Selenium WebDriver isDisplayed method will return NoSuchElementFound. This is because even though the element is present in the DOM, it is not visible to users.

3. isSelected() command
This command only works on input elements such as radio buttons, checkboxes, select options, and menu items. It is used to determine if an element is selected. If the specified element is selected, the value returned is true. If not, the value returned is false.

Syntax:

element.isSelected();

Code:

WebElement element = driver.findElement(By.id("Sex-Male"));
boolean status = element.isSelected();
//Or can be written as
boolean staus = driver.findElement(By.id("Sex-Male")).isSelected();
4. submit() command
This command is handy when interacting with forms (or elements within a form) on a web page. It doesn’t require a parameter and returns nothing.

As evident from its name, the command submits relevant information (as required) on a website. If the action triggered by this command changes the current web page, the method will wait until the new page loads.

Syntax:

element.submit();

Code:

WebElement element = driver.findElement(By.id("SubmitButton"));
element.submit();
//Or can be written as
driver.findElement(By.id("SubmitButton")).submit();
WebElement element = driver.findElement(By.id("SubmitButton"));
element.submit();
//Or can be written as
driver.findElement(By.id("SubmitButton")).submit();
Also Read: Selenium Commands every Developer or Tester must know

5. isEnabled() command
This WebElement in Selenium command verifies if an element is enabled on the web page. If the element is enabled, it returns a true value. If not, it returns a false value.

Syntax:

element.isEnabled();

The code below verifies if an element with the id attribute value next is enabled.

boolean eleEnabled= driver.findElement(By.xpath(“xpath”)).isEnabled();

Full Code:

// Create WebElement
WebElement eleEnabled = driver.findElement(By.id("TextBox"));
// Perform isEnabled operation
eleEnabled.isEnabled();
// OR
// Verify WebElement is Enabled or Not? e.g: Radio / Checkbox.
driver.findElement(By.id("Text")).isEnabled();
6. getLocation() command
This command retrieves the location of a specified element on a web page. It does not require a parameter and returns the Point object as its result. The X and Y coordinates of the element can be derived from the Point object returned.

Syntax:

element.getLocation();

Code:

WebElement element = driver.findElement(By.id("SubmitButton"));
Point point = element.getLocation();
System.out.println("X cordinate : " + point.x + "Y cordinate: " + point.y);
7. clear( ) command
When using this WebElement in Selenium command, its value will be cleared if the element in question is a text entry. It doesn’t require a parameter and returns nothing.

Syntax:

element.clear();

The clear() method does not affect other web elements. The text entry elements here are INPUT and TEXTAREA.

Code:

// Create WebElement
WebElement eleClear = driver.findElement(By.id("TextBox")); 
// Perform clear operation
eleClear.clear();
// OR
// Clear particular WebElement e.g: Textbox.
driver.findElement(By.id("TextBox")).clear();

8. getText() command
This command retrieves the text within a specific web element. This includes the inner text as well as the sub-elements sans whitespace. It doesn’t require a parameter and returns a string value. This method is often used to verify labels, messages, error, and other elements (involving text) displayed to website visitors.

Syntax:

element.getText();

Code:

// Create WebElement
WebElement elegetText = driver.findElement(By.id("TextBox"));
// Perform getText operation
elegetText.getText();
// OR
// Get text of Particular WebElement &amp; Store into String
driver.findElement(By.id("TextBox")).getText();

9. getTagName() command
This method retrieves the tag name of the specified element. It does not require a parameter and returns a string value as its result.

Syntax:

element.getTagName();

This command does not return the value of the name attribute. It returns the tag. For example, if the code is <input name=”foo”/>, then this command will return the tag, i.e. “input”.

Code:

// Create WebElement
WebElement elegetTagName = driver.findElement(By.id("TextBox"));
// Perform getTagName operation
elegetTagName.getTagName();
// OR
// Able to get TagName of Particular WebElement &amp; Store into String
driver.findElement(By.id("TextBox")).getTagName();
// Create WebElement
WebElement elegetTagName = driver.findElement(By.id("TextBox"));
// Perform getTagName operation
elegetTagName.getTagName();
// OR
// Able to get TagName of Particular WebElement &amp; Store into String
driver.findElement(By.id("TextBox")).getTagName();

10. getCssValue() command
This command retrieves the CSS property value of a specified element. It does not require a parameter and returns a string value as its result.

Syntax:

element.getCssValue();

Color values must be returned as rgba strings. For example, if the “background-color” property is set as “green” in the HTML source, the value returned by the command will be “rgba(0, 255, 0, 1)”.
Shorthand CSS properties (e.g. font, background, border, margin, border-top, margin-top, padding, padding-top, outline, list-style, pause, cue) are not returned, as required with DOM CSS2 specifications. Access the longhand properties directly in order to access the desired values.
Code:

//Locating textBox element using CSS Selector
WebElement textBox = driver.findElement(By.cssSelector("div#textBox "));

//Performing sendKeys operation on the element
textBox.sendKeys("stqatools");

11. getAttribute() command
This command retrieves the attribute value of a specified element. It uses String as the parameter and returns a string value as its result.

Syntax:

element.getAttribute();

Code:

WebElement element = driver.findElement(By.id("SubmitButton"));
String attValue = element.getAttribute("id"); //This will return "SubmitButton"
12. click() command
The click() command lets the tester replicate the click action on a button, link, radio button or checkbox. In Webdriver, the click occurs after the element is found. In Selenium IDE, the recorder identifies the element, the command itself performs the click.

Syntax:

element.click();

Code:

// Create WebElement
WebElement eleclick = driver.findElement(By.id("TextBox"));
// Perform click operation
eleclick.click();
// OR
// Click on any WebElement e.g: Button.
driver.findElement(By.id("Button_Id")).click();
// Create WebElement
WebElement eleclick = driver.findElement(By.id("TextBox"));
// Perform click operation
eleclick.click();
// OR
// Click on any WebElement e.g: Button.
driver.findElement(By.id("Button_Id")).click();

13. getSize() command
This command retrieves the height and width of a specific rendered element. It does not require a parameter and returns the Dimension object as its result.

Syntax:

element.getSize();

Code:

WebElement element = driver.findElement(By.id("SubmitButton"));
Dimension dimensions = element.getSize();
System.out.println(“Height :” + dimensions.height + ”Width : "+ dimensions.width);

Locators in Selenium: A Detailed Guide

Over the past decade, Selenium has become the most popular option for developers to run automation tests for web applications. The Selenium suite has excellent flexibility — it allows teams to run the tests on a local machine or the cloud, interfacing through many commonly used programming languages. While there are a set of challenges in Selenium, the flexibility that it provides makes it the best testing framework to adopt.

In this post, let’s learn about different Locators in Selenium – ID, XPath, Name, DOM, Link, Tag & more that enables testers to select and act on an HTML DOM element.

What are Locators in Selenium?
Our guide to getting started with the Selenium framework with Python briefly described locators in Selenium. The broad steps to perform a test through Selenium are as follows –

Download browser drivers
Initiate a Selenium WebDriver
Load web applications
Perform designated actions in a defined test
Assess if the test achieved the desired outcome
Close the WebDriver
Locators in Selenium come into action in the fourth step above after the Selenium WebDriver is initialized and loaded the webpage to be tested. A locator enables testers to select an HTML DOM element to act on. This post examines the top 8 locators in Selenium WebDriver.

Knowing how to use different locators correctly is key to building better automation scripts. If the test script is not able to identify which element it needs to interact with, the test will fail before it can begin.

Different Types of Locators in Selenium
Here’s a snapshot overview of top 8 locators in Selenium:

By CSS ID: find_element_by_id
By CSS class name: find_element_by_class_name
By name attribute: find_element_by_name
By DOM structure or Xpath: find_element_by_xpath
by tagName: find_element_by_tag_name()
By link text: find_element_by_link_text
By partial link text: find_element_by_partial_link_text
By HTML tag name: find_element_by_tag_name
While all these locators return single elements, one may use the .find_elements() method to find multiple elements. Let’s further explore the different types of locators in Selenium and how to use them.

Locate Elements by CSS ID
This is by far the simplest method of locating an element. The CSS ID, stored in the id attribute of an HTML DOM element, is unique for every element in the page by design. Thus, an ID can uniquely identify an element.

To use this feature, one needs to call the .find_element_by_id() method of the webdriver class. Here is the usage for it.

from selenium import webdriver

driver = webdriver.Chrome('./chromedriver')
driver.get("https://www.python.org")

search_bar = driver.find_element_by_id("id-search-field")
If there is no DOM element with the ID that one is searching for, a NoSuchElementException is raised, which one can account for, by using a try-catch block.

Theoretically, every DOM element on a page should have a unique ID. However, in real life, one does not commonly observe this. Most elements may not have an ID or encounter two elements with the same ID. In such cases, one needs to use a different strategy to identify a DOM element uniquely.

Locate Elements by CSS Class
A second strategy for locating elements on a page is to search by the class name. The class name is stored in the class attribute of an HTML tag. By design, a CSS class applies to a group of DOM elements. The .find_element_by_class_name() method only returns the first element with the matching class. It raises a NoSuchElementException if no element exists with the given class name. Here is how to use the method in the driver.

from selenium import webdriver

driver = webdriver.Chrome('./chromedriver')
driver.get("https://www.python.org")

# Returns first element with matching class
first_search_bar = driver.find_element_by_class_name("id-class-name")
Locate Elements by Name
In HTML5, form elements often have a name attribute associated with them. The .find_element_by_name() method only returns the first element with the matching class. If multiple elements of the same name exist, the first matched element will be returned. No matching elements result in a NoSuchElementException error.

Consider the following form:

<form id="loginForm">
<input name="name" type="text" value="First Name" />
<input name="name" type="text" value="Last Name" />
<input name="email" type="text" value="Business Email" />
<input name="password" type="password" />
<input name="continue" type="submit" value="Sign Me Up" />
</form>
The following code returns the email form element.

email_input = driver.find_element_by_name("email")
However, the following code only returns the first name form element.

name_input = driver.find_element_by_name("name")
Using the .find_element_by_name() method, it is impossible to get to the last name input form field in the example. This brings us to the next locator.

Locate Elements by XPath
If one has failed to identify an element by ID, class, or name, one would need to locate the element through its XML path. This process may also be implemented while reading an XML document. In this tutorial, we explore the use of relative paths, as absolute paths are prone to errors with the slightest change in the HTML structure.

We will use the .find_element_by_xpath() method to locate an appropriate element in the document. The argument that the .find_element_by_xpath() method takes is the path to the element.

To find the email input field in the above HTML form example, use the following code:

email_input = driver.find_element_by_xpath("//form[input/@name='email']")
This code snippet searches for the first form element of the page. Within this form, it searches for input with the name, which equals the value email, thus narrowing down to the required element.

Next, let us try to locate the form’s first and last names input element above.

first_name = driver.find_element_by_xpath("//form[@id='loginForm']/input[1]")
last_name = driver.find_element_by_xpath("//form[@id='loginForm']/input[2]")
The method first searches for a form with the ID login form and then selects the form’s first and second input elements as the first and last names.

Locate Elements by tagName
In addition to the popular methods we have discussed, there are a few other element locators in the Selenium WebDriver that testers may wish to explore.

One can locate elements by their HTML tag name using the .find_element_by_tag_name() method.

page_heading = driver.find_element_by_tag_name('h1')
Locate Elements by linkText
One can also search for a hyperlink element using the link text. One can either use the .find_element_by_link_text() method to search for the exact link’s text.

# Exact Link Text
click_here_link = driver.find_element_by_link_text('Click Here')
Locate Elements by partialLinkText
Or one can also search for a hyperlink element using the partial link text .find_element_by_partial_link_text() method to search for a partial text.

# Partial Link Text 

click_here_link = driver.find_element_by_partial_link_text('Click')
Locate Multiple Elements
In this tutorial, we have discussed methods that locate only single elements. One may want to select a group of elements and then iterate through them. The .find_elements() method helps in finding multiple elements in the DOM structure.

Here are typical examples of the usage of the .find_elements() method. To find all input elements of a form with ID loginForm, use the following snippet –

from selenium.webdriver.common.by import By

all_inputs = driver.find_elements(By.XPATH, '//form[@id='loginForm']/input')
To locate all elements with a class name, use the following code –

from selenium.webdriver.common.by import By

all_elements = driver.find_elements(By.CLASS_NAME, 'my-css-class')
In addition to this, the By class has the following attributes:

By.ID: search using the CSS ID
By.LINK_TEXT: search using the exact link text
By.PARTIAL_LINK_TEXT: search using partial link text
By.NAME: search using the name attribute
By.TAG_NAME: search using the HTML tag name


findElement and findElements in Selenium

Finding elements on the webpage can be a nightmare due to the complexity of web elements. However, web elements play a vital role in developing and testing any application. Different actions can be performed to find elements in Selenium using commands like search elements, associate events with web elements, etc.

To make things easier for testers, this article will offer insights into Selenium findElement vs findElements with the help of an example.

Introduction to Selenium Find Element
Interaction with a web page requires the driver to locate a web element, and either trigger a JavaScript event like a click, enter, select, etc. or type in the field value. Usually, one starts automated testing of any web app by finding relevant web elements on the web page. Such automated testing is often executed using frameworks like Selenium WebDriver.

Selenium defines two methods for identifying web elements:

findElement: A command to uniquely identify a web element within the web page.
findElements: A command to identify a list of web elements within the web page.
Let’s understand the difference between these two methods in greater detail.

Read More: Selenium WebElement Commands

Difference between findElement vs findElements in Selenium
findElement	findElements
Returns the first matching web element if the locator discovers multiple web elements	Returns a list of multiple matching web elements
Throws NoSuchElementException if the element is not found	Returns an empty list if no matching element is found
Detects a unique web element	Returns a collection of matching elements
Now that you’ve understood the core difference between Selenium findElement vs findElements, also try to get into some fundamental Selenium commands with Basic Commands of Selenium Webdriver.

Find Element in Selenium command Syntax (with explanation)
The findElement command returns an object of the type WebElement. It can use various locator strategies such as ID, Name, ClassName, link text, XPath, etc.

Below is the syntax:

WebElement elementName = driver.findElement(By.LocatorStrategy("LocatorValue"));

Locator Strategy comprises the following values:

ID
Name
Class Name
Tag Name
Link Text
XPath
Locator Value is the unique method to identify the web element quickly.

Example: Find Element in Selenium:

driver.findElement(By.xpath("//input[@id='gh-ac']")).sendKeys("Guitar");

Find Elements in Selenium command Syntax (with explanation)
The findElements command returns an empty list if no elements are found using the given locator strategy and locator value.

Below is the syntax of findElements command

List<WebElement> elementName = driver.findElements(By.LocatorStrategy("LocatorValue"));

Example: Find Elements in Selenium

List<WebElement> listOfElements = driver.findElements(By.xpath("//div"));

Now, let’s delve deeper into understanding how to find web elements with the help of various locators. One can refer to different types of locators in Selenium.

Also Read: How to get HTML source of a Web Element in Selenium WebDriver

How to use Selenium findElement
1. Find by ID
ID is uniquely defined for each element and is the most common way to locate elements using ID Locator. If a website has dynamically generated ids, then this strategy cannot be used to find an element uniquely. However, it will return the first web element which matches the locator.

Example: Let’s take bstackDemo for automating and finding the elements. When we open the website, there is one link button “Favourites”, as shown below.

https://browserstack.wpenginepowered.com/wp-content/uploads/2023/08/findelement_id-768x536.png

As you can see, it comprises an ID locator whose value is favourites.

The code snippet for find element in Selenium uses the same locator value to write a program:

from selenium import webdriver

from selenium.webdriver.chrome.service import service

from selenium.webdriver.chrome.options import Options

service = Service("path/to/driver")

options = Options()

driver = webdriver.Chrome(service=service, options=options)





#instance of Chrome | Firefox | IE driver

driver.get(https://bstackdemo.com/)




elementID = driver.findElement(By.id("favourites"))

# will raise NoSuchElementException if not found

2. Find by Name
This is similar to Find By ID, except the driver will locate an element by the “name” attribute instead of “id”.

Example: Consider the same bstackdemo webpage. After successful login, we have one field with name “viewport” value shown as the given image.

find element in Selenium By NameThe entire code remains similar to that of ID locator, except that the difference will be in the findElement syntax.

elementName = driver.findElement(By.name("viewport"))

3. Find By LinkText
LinkText helps find links in a webpage. It is the most efficient way of finding web elements containing links.

When the tester hits that link and inspects it, it locates the link text Returns, as shown in the snapshot below.

Find Element in Selenium - LinkText
This can be located simply by using Selenium findElement with the syntax below:

elementLinktext = driver.findElement(By.linkText(“Offers”))

4. Find By CSS Selector
CSS Selector is used to provide style rules for web pages and can identify one or more web elements.

Example: Consider the website’s homepage; there is an”Add to cart” button for all products. Using the same value, the Find elements in Selenium method can locate the element.

elementcss= driver.findElement(By.cssSelector('div[id='1'] div[class='shelf-item__buy-btn']'))

Also Read: Quick CSS Selectors Cheat Sheet

5. Find By XPath
XPath is a Selenium technique to navigate through a page’s HTML structure. XPath enables testers to navigate through the XML structure of any document and can be used on both HTML and XML documents.

Example: Let’s try to locate the favorites button on the homepage with the help of XPath. The code below shows that it contains an ID locator. Note that relative XPath starts with ‘//’.

In the image below, one can see a Hyperlink tag. Start with //a. Here //a  implies a tag name. Use the id attribute and pass favourites in single quotes as its value.

This will give the XPath expression shown below:

//a[@id=’favourites’]

Find By XPATH in Selenium

Now, using the Selenium findElement method, execute the code below:

elementxpath = driver.findElement(By.xpath("//a[@id=’favourites’]"))


https://www.browserstack.com/guide/xpath-locators-cheat-sheet

https://www.browserstack.com/guide/css-selectors-cheat-sheet

How to handle iFrame in Selenium

This article will give you a glimpse of frames and iframes. It also describes various methods that enable easy handling of iframes using Selenium WebDriver commands. In the following sections, let’s learn how to handle iframe in Selenium with the SwitchTo() method to switch between frames along with code samples.

What are iframes in Selenium?
An iframe is also known as an inline frame. It is a tag used in HTML5 to embed an HTML document within a parent HTML document. An iframe tag is defined using <iframe></iframe> tags. 

How to Handle Alerts in Selenium?
Handling alerts manually is a tedious task. To reduce human intervention and ease this task, Selenium provides a wide range of functionalities and methods to handle alerts.

The following methods are useful to handle alerts in Selenium:

1. Void dismiss(): This method is used when the ‘Cancel’ button is clicked in the alert box.

driver.switchTo().alert().dismiss();
2. Void accept(): This method is used to click on the ‘OK’ button of the alert.

driver.switchTo().alert().accept();
3. String getText(): This method is used to capture the alert message.

driver.switchTo().alert().getText();
4. Void sendKeys(String stringToSend): This method is used to send data to the alert box.

driver.switchTo().alert().sendKeys("Text");
Tip of the day: 5 Selenium tricks to make your life easier

Now let’s understand how exactly alerts in selenium work with the help of an example.

Real-time Example of Alert Handling
Let’s take the example of the BrowserStack website. Using the Browserstack sign up page for alert handling. Initially, enter the requested details as shown in the below snapshot.

Sign-up page Example
Now, without checking the box of Terms of Service, click on the “Sign me up” button. As it is necessary to accept Terms of Service, it will throw an Alert to check the box of Privacy Policy. The snapshot below depicts the same.

Alert Handling in Selenium  https://www.browserstack.com/guide/alerts-and-popups-in-selenium
The task here is to handle this alert. Let’s write a Selenium test script to handle alerts.

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.NoAlertPresentException; 
import org.openqa.selenium.Alert;

public class AlertHandlingDemo {
public static void main(String[] args) throws NoAlertPresentException,InterruptedException { 
System.setProperty("webdriver.chrome.driver","Path_of_Chrome_Driver"); //mention dummy path or variable that stores chrome driver path 
WebDriver driver = new ChromeDriver(); driver.get("https://www.browserstack.com/users/sign_up");

driver.findElement(By.id("user_full_name")).sendKeys("username"); driver.findElement(By.id("input-lg text user_email_ajax")).sendKeys("username.xyz.net");
driver.findElement(By.id("user_password")).sendKeys("Your_Password");
driver.findElement(By.id("user_submit")).click();

Thread.sleep(5000);

Alert alert = driver.switchTo().alert(); // switch to alert

String alertMessage= driver.switchTo().alert().getText(); // capture alert message

System.out.println(alertMessage); // Print Alert Message
Thread.sleep(5000);
alert.accept(); 
}
}
When you execute the above code, it navigates through the Sign up page, inputs the necessary details, hits the Sign me up button and throws the alert.

Next, the driver will switch to alert, try to capture the alert message, and then display the message.

Note: To cross-verify or handle alerts manually, one can paste the below command.

driver.findElement(By.xpath("//a[@class='bs-alert-close']")).click();
That’s all about how to handle alerts in selenium. With this, let’s move further with this article and understand the fundamentals of pop-ups in selenium.

What are Popups in Selenium?
Popup is a window that displays or pops up on the screen due to some activity. If one wishes to know about the various scenarios of pop-ups and how to handle them, read the documentation page.

How to handle popups in Selenium
In Selenium Webdriver, there are multiple methods to handle popups:

1. Driver.getWindowHandles();

In order to handle the opened windows by Selenium Webdriver, you can use Driver.getWindowHandles() to switch between the windows.

2. Driver.getWindowHandle();

When the webpage is loaded, you can handle the main window by using driver.getWindowHandle(). It will handle the current window that uniquely identifies within the driver instance.

Also Read: How to handle multiple windows in Selenium

Now let’s move further and understand how to handle a web dialog box or a pop up window using Selenium Webdriver with the help of an example.

Handling Web Dialog Box/Popup Window using Selenium
In Selenium, a robot class is used to handle the keyboard and mouse functions. It is used to close the pop-up window. You can get the window handle of the pop-up window using the WindowHandle() function.

I have created my own webpage to demonstrate popup handling in Selenium. You can copy the same code and paste in notepad and save it as .html file to proceed with testing.

Now let’s write a code to handle this dialog box.

import java.util.Iterator; 
import java.util.Set; 
import org.openqa.selenium.By; 
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

public class Popup_Demo { 
public static void main(String[] args) throws InterruptedException { 
WebDriver driver=new FirefoxDriver(); driver.get("Webpage link"); 
driver.manage().window().maximize(); 
Thread.sleep();
driver.findElement(By.id("PopUp")).click(); // Clicking on the popup button
Robot robot = new Robot();
robot.mouseMove(400.5); // Navigating through mouse hover. Note that the coordinates might differ, kindly check the coordinates of x and y axis and update it accordingly.
robot.mousePress(InputEvent.BUTTON1_DOWN_MASK);
Thread.sleep(2000);
robot.mouseRelease(InputEvent.BUTTON1_DOWN_MASK);
Thread.sleep(2000);
driver.quit();
}
}

https://www.browserstack.com/guide/exceptions-in-selenium-webdriver

Exception Handling in Selenium WebDriver

What is Exception?
“Exception” is a standard term used by software programmers regardless of any programming language that is used to write the code. “Exception” as the name suggests, is an unusual event or an uncommon case that disrupts the normal flow of program execution.

There may be several reasons behind the occurrence of exceptions that indicate the halt in the program flow. An exception object is created when an exception is encountered, which contains debugging information such as the line number, the type of Exception, and the method hierarchy. Once the exception object is created and handed over to the runtime environment, this process is called “Throwing the Exception.”

Types of Exceptions in Selenium
The Exceptions are classified mainly into two types:

Checked Exceptions: These exceptions are handled while writing the code itself before the compilation of the code, and hence they are examined at the compile time.
Unchecked Exceptions: These exceptions get thrown at run time and are more catastrophic as compared to Checked Exception.

What is Exception Handling in Selenium?
Exception handling is a process or a mechanism that detects and resolves runtime exceptions and communication errors in Selenium.

11 Common Exceptions in Selenium WebDriver
One can find a complete list of Selenium WebDriver Exceptions in the documentation given by Selenium, but below are a few standard Selenium exceptions faced while running a test:

https://browserstack.wpenginepowered.com/wp-content/uploads/2023/08/Exceptions-in-Selenium-768x529.png

ElementNotSelectableException: This exception belongs to InvalidElementStateException class. This exception occurs when the web element is present on the web page but cannot be selected.Solution:
Try for other interfaces to select the element (selectByIndex, selectByVisibleText).
A wait command can also be added to wait until the element becomes clickable.
ElementNotInteractableException: This exception is thrown when an element is present in DOM, but it is not interactable, like unable to perform any action on it such as clicking or sending keys. This happens probably when the element to be interacted with is either hidden or disabled.Solution:
Wait until the element is visible or clickable using Explicit wait.
Scroll until the element gets in display using the Actions class.
Use JS Executor to interact directly with the DOM.
ElementNotVisibleException: Selenium throws ElementNotVisibleException when an element is present in the DOM, but it is not visible to the user.Solution:
Try to write unique locators that match with a single element only.
Wait until the element is visible or clickable using explicit wait.
NoSuchElementException: This is the most common Selenium exception which is a subclass of NotFoundException class and thrown by findElement() method of Selenium WebDriver. This exception occurs when the locators defined in the Selenium program is unable to locate the element in the DOM.Solution:
Reverify the locator by inspecting the browser and checking whether the element is present on DOM or not. Try switching to more reliable locators.
Wait for the element to load using explicit wait.
NoSuchFrameException: This exception occurs when Selenium is unable to locate the desired frame or iframe using the specified iframe identifier (By iframe id, name or index). Iframe is a web page inside a web page and to work with the iframe elements, we need to first switch to the desired iframe. This exception triggers when Selenium is unable to find the iframe or if it is switching to an invalid iframe.Solution:
Use wait after the action which triggers to open the iframe to ensure the iframe is loaded properly.
Ensure the iframe locator is correct. (Switch between iframe name, id or index and recheck)
NoAlertPresentException: This exception occurs when Selenium tries to switch to an alert box which is not available on the web page which means the driver is switching to an invalid or non-existing Alert pop up. Like iframe, the driver first needs to switch to the desired Alert box to interact with it and then perform actions on it such as clicking on OK/ Submit/ Cancel button or fetching Alert message.Solutions:
Use wait after the action which triggers to open the Alert to ensure it is loaded properly before interacting.
Ensure alert locator is correct and visible on DOM by inspected browser. Try with different alert locators.
NoSuchWindowException: Selenium throws this exception when the WebDriver cannot find the desired browser window or tab using the specified window handle or name. This may occur when the window browser or tab we are attempting to work with is either not present, has been closed during the execution or is not completely loaded.Solutions:
Ensure that the window handle or name being used is accurate.
Wait for the browser window or tab to completely load and then switch the WebDriver to the desired window instance.
StaleElementReferenceException: This exception pops up when the element that was referenced by the locator is no longer present in the DOM or has become stale. It is a runtime exception that occurs when the page gets dynamically loaded, deleting the referenced element completely from the DOM, so that it becomes stale.Solutions:
Refresh the page before accessing the element that causes StaleElementException.
Use try-catch block to handle the exception and attempt to locate the element again in the catch block.
SessionNotFoundException: SessionNotFoundException will occur when the Webdriver is trying to perform actions on the web application after the browser is closed or when the browser session is not available.Solution: To handle such exceptions, we need to revisit our code and check if the code is not accidentally closing the browser. We need to make sure that the browser remains active throughout the execution and should be closed only at the end of the execution.
TimeoutException: In Selenium, TimeOutException occurs when a command takes longer than the wait time to avoid the ElementNotVisible Exception. Due to certain environment conditions such as low internet speed or web application taking more time than usual to completely load, the element to be interacted with does not load. And in such conditions when the WebDriver tries to find the element on the webpage, TimeoutException occurs.Solutions:
Check the load time of the web element manually and add wait accordingly.
Add explicit wait using JavaScript executor until the page is loaded.
Try using some other property to locate the element such as CSS Selector or Xpath.
WebDriverException: This exception occurs when the WebDriver is acting immediately after closing the driver session.Solution: Use driver.close() after the completion of all tests at the suite level and not at the test level. If using TestNG, use driver.close() in @AfterSuite and not in @AfterTest.

Handling Exceptions In Selenium WebDriver
Following are a few standard ways using which one can handle Exceptions in Selenium WebDriver:

Try-catch
This method can catch Exceptions by using a combination of the try and catch keywords. Try indicates the start of the block, and Catch is placed at the end of the try block to handle or resolve the Exception. The code that is written within the Try/Catch block is referred to as “protected code.” The following code represents the syntax of Try/Catch block –

try
   {
     // Some code
   }
catch(Exception e)
  {
     // Code for Handling the exception
  }
Multiple catch blocks
There are various types of Exceptions, and one can expect more than one exception from a single block of code. Multiple catch blocks are used to handle every kind of Exception separately with a separate block of code. One can use more than two catch blocks, and there is no limitation on the number of catch blocks. The code below represents the syntax of multiple catch blocks –

try
   {
      //Some code
   }
catch(ExceptionType1 e1)
   {
     //Code for Handling the Exception 1
   }
catch(ExceptionType2 e2)
   {
     //Code for Handling the Exception 2
   }
Throw / Throws
When a programmer wants to generate an Exception explicitly, the Throw keyword is used to throw Exception to runtime to handle it. When a programmer is throwing an Exception without handling it, then he/she needs to use Throws keyword in the method signature to enable the caller program to understand the exceptions that might be thrown by the method. The syntax for Throws is as follows:

public static void anyFunction() throws Exception
{
try
   {
     // write your code here
   }
catch (Exception e)
   {
      // Do whatever you wish to do here

      // Now throw the exception back to the system
      throw(e);
   }
}
Multiple Exceptions
One can mention various Exceptions in the throws clause. Refer to the example below:

public static void anyFunction() throws ExceptionType1, ExceptionType2

{
 try
   {
     // write your code here
   }
 catch (ExceptionType1 e1)
   {
    // Code to handle exception 1
   }
 catch (ExceptionType1 e2)
   {
    // Code to handle exception 2
   }
}
Finally
The Finally keyword is used to create a block of code under the try block. This finally code block always executes irrespective of the occurrence of an exception

try
  {
    //Protected code
  }
catch(ExceptionType1 e1)
  {
    //Catch block
  }
catch(ExceptionType2 e2)
  {
    //Catch block
  }
catch(ExceptionType3 e3)
  {
    //Catch block
  }

finally
   {
     //The finally block always executes.
   }
One can also use the following methods to display Exception Information:

printStackTrace(): It prints the stack trace, name of the exception, and other useful description
toString(): It returns a text message describing the exception name and description
getMessage(): It displays the description of the exception
Try Exception Handling in Selenium Webdriver

Conclusion

Exception handling is a very crucial part of every Selenium Script
Exceptions in Selenium can not be ignored as they disrupt the normal execution of programs
One can write optimal and robust scripts by handling the Exceptions in unique ways
Programmers can handle standard exceptions using various techniques like Try/catch, Multiple catch blocks, Finally, and others depending upon the requirement of scripts.
For analyzing the exceptions in detail, one can also use methods like printStackTrace(), toString(), and getMessage()

Selenium Wait Commands: Implicit, Explicit, and Fluent Wait
https://www.browserstack.com/guide/exceptions-in-selenium-webdriver

How to handle iFrame in Selenium
https://www.browserstack.com/guide/handling-frames-in-selenium

How to get HTML source of a Web Element in Selenium WebDriver
https://www.browserstack.com/guide/alerts-and-popups-in-selenium

Selenium Wait Commands: Implicit, Explicit, and Fluent Wait
https://www.browserstack.com/guide/wait-commands-in-selenium-webdriver

Selenium Wait Commands: Implicit, Explicit, and Fluent Wait
https://www.browserstack.com/guide/wait-commands-in-selenium-webdriver

Understanding ExpectedConditions in Selenium (with Types and Examples)
https://www.browserstack.com/guide/expectedconditions-in-selenium

How to get Selenium to wait for a page to load
https://www.browserstack.com/guide/selenium-wait-for-page-to-load

Wait Commands in Selenium C and C#
https://www.browserstack.com/guide/wait-commands-in-selenium-c-and-c-sharp

Design Patterns in Selenium
https://www.browserstack.com/guide/design-patterns-in-selenium

Design Patterns in Automation Framework
https://www.browserstack.com/guide/design-patterns-in-automation-framework

Page Object Model in Selenium and JavaScript
https://www.browserstack.com/guide/page-object-model-using-selenium-javascript

Understanding No Such Element Exception in Selenium
https://www.browserstack.com/guide/no-such-element-exception-selenium

Agile Testing Metrics that every tester must know
https://www.browserstack.com/guide/agile-testing-metrics

11 Agile Testing Challenges and its Solutions
https://www.browserstack.com/guide/agile-testing-challenges

Continuous Integration in Agile
https://www.browserstack.com/guide/continuous-integration-with-agile

Selenium Automation Framework: A Detailed Guide
https://www.browserstack.com/guide/selenium-framework

Software Testing Strategies and Approaches
https://www.browserstack.com/guide/software-testing-strategies-and-approaches

5 Questions to ask before every Software Release
https://www.browserstack.com/guide/questions-to-ask-before-software-release

What is Automation Testing: Benefits, Strategy, Tools
https://www.browserstack.com/guide/automation-testing-tutorial

Best Practices for Selenium Test Automation
https://www.browserstack.com/guide/best-practices-in-selenium-automation

6 Things to avoid when writing Selenium Test Scripts
https://www.browserstack.com/guide/things-to-avoid-in-selenium-test-scripts

ChatBot Testing : A Beginner’s Guide
https://www.browserstack.com/guide/what-is-chatbot-testing

Best Practices
https://www.browserstack.com/guide/category/best-practices

Parallel Testing with Selenium
https://www.browserstack.com/guide/parallel-testing-with-selenium

Learn Selenium with Java to run Automated Tests
https://www.browserstack.com/guide/selenium-with-java-for-automated-test

How does Selenium isDisplayed() method work?
https://www.browserstack.com/guide/isdisplayed-method-in-selenium

Top 21 Monitoring Tools in DevOps for 2024
https://www.browserstack.com/guide/top-devops-monitoring-tools

Understanding Playwright Assertions
https://www.browserstack.com/guide/playwright-assertions

Understanding No Such Element Exception in Selenium
https://www.browserstack.com/guide/no-such-element-exception-selenium

Playwright vs Selenium: Which to choose in 2024
https://www.browserstack.com/guide/playwright-vs-selenium

Unit Testing of React Apps using JEST : Tutorial
https://www.browserstack.com/guide/unit-testing-of-react-apps-using-jest

Test Plan vs Test Strategy: Purpose & Differences
https://www.browserstack.com/guide/test-plan-vs-test-strategy

Understanding Element Click Intercepted Exception in Selenium
https://www.browserstack.com/guide/element-click-intercepted-exception-selenium

Understanding Element Not Interactable Exception in Selenium
https://www.browserstack.com/guide/understanding-element-not-interactable-exception-in-selenium

Cypress vs Selenium: Key Differences
https://www.browserstack.com/guide/cypress-vs-selenium

How to Select Date from Datepicker in Selenium Webdriver using Java
https://www.browserstack.com/guide/datepicker-in-selenium

Nightwatch vs Mocha vs Protractor : Differences
https://www.browserstack.com/guide/nightwatch-vs-protractor-vs-mocha

Understanding Stale Element Reference Exception in Selenium
https://www.browserstack.com/guide/stale-element-reference-exception-selenium

Top 9 JavaScript Testing Frameworks in 2024
https://www.browserstack.com/guide/top-javascript-testing-frameworks

Understanding Selenium Timeouts
https://www.browserstack.com/guide/understanding-selenium-timeouts

Cross-Site Scripting (XSS) Testing to Prevent XSS attacks
https://www.browserstack.com/guide/xss-testing

Understanding Testing Library Jest DOM
https://www.browserstack.com/guide/testing-library-jest-dom

Understanding ExpectedConditions in Selenium (with Types and Examples)
https://www.browserstack.com/guide/expectedconditions-in-selenium

How to handle Alerts and Popups in Selenium?
https://www.browserstack.com/guide/alerts-and-popups-in-selenium

Handling Login Popups in Selenium WebDriver and Java
https://www.browserstack.com/guide/alerts-and-popups-in-selenium

How to Close a Browser in Selenium
https://www.browserstack.com/guide/close-browser-in-selenium

How to perform Mouse Hover Action in Selenium
https://www.browserstack.com/guide/mouse-hover-in-selenium

All about TestNG Listeners in Selenium
https://www.browserstack.com/guide/testng-listeners

TestNG Annotations in Selenium Webdriver with Examples
https://www.browserstack.com/guide/testng-annotations-in-selenium

How to Scroll Down or Up using Selenium Webdriver
https://www.browserstack.com/guide/selenium-scroll-tutorial

How to use DataProvider in Selenium and TestNG?
https://www.browserstack.com/guide/dataprovider-in-selenium-testng

TestNG vs Cucumber: Core Differences
https://www.browserstack.com/guide/testng-vs-cucumber

Test Automation using Selenium and Cucumber Framework: Tutorial
https://www.browserstack.com/guide/automation-using-cucumber-selenium

What is Cucumber Framework? (Benefits of Cucumber Testing)
https://www.browserstack.com/guide/learn-about-cucumber-testing-tool

How to Run Tests with Cypress and Cucumber
https://www.browserstack.com/guide/how-to-run-cypress-cucumber-test

How to Automate TestNG in Selenium
https://www.browserstack.com/guide/testng-framework-with-selenium-automation

Page Object Model with Playwright: Tutorial
https://www.browserstack.com/guide/page-object-model-with-playwright

Page Object Model and Page Factory in Selenium
https://www.browserstack.com/guide/page-object-model-in-selenium

Page Object Model and Page Factory in Selenium C#
https://www.browserstack.com/guide/page-object-model-and-page-factory-in-selenium-c

Page Object Model in Cucumber
https://www.browserstack.com/guide/page-object-model-in-cucumber

Cucumber Best Practices to follow for efficient BDD Testing
https://www.browserstack.com/guide/cucumber-best-practices-for-testing

How to run failed test cases using TestNG in Selenium Webdriver?
https://www.browserstack.com/guide/run-failed-test-cases-in-testng-and-selenium

Database Testing using Selenium and TestNG
https://www.browserstack.com/guide/database-testing-using-selenium

How to Scroll Down or Up using Selenium Webdriver
https://www.browserstack.com/guide/selenium-scroll-tutorial

How to perform Mouse Hover Action in Selenium
https://www.browserstack.com/guide/mouse-hover-in-selenium

5 Common Bugs Faced in UI Testing
https://www.browserstack.com/guide/bugs-in-ui-testing

How to handle Multiple Tabs in Selenium
https://www.browserstack.com/guide/handling-tabs-in-selenium
