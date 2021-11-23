package week2_day2_assignment;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;

import io.github.bonigarcia.wdm.WebDriverManager;

public class SeleniumCreateLead {
	
	public static void main(String[] args) {
	
		WebDriverManager.chromedriver().setup(); 
		 ChromeDriver driver = new ChromeDriver();
		 driver.manage().window().maximize();
		// 1. Launch URL "http://leaftaps.com/opentaps/control/login"
		 driver.get("http://leaftaps.com/opentaps/control/login");
		 driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		 String tit = driver.getTitle();
		 System.out.println(tit);
		
		 //2. Enter UserName and Password Using Id Locator
		WebElement username = driver.findElement(By.id("username"));
		username.sendKeys("demosalesmanager");
		WebElement password = driver.findElement(By.id("password"));
		password.sendKeys("crmsfa");
		//3. Click on Login Button using Class Locator
		WebElement loginbutton = driver.findElement(By.className("decorativeSubmit"));
		loginbutton.click();
		//4. Click on CRM/SFA Link
	    WebElement text = driver.findElement(By.linkText("CRM/SFA"));
		text.click();
		//5. Click on contacts Button
		driver.findElement(By.linkText("Contacts")).click();
		//6. Click on Create Contact
		driver.findElement(By.linkText("Create Contact")).click();
		//7. Enter FirstName Field Using id Locator
		driver.findElement(By.id("firstNameField")).sendKeys("firstNameField");
		//8. Enter LastName Field Using id Locator
		driver.findElement(By.id("lastNameField")).sendKeys("lastNameField");
		//9. Enter FirstName(Local) Field Using id Locator
		driver.findElement(By.id("createContactForm_firstNameLocal")).sendKeys("createContactForm_firstNameLocal");
		//10. Enter LastName(Local) Field Using id Locator
		driver.findElement(By.id("createContactForm_lastNameLocal")).sendKeys("createContactForm_lastNameLocal");
		//11. Enter Department Field Using any Locator of Your Choice
		driver.findElement(By.id("createContactForm_departmentName")).sendKeys("department");
		//12. Enter Description Field Using any Locator of your choice
		driver.findElement(By.id("createContactForm_description")).sendKeys("this is description");
		//13. Enter your email in the E-mail address Field using the locator of your choice
		driver.findElement(By.id("createContactForm_primaryEmail")).sendKeys("jdjdj@gmail.com");
		//14. Select State/Province as NewYork Using Visible Text
		WebElement Drop1 = driver.findElement(By.id("createContactForm_generalStateProvinceGeoId"));
		Select sele = new Select(Drop1);
		sele.selectByVisibleText("Wyoming");
		//15. Click on Create Contact
		driver.findElement(By.className("smallSubmit")).click();
		//16. Click on edit button
		driver.findElement(By.linkText("Edit")).click();
		//17. Clear the Description Field using .clear
		driver.findElement(By.id("updateContactForm_description")).clear();
		//18. Fill ImportantNote Field with Any text
		driver.findElement(By.id("updateContactForm_importantNote")).sendKeys("important notes");
		//19. Click on update button using Xpath locator
		driver.findElement(By.xpath("//input[@name='submitButton']")).click();
		//20. Get the Title of Resulting Page.
		String title = driver.getTitle();
		System.out.println("title : " +title);
		System.out.print("Script Passed");
		driver.quit();
		
	}

}
