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


practice day 45:



