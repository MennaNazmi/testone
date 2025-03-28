"# testone" 
hihihi

Day 28 assignment

Day 29 checkboxes
create new package 
create ne class

WebDriver driver=new CChromeDriver();
driver.get("dd");
driver.manage().window().maximize();
//select secific checkbox
driver.findElement(By.xpath("//input[@id='sunday']")).click();
//select all checkboxes by searching for the common locators
List <webElement> checkboxes = driver.findElements(By.xpath('input[@class='form-check-input' and type='checkbox']'))
//input[@class='form-check-input' and @type='checkbox']
for (int i = 0;i<checkboxes.size();i++){
checkboxes.get(i).click();
}
===normal for loop or enhanced for loop
for (WebElement checkbox:checkboxes){
checkbox.click();
}
//select last 3 checkboxes-->total -3= starting index
for (int i=4;i<checkboxes.size();i++ ){
checkboxes.get(i).click();
}
=====//select first 3 checkboxes
for(int i=0;i<3;i++){
checkboxes.get(i).click();
}
====//unselect checkboxes if ther are selected
for (WebElement checkbox: checkboxes)
{
checkbox.click();
}

Thread.sleep(5000)

for(int i=0;i<checkboxes.size();i++){
if (checkboxes.get(i).isSeleccted()){
checkboxes.get(i).click();
}
}
============================
====================Alerts/Popups
//normal alert-->ok
//confirmation alert--> ok , cancel
//prompt alaert--> text , ok, cancel
alert is not a webElement so u cannot inspect any thing

creaet new class:
	WebDriver driver=new ChromeDriver();
	driver.get("");
	driver.manage().window().maximize();
	//normal alert--ok
	driver.findElement(By.xpath("//button..")).click();
	Thread.sleep(2000);
	Alert mylert=driver.switchTo().alert();
	mylert.getText();
	System.out.println(mylert.getText());
	mylert.accept();
	
	//confirmation alert-- ok,cancel
	
	driver.findElement(By.xpath("//button..")).click();
	Thread.sleep(2000);
	Alert mylert=driver.switchTo().alert();
	mylert.getText();
	System.out.println(mylert.getText());
	mylert.dismiss();
	// prompt
	
	driver.findElement(By.xpath("//button..")).click();
	Thread.sleep(2000);
	Alert myprompt=driver.switchTo().alert();
	myprompt.sendKeys("welcome");
	System.out.println(mylert.getText());
	myprompt.accept();
	
	//i dont wanna use switchTo 
	//using exciplict wait 
	
	WebDriverWait mywait= new WebDriverWait(driver,Duration.odSeconds(10));
	
	Alert myalert=mywait.until(ExpectedCondtions.alertIsPresent)//return alert into var
	
	//authenticated popup
	//inject usename and pass in url   http://username:password@the-ni.com/sdf
	
	assignment day29 
	checkboxes
	pop up
	
	
===============================================	
===============Day30===frames/iframes============================
WebElement frame1 driver.findElement(By.xpath("//frame[@src='']"));
driver.switchTo().frame(frame1)
//driver.switchTo().frame(name/id/webelement/index)//index if we have 1 single frame
driver.findElement("//input[@name='txt']")).sendKeys("welcom")


driver.switchTo().defaultContent() //to go the page then frame 2 we cannot move from frame1 to antoher frame
