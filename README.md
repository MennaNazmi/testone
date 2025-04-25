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



As an automation tester my roles and respoisiblity to identiy test ccases and select a couple of E2E test cases to generate automation scripts to develop test classes per requiement.
and making test scripts and execute them also review them and  awre of agile frame work.Also Attending daily stand up meeting  and clarificatoin meeting and demos with the clients and finally attend the retrospect meeting


currently we use page object moodel in my organizatoin as we use maven project as there are different folders in maven project like 
1- SRC/test  src/resources in src'test all the test classes and 
2- in src/main/java we create pages. 
3- POM.xml we store all depenecies 
4- testng.xml to run the test cases in paralaer with parameters from config file to store login credential as we use testng annoation with @test @beforeclass @afterclass also we use assertions for our test case base or fail to verification.
as in maven depenecy all downloaded jar files are stored in maven dependecy 
5- we create basepage class and baseclass which has the constructor and extened ed to test class that is inheritance operation.
6- we create different folders like scrennshots to store any failed test cases , logs, utities 

also we like jenkins continus integration 

Q)we have to use:
comments 
try and catch

Q) host key verification failed?

Q)how to test 10K users?

we have2 approaches connect to database then ccreate a for loop then run
second using jmeter using assertions 


enviroment issues llikeOS Differences:
. Permissions and Access Rights:
Browser/Driver Differences 
========20-4-2025
authenticatoin pops up in selenium java

1- passing credentials in HTTP URL 
http://username:password@yourwebsite.com

2. Handling authentication dialogs using Alert
Alert alert=driver.swithcTo().alert();
alert.accept();

3. Using AutoIT (for Windows-based pop-ups)
but this has to be not headless mode. GUI


4. POM vs PageFactory?
   Page Object Model (POM) is a design pattern in Selenium where each web page is represented by a separate class. The main idea is to create a class for each page of the application, and this class should contain all the elements and methods required to interact with that page.

   Page Factory is a class that provides a convenient and efficient way to initialize and manage web elements using annotations in Selenium. It is a part of the Page Object Model but specifically refers to the way the elements of a page are initialized and managed.Page Factory leverages annotations like @FindBy and @CacheLookup to locate web elements. It is used in combination with PageFactory.initElements(driver, this) to initialize the elements on the page.

   POM initialization: we use driver.findElement() or bBy locators
   Page Factory: automatically initializes elements using PageFactory.initElements() 


5. limitaions for selenium webdriver?
   	1-Limited suppoer for desktop applications so we can use autoIT
   	2-Cannot handle captchas
    	3-Does not support some browser-specific features such as extensions
        4-No Built-in Reporting
   	5-Difficult to Handle Complex File Uploads and Downloads

6.how to handle dynamic elements in selenium?
	1-Using Explicit Waits -- wait.until
 	2-using XPath with contains() or starts-with() 
  		WebElement element = driver.findElement(By.xpath("//*[contains(@id, 'dynamic-part')]"));
    	3-Selenium 4, relative locators
7. DesiredCapabilities?
	are used to define the properties or configuration like browser configuration is chrome or edge

 8. The diff QA  ضمان الجودة and QC مراقبة الجودة?
    QA: Process-Oriented
    	preventing defects بنطبق الاجايل و طرق التيستنج المختلفة
        A well-defined test strategy
    هل بنتيست ازاى ؟ البروسيس ماشية ازاى ؟ اول حاجة ال اسموك وبعدها الفانكشنل و بعدها السانتي لو لقينا بج و بعدها الريتيست و بعدها الريجريشن  و هذا و نمشي ف البج لايف سايكل

  OC:  Product-Oriented 
       detecting defects 
       الي بنعملو علشان نطلع الديفكتش والبجز


###########
https://www.youtube.com/watch?v=rdv6OdbROHA&ab_channel=RDAutomationLearning

Q1-If u have a requiement with no doc, how will u test ur software?
at this time ill do exprotatry testing and understand the business needs, after understand the requiements ill write the documentation with user stories like memo from the meeting then ill write the test cases then test execution that covered all scenarios. so the short answer is expratory testing.

Q2: u have a release in 3 days and ur tc are working find but the cliend want to add 1 more US added to the release so we need to add us with development and testing so its a change with deploy and build, will u say yes or will u ask for more time?
First ill ask the stakholders and client team then ill create a test plan with acceptance criteria with test data and my resocurse so if we need more people ill ask them to finish this in 3 days for about 805 if that ok we will go thro the confirmation process. if not ill negation with them to release this new change in the next sprint.


Its a business ask so u got the decision from the stakeholders or the client team. so if its necessary so we will deliever it. so ill create my test plan with acceptance criteria with test data. 
then in the meeting ill show him the test plan with my resources/ people
واني هدخل حد تاني ف التيم علشان الدنيا زحمة  لو تمام هخلص مثلا 80 ف المية ف 3 ايام 
ف هنروح للموافقة  

Q3: tell me points in retrospective meeting?
عباردة اية الحاجاات الحلوة اية الحاجات الوحشة ازاى محسن من نفسنا؟
need to add some mock up in ui for examples 

Q4: u had us in sprint 1 and us in sprint 2. the client found a bug in us sp1 so the dev will fix that ib us sp1. u wont be to test us 2 what will u do?

ill find the root cause for us 1. like any prod issue after finish sp 1 ill go to sp 2. so ill prioritize this us which the client found the bug.

Q5: whats defect cascading? is a defect which is caused by another defect.

Q6: how u test the api? using crud methods and compare the expected and actual results.

Q7: the diff global and local var in postman?
postman is an api testing tool. local is the smallest var scope. 
global are the ones can use in outside the collections with diff env for examples.verify the status code and payload with inputs and outputs. when the value is changes or not. we can use assertions. 



Q8: authorization vs authentication:
authorization: مين يقدر يعمل اية؟,What can you do?

authentication: مين الي هيدخل و مين لا؟Who are you? . identity of a user, device, or system
these are in security testing. 

C then Z.



Q9: what is test clouse report? 
after closing the defects and us. so its kind of docu to client with test scenarios to ocfficatlly finish the test process. how many bugs. how many test cases.
#############################
#############################

https://www.youtube.com/watch?v=lJSPN3EZdJ8&ab_channel=RDAutomationLearning

Q1: review the test cases on particual scenario with fresher, can u tell me which are the points or details u focuse? 

check if u cover all the project core functionality using test case tech like BVA, EP or even decision tree and how positive scenario and negative scneaio.

Q2: u found a crical defect, u spoke to dev team, how to manage the time so it wont wasted? 
if the defect is critical, ill make it the priortoy to be fixed as soon as possible at the same time, i am preparing my scenario and test cases  and what is the expected result and the effect on different scenario

Q3: the critical defect is fixed on satureday, and the next 2 days are off. would u test on satureday or Monday? 

if the release on Monday, I will tell them to be tested before Monday i know its vacation so i need to make my work perfect. 


Q4: how much time u take to create the severity matrix? 
after the test ccases work is done, we write the severity matrix, ID, scenario, fn,


Q5: if u dont have access to database how to test it?
check the env problem or connection problem. if all is ok, machine problem 

Q6: u have a relaese after 1 week and before release u have working freeze no one is allowed to do any changes, but there is a requeiemtn from the client so there is a grooming section are reviewing a US?

اول حاجة اسئل علي هل الحاجات الجديدية المطلوبة هتاثر علي القديم و يحصل 
cascading defect 

لو مش هتاثر نخليها الاسبرنت الي جي 
لو هتاثر هنحطها ف الاسبرنت و نعمل رجرشن تيست

Q7: what is acceptance criteria? 
is the product accept the customer needs as the tests fullfil the customer requiements. 
عبارة عن تشيك ليست ان الريكويرمنت تمام و ميحصلش 
flaky testing or scenario loss 
the non function is apart from acceptance criteria. there are some feature can be in next sprint. 

Q8: what happened in daily standup meeting? 
its an agile process. is conducted fo 15 min to answer of 3 questions. what is ur yesterday task? whats ur today task? is there any pending task in  ur hand? or problem. as its an important meeting to be aligned with dev and testers and pm. so we can finish the sprint on time.--
what issue u faced, then raised a dts, then fixed and resolved?
amount fix enter accept decimal values not integars only when i communicate with the dev and still not fully aware of the funcationallity. so due to my daily standup meeting


Q9: the client changes the US the u have written the test cases and performed the test execution, how u deal with this situation?
هقارن بين الجديد و القديم  لو في تعديل  بسيط هزود لكن لو كلها متغير هبدا من اول 

############################
https://www.youtube.com/watch?v=h4_XWnnPP8E&ab_channel=RDAutomationLearning

Q1: while showing the demo a bug is showing?
i will check my test evidence document or send it in the meeting attached and say we had test this ffeature earlier maybe there something changed so we will retest it and fix it as soon as possible. and after fixing the issue ill mention in the project group. 

Q2: if the req is not clear with u what will u do?
i will colaboorate with team members as i am seeking for the information then i will move froward but i will not jump to write the test cases. 

Q3: api testing? 
1-check url,
2- check methods, 
3-check user name and pass with param
4- check the status code. 
5- check the token timeout.

################ 
https://www.youtube.com/watch?v=0KRthSLtDPY&ab_channel=SoftwaretestingbyMKT

Q1: what challenges u faced?

communication- keep following the ppl fo a bug 
some times the data is not available , the env is not ready.

#####################23-4-2025
https://www.youtube.com/watch?v=REiiI3j8h-A&list=PLTGn8a4YcF3xjCN4ZQl3ymhVmRGDflmAd&index=42&ab_channel=RDAutomationLearning

Q1: what's normalization? 
when u have great schema.

in denormalization

==
https://www.youtube.com/watch?v=_Pj0ueripow&list=PLTGn8a4YcF3xjCN4ZQl3ymhVmRGDflmAd&index=9&ab_channel=RDAutomationLearning


Q1: write a code to read a data from excel file?


==
https://www.youtube.com/watch?v=7W4FFy0TEHE&t=13s&ab_channel=RDAutomationLearning

Q1: the diff test scenario and test cases?

test scenario is a group of test cases.
in test case we cover low level functionality as in test case we have prereq - test steps.

Q2: if u got a defect what steps u take?

ill raise an issue and retest then regression test. and take an eveidance with screenshots and videos 

Q3: what if developer say its not a defect? 
go to the req that documents
tell them/collaborate my test scenarios and steps
inform my Team lead 
go to PM

Q4: testing in multi environment? qa env/ production env but the diff output in production env what will u do?

u will validate the scenario that i go through to the client and check if that follows the acceptance criteris and req or new thing? 
we try to find the root cause analysis. 
CHECK ISSUE OR NOT->ROOT CAUSE "missed to test it so ill add a new test case or a new req we need to disucss with developer".


Q5: which is the diff testing tech?and when do we use it? BVA is used at boundaries of input range rather thatn fousing on middle values.

Q6: testing amazon filter? how much time? 
first smoke testing  i calculate for design and test cases and execution on diff devices and env called compatibility testing with performance testing. if we have multiple ppl with diff lang. 

planning 3 days
functional -- 7 days
usabliy 2 days 
performace 5 days
security 2 days 
cross browsing 5 days

regression 7 days
post release 3 dyas 
so it will take for around 35 dyas


Q7: how to test google map?
direction - lat -long - share location - valid/invalid address - search landmarks- filters like atms search - real time routes- offline location after downloading - zoom
 

####################25-4-2025


https://youtu.be/TowbBJYjNic?si=DVOQx-My7-GJGX32

How Many types of browser in selenium?

Chrome-egde-firefox

How to make sure the page is loaded in selenium?

By checking the element is there or not.

 

How to run selenium using command line?

Whats the exceptions? 

Nosuchelements

WebdriverException

Timeout exception-->

Nosuchwindow exception

Sealelement exception

 

 

How to scroll down And scrol down element?

 

 

What are the listeners in selenium?

We have2 types webdrive and testng

 

 

 

How to take take screenshot in webdriver?

 

Tll me test status in selenium? Smke-fn-reg- sanity- crossbrowser- integration test

 

Whats assertion in selenium? Its a verifivation point

 

 

Whats build faces in maven?  Validate-Combine-test-ackege-install-deploy

 

 

How to handle keyboard actions?

Action class and sendkeys methods

Actions using in advance using apis






