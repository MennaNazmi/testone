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

