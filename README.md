Day 43:
annotation 
@BeforeMethod
@AfterMethod

@BeforeClass --> execute only once before starting tc 
@AfterClass ---> execute only once after starting tc

@BeforeTest ---> execute once if we have 1 class for each test, if we have multiple class it will execute for each test level
@AfterTest 

@BeforeSuite
@AfterSuite

method-class-test-suite


1) login --@BeforeMethod -- before every test method
2) search 
3) logout---@AfterMethod
4) login
5) adv search 
6) logout

login-test-logout
beforemethod-test-aftermethod
----
suite test class
<suite> 
	<test
 		<class>
			//method
		<class>
	<test
<suite
====
BeforeSuite
	BeforeTest
		BeforeClass
			BeforeMethod
				test2
			AfterMethod
			BeforeMethod
				test2
			AfterMethod	
		AfterClass
	AfterTest
AfterSuite

Assertion - validation point: 
why we need assertions? even when the test is failed it gives passed so we use assertion 
Assert.assertEquals(title1,title2) //a predefined class
//we will see the assertion outputs in reports
Assert.assertTrue(true)
Assert.assertTrue(false)

types of assertions:
hard and soft
assert.assertEquals("123",123) //fails
Assert.assertNotEquals(123,123) //fails
Assert.fail()
hard assertions are the methods to access the class.
once hard assertion is failed, it wont continue the code so we use soft assertion.

SoftAssert sa=new SoftAssert()
sa.assetEquals(1,2)
sa.assertAll();//mandatory or evey soft assert will be passed

hard assert directly access the class as Assert is a class
soft asset we access the class through object using SoftAssert class



what is annotations?
when do we use soft / hard assert?
---------
Day 44:
dependency methods 

if login fails, other test cases will fail. so we need to skip all dependence methods.

dependsOnMethods={"openapp"}//void openapp{} as it will skip the dependent if it fails. 

grouping: 
groups={"groupname"}
@Test(priotroty=1,groups="sanity")

@Test(priotroty=1,groups={"sanity","ss"})

In XML:
<test>
<groups>
	<run>
		<include name""/>
	</run>
</groups>

<classes>
 <class/>
<classes>
</test>


----
Day 45: 
parameterization


1- @DataProvider -- data driven testing
2- using cml file -- parallel testing 

dataprovider to prepare test data and return to another test method- to provide test data to anther test data like chaining 
:) avoid looping statmenets - repeated 


@DataProvider(name="db", indices={0,1})//it returns object 2d type of an array- to create test data and prepare it.
Object[][] loginData()//return data any type // indices:هياخد اول و تاني بس 
{
Object data[][]={
{"abc1@gmail.com","test1"},
{"abc2@gmail.com","test2"},
{"abc3@gmail.com","test3"}
			}
return data;
}

@Test(DataProvider=db)
void testlogin(String email,String pwd){
......sendKeys(email)
}
---
pass browser from xml inside a class
<parameter name="browser" value="chrome"/>
@Parameters({"browser"})
void setup(String br)

--
run sequential  
on xml create test and change the value

run parallel
<suite name="Suite" parallel="tests"> 
or on any level
practice day 45:


Day 43:
annotation 
@BeforeMethod
@AfterMethod

@BeforeClass --> execute only once before starting tc 
@AfterClass ---> execute only once after starting tc

@BeforeTest ---> execute once if we have 1 class for each test, if we have multiple class it will execute for each test level
@AfterTest 

@BeforeSuite
@AfterSuite

method-class-test-suite


1) login --@BeforeMethod -- before every test method
2) search 
3) logout---@AfterMethod
4) login
5) adv search 
6) logout

login-test-logout
beforemethod-test-aftermethod
----
suite test class
<suite> 
	<test
 		<class>
			//method
		<class>
	<test
<suite
====
BeforeSuite
	BeforeTest
		BeforeClass
			BeforeMethod
				test2
			AfterMethod
			BeforeMethod
				test2
			AfterMethod	
		AfterClass
	AfterTest
AfterSuite

Assertion - validation point: 
why we need assertions? even when the test is failed it gives passed so we use assertion 
Assert.assertEquals(title1,title2) //a predefined class
//we will see the assertion outputs in reports
Assert.assertTrue(true)
Assert.assertTrue(false)

types of assertions:
hard and soft
assert.assertEquals("123",123) //fails
Assert.assertNotEquals(123,123) //fails
Assert.fail()
hard assertions are the methods to access the class.
once hard assertion is failed, it wont continue the code so we use soft assertion.

SoftAssert sa=new SoftAssert()
sa.assetEquals(1,2)
sa.assertAll();//mandatory or evey soft assert will be passed

hard assert directly access the class as Assert is a class
soft asset we access the class through object using SoftAssert class



what is annotations?
when do we use soft / hard assert?
---------
Day 44:
dependency methods 

if login fails, other test cases will fail. so we need to skip all dependence methods.

dependsOnMethods={"openapp"}//void openapp{} as it will skip the dependent if it fails. 

grouping: 
groups={"groupname"}
@Test(priotroty=1,groups="sanity")

@Test(priotroty=1,groups={"sanity","ss"})

In XML:
<test>
<groups>
	<run>
		<include name""/>
	</run>
</groups>

<classes>
 <class/>
<classes>
</test>


----
Day 45: 
parameterization


1- @DataProvider -- data driven testing
2- using cml file -- parallel testing 

dataprovider to prepare test data and return to another test method- to provide test data to anther test data like chaining 
:) avoid looping statmenets - repeated 


@DataProvider(name="db", indices={0,1})//it returns object 2d type of an array- to create test data and prepare it.
Object[][] loginData()//return data any type // indices:هياخد اول و تاني بس 
{
Object data[][]={
{"abc1@gmail.com","test1"},
{"abc2@gmail.com","test2"},
{"abc3@gmail.com","test3"}
			}
return data;
}

@Test(DataProvider=db)
void testlogin(String email,String pwd){
......sendKeys(email)
}
---
pass browser from xml inside a class
<parameter name="browser" value="chrome"/>
@Parameters({"browser"})
void setup(String br)

--
run sequential  
on xml create test and change the value

run parallel
<suite name="Suite" parallel="tests"> 
or on any level
practice day 45:

==========================
Day 20 continue
HashMap like dictionary 

HashMap <Integer, String>hm=new HashMap();
hm.keySet()//return only keys
hm.values()//return values only
hm.entrySet()//return keys and values
in for -->k k.get

Day 46:
testing listners 

want to perform some actions 

after pass--> post action
failed --> post action
listener is a class to perform some actions 


2 ways to implements listener class:
method 1: class mylistener implements ITestlistener

ITestlistener s an interface 
method 2
class mylistener extends TestListenerAdapter 

 store items in "key/value" pairs,
hm.put(100,"john");//add pairs


public class Mylistener implements ITestListener 
{
 void onStart(ITestResult context){}//execute only once
 void onTestStart(ITestResult context){}//execute for every test
 void onTestSuccess(ITestResult context){}
 void onTestFailure(ITestResult context){}
}

right click on class -->testing >>

to run listener class without xml file:
in class 
@Listeners(filename.MyListener.class) //above
but run listener from xml is better
 

لو عندنا كذا كلاس فايل كل شوية اعرف الليسنر فية!
الاحسن الاكس ام  ال علشان بحط سطر واحد و بيشتغل مع كل الكلاسس

Day 47:
POM
its a design patter. to locate locators in separate location. 

how many pages u will going to interact?
for each page u will create classes contains page elements and actions. 
testcase class 

LoginTest--> testmethods - validation 
page object class--> page element and action methods 

:) reusability - update locators 

2 approaches to create page object classes:
1- without pagefactory to create page object class
2- using pagefactory to create page object class// avoid findElement by writing locators in diff way
--------------------

loginPage.java

package day47;
public class loginPage{
WebDriver driver;
//constrator
loginPage(WebDriver driver)
{
this.driver = driver;
}
//locators
//WebElement //usertxt=driver.fineElement(By.xpath("//input[@placeholder='Username']"));
//By loc =By.xpath("//input[@placeholder='Username']")
//driver.findElement(loc).sendKeys("");
//store the locator in a variable 
By txt_username_loc =By.xpath("//input[@placeholder='Username']");
By txt_password_loc=By.xpath("//input[@placeholder='Password']");
By btn_login_loc=By.xpath("//button[@']");
//from selectorHub second button, write the pattern u wanna then select the locator, click on third button then copy
driver.findElement(loc).sendKeys("");


//action methods
//every locator has an action

public void setUserName(String user)
{driver.findElement(txt_username_loc).sendKeys(user);}


public void setUserName(String pwd)
{driver.findElement(txt_password_loc).sendKeys(pwd);}

public void clickLogin()
{driver.findElement(btn_login_loc).click();}


}

======================
LoginTest

public class LoginTest{
Webdriver driver;

@BeforClass
void setup(){driver= new ChromeDriver();
driver.manage().implicitlyWait(Duration.ofseconds(4));
driver.get("")}

@Test 
void testlogin()
{ //action methods 
LoginPage lp= new LoginPage(driver);//the constructor
lp.setUserName("Admin");
lp.setPassword("admin123");
lp.clickLogin();
//validation
Assert.assertEquals(driver.getTitle(),"");
}

@AfterClass
void tearDown()
{
driver.quite();}
 }

//execute test class, so pom class will refer inside test case

//another way to create page object class

public class LoginPage2{
WebDriver  driver;
//constrator
LoginPage2(WebDriver driver)
{this.driver=driver;
PageFactory.initElement(driver,this);}
//locators
@FindBy(xpath="//input") WebElement txt_username;//stor the element in a var





 }
 =======================================================8 APRIL 2025=====================
 Day 17:
Wrapper classes:
WE CAN store data in object formate or primative format;
String s="welcome";
string s= new String("welcome")
every primitive data there is a wrapper class.
:) can convert the data format from string to int,char--> Integer.parseInt(vluewannaconvert);
String.valueOf(anythingwillbe converted ot string)


ArrayList arr=new ArrayList();//accept diff types
:) in collecgtions we use wrapper classes

package: 
2 types of packages:
build in "import" and user defi	ned package 

access modifier:
defines the scope of methods 
public - protected- default - private: access only within the class

Day 18:
Exception handling:
event cuz the program to termination. it is not an error. becomes cuz of user mistakes.
we have 2 types of exceptions:
	1- checked which can be handled by try catch() or  keyword
as when i use thread.sleep() there is a change to get exception as ther process is sleeping and manybe another process wil come in parallel and interrupt the first process 
	2- unchecked  try catch() finally//will always se conn
Errors:
1- syntax
2- logical

try 
{ //ok
}
catch(mention the exception e)
{//not ok
}
catch(another exception)
{not ok
}

Exception class to handle all exceptions


 



Day 19: 
convert the data from type to type
up casting/ widening //from smaller to larger
down casting/ narrowing // from larger to smaller -- int y=(int) x;

Parent p= new child()//upcasting from child to parent
//storing a child object into the parent
// we cannot access child class p.childmethod

rules for typecasting
1- there is a relationship 
Didnt finish it 
===10-4-2025
Q1:Merge two given sorted array of integers and create a new sorted array
جبت اخر 2 ارايس و بقارن 
 واحط الاصغر ف الاراي الجديد و ازود الاراي القديم الي بقارن بية
--
Q2:Get the first occurrence of a string within a given string

strstr(,)Get a pointer to the first occurrence of a string in another string
char myStr[] = "The rain in Spain falls mainly on the plains";
char *myPtr = strstr(myStr الجملة الي بدور فيها, "ain"الي بدور عليه);

-----
ep1 collections: 
collection vs collection framework 
collection is a group of objects. 

collection framework: to represent group of objects into a single intity"class or interfaces" like 
-ArrayList 
-List 
-HashMap
-HashTable
-TreeStack


int a[] = new int[100];//group of objects 
:( homogenious data same kind of element
:( fixed size cannot increase or decrease



Object a[]=new object[5];
:) diff data type 
group of objects with diff types
:) dynamic size
:) have methods like sort, search


ep2: java collections:

collection interface contains common methods
collections is a class in java.utile package so we can use methods.

Collections.sort(arr);  
3 interfaces: List like ArrayList, Set, Queue 
List is a child of collection interface
1-ordered
2-duplicate is allowed 
listname.add(objectadded)
listname.addAll(multipleobjects)
listname.remove(objectneedtoremove)
listname.removeAll(collectionname)
listname.retainAll(collectionname)//all object will be removed except in retainAll
listname.clear()
.isEmpty()
.size()
.contains()
containsAll()
.set()
.get()
.sort()
.shuffle()

Set interface:  ----> HashSet, LinkHashSet
1- not ordered --no index
2- duplicate not allowed


Queue interface:FIFO
1-priority queue


Map interface is not a child interface of collection is independent.

key and value pair. 
HashMap 
LinkedHashMap 
HashTable 




==========14-4-2025
Cardholder data should not be stored in plaintext in the database.
Sensitive data (e.g., full card numbers, CVV) must be encrypted using appropriate methods.
If card data is displayed (e.g., in a report or dashboard), it must be masked to show only the last four digits of the card number and never show CVV.
POST CONDITIONS: No sensitive data (e.g., credit card numbers, CVV) should be exposed in the database or logs.
Cardholder data is stored in an encrypted format, with no sensitive information visible in the database or logs.
crucial financial regulations like PCI-DSS, GDPR, SOX, and PSD2

GDPR: general data protection regulationv

--
thanks for this opporunity to intriduce myself. my name is menna . graduated from .. i have a totla exp of 3.5 y in software testing field and i worked on both manaual and automation.  i have experienced ] domain  telecomm , GIS and newly investment banking  projects. as a part of testing team my roles and resposibilties is to understand requiement and do my static testing then clarify if we have any confilict with previous requiement or not. prepare test cases then report to them using DTS like jira to report the defects as dts we use in my organzization for tracking purpose or for project management tool.

Also i have experience in sanity testing functional , regression , retest, little performance testing like load and stress test. API testing using postman to make sure the status code and payload is verified correctly with database testing.
recently i am working in automation testing currently we use selenium webdriver as a tool and java as a language with page object model to make things organize. 

As an automation tester my roles and respoisiblity to identiy test ccases and take a couple of E2E test cases to generate automation test cases to develop test classes per requiement.
and making test scripts and execute them also review them and  awre of agile frame work. Attending daily stand up meeting  and clarificatoin meeting and demos with the clients and finally attend the retrospect meeting

