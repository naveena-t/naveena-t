package week2_day2_assignment;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;

import io.github.bonigarcia.wdm.WebDriverManager;

public class SeleniumSalesForce {
	
	//SalesForce:
		// Step 1: Download and set the path 
		// Step 2: Launch the chromebrowser
		// Step 3: Load the URL 
		// https://www.salesforce.com/in/form/signup/freetrial-sales/?d=70130000000Enyk
		// Step 4: Maximise the window
		// Step 5: Add implicit wait
		// Step 6: Fill in all the text boxes
		// Step 7: Handle all the dropdowns
		// Step 8: Click the check box
		// Step 9: Close the browser
		//*Note: No need click Start my freeTrial


	public static void main( String[] args) throws Exception {
		
		WebDriverManager.chromedriver().setup();
		
		ChromeDriver driver = new ChromeDriver();
		
		driver.manage().window().maximize();
		
		driver.get("https://www.salesforce.com/in/form/signup/freetrial-sales/?d=70130000000Enyk");
		
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		
		
		driver.findElement(By.name("UserFirstName")).sendKeys("UserFirstName");
		driver.findElement(By.name("UserLastName")).sendKeys("UserLastName");
		driver.findElement(By.name("UserEmail")).sendKeys("hdfsdhg@gmail.com");
		driver.findElement(By.name("CompanyName")).sendKeys("CompanyName");
		driver.findElement(By.name("UserPhone")).sendKeys("7845123685");
		
		WebElement drop1 = driver.findElement(By.name("UserTitle"));
		//Thread.sleep(1000);
		Select sele1 = new Select(drop1);
		sele1.selectByValue("Customer_Service_Manager_AP");
		
		WebElement drop2 = driver.findElement(By.name("CompanyEmployees"));
		//Thread.sleep(1000);
		Select sele2 = new Select(drop2);
		sele2.selectByIndex(3);
		
		WebElement drop3 = driver.findElement(By.name("CompanyCountry"));
		Thread.sleep(1000);
		//drop3.click();
		Select sele3 = new Select(drop3);
		sele3.selectByVisibleText("India");	
		Thread.sleep(1000);
		WebElement drop4 = driver.findElement(By.name("CompanyState"));
		Select sele4 = new Select(drop4);
		sele4.selectByVisibleText("Uttar Pradesh");	
		
	    driver.findElement(By.xpath("//input[@id='SubscriptionAgreement']/following-sibling::div[1]")).click();
		
	    System.out.println(" Execution Passed ");
		driver.quit();
	}

}
