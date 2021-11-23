package week2_day2_assignment;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;

import io.github.bonigarcia.wdm.WebDriverManager;

public class SeleniumFaceBook {
	
	//Assignment 2
	//FaceBook:
	//================================
	
	 
	// ( A normal click will do for this step) 


	public static void main(String[] args) {
	// Step 1: Download and set the path 	
		WebDriverManager.chromedriver().setup();
		// Step 2: Launch the chromebrowser
		ChromeDriver driver = new ChromeDriver();
		// Step 3: Load the URL https://en-gb.facebook.com/		
		driver.get("https://en-gb.facebook.com/");
		// Step 4: Maximise the window
		driver.manage().window().maximize();
		// Step 5: Add implicit wait
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		// Step 6: Click on Create New Account button
		driver.findElement(By.linkText("Create New Account")).click();
		// Step 7: Enter the first name
		driver.findElement(By.name("firstname")).sendKeys("FirstName");
		// Step 8: Enter the last name
		driver.findElement(By.name("lastname")).sendKeys("LastName");
		// Step 9: Enter the mobile number
		driver.findElement(By.name("reg_email__")).sendKeys("9894854588");
		// Step 10: Enter the password
		driver.findElement(By.name("reg_passwd__")).sendKeys("password");
		// Step 11: Handle all the three drop downs
		WebElement Drop1 = driver.findElement(By.id("day"));
		Select Select1 = new Select(Drop1);
		Select1.selectByVisibleText("31");
		WebElement Drop2 = driver.findElement(By.id("month"));
		Select sele2 = new Select(Drop2);
		sele2.selectByIndex(11);
		WebElement Drop3 = driver.findElement(By.id("year"));
		Select sele3 = new Select(Drop3);
		sele3.selectByValue("1996");
		// Step 12: Select the radio button "Female"
		driver.findElement(By.xpath("//label[text()='Female']")).click();
		//driver.quit();
		
		
		
		
		
	}

}
