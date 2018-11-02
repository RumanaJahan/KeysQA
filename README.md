# Best Practice with Selenium

# Hybrid Framework has been used which is a hybrid of Behavior Driven Development and Data Driven Framework
- Behavior Driven Development framework allows automation of functional validations in easily readable and 
  understandable format for all the stake holders
- Data Driven Framework retains the test data in external file database so that the same functionality can be 
  tested with different test data sets
- Reusable
- Reduced script maintenance
- Portable


## Be robust and portable 
  - Prefered selector order : id > name > css > xpath 
  - Avoid Thread.sleep prefer Wait or FluentWait
  - Use relative URLs
  - Don’t rely on specific Driver implementation
  - Create your dataset

## Know your new tool
  - Keep up to date (versions and usage pattern)
  - How to deal with UI components like... fileupload, datepicker, ajaxtables,...
  - Detect when selenium isn't the good tool for the job, then use other tool

## Use PageObjects pattern

Page Object is a Design Pattern which has become popular in test automation for enhancing test maintenance and reducing code duplication. A page object is an object-oriented class that serves as an interface to a page of your Application Under Test. The tests then use the methods of this page object class whenever they need to interact with that page of the UI. The benefit is that if the UI changes for the page, the tests themselves don’t need to change, only the code within the page object needs to change. Subsequently all changes to support that new UI are located in one place.

### The Page Object Design Pattern provides the following advantages :

There is a clean separation between test code and page specific code such as locators (or their use if you’re using a UI map) and layout.
There is  a single repository for the services or operations offered by the page rather than having these services scattered through out the tests.
For example you have a LoginPage that you can reuse in all your integration test.
if the logon has now a new option or the layout changed a bit… adapt the LoginPage… that’s it !

## Preferred selector order : id > name > css > xpath

To locate an element we can use

- the element’s ID
- the element’s name attribute
- an XPath statement
- by a links text
- document object model (DOM)

In practice, you will discover id and name are often the easiest and sure way.
xpath are often brittle. for example you have 3 tables displayed but sometimes there are no data and the table isn’t rendered, your xpath locating the second table will not always return the intented one.
css are the way to go in conjunction of id and name !
locating links in an internationalized application is sometimes hard… try to use partial href.
various selectors articles : why-jquery-in-selenium-css-locators-is-the-way-to-go, css selector demystified, jquery selectors

## Avoid Thread.sleep prefer Wait or FluentWait

## Use relative URLs

## Avoid hardcoding hosts

Don’t rely on specific Driver implementation

