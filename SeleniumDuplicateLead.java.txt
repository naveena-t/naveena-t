package week2_day2_assignment;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import io.github.bonigarcia.wdm.WebDriverManager;

public class SeleniumDuplicateLead {
	public static void main(String[] args) throws Exception {
		
		WebDriverManager.chromedriver().setup();
		ChromeDriver driver = new ChromeDriver();
		//1	Launch the browser
		driver.get("http://leaftaps.com/opentaps/control/main");
		driver.manage().window().maximize();
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		
		WebElement username = driver.findElement(By.id("username"));
		username.sendKeys("demosalesmanager");
		WebElement password = driver.findElement(By.id("password"));
		password.sendKeys("crmsfa");
		WebElement loginbutton = driver.findElement(By.className("decorativeSubmit"));
		loginbutton.click();
	    WebElement text = driver.findElement(By.linkText("CRM/SFA"));
		text.click();
		
		//6	Click Leads link
				driver.findElement(By.linkText("Leads")).click();
		//7	Click Find leads
				driver.findElement(By.linkText("Find Leads")).click();
		//8	Click on Email
			driver.findElement(By.xpath("//span[text()='Email']")).click();
		//9	Enter Email 
			driver.findElement(By.name("emailAddress")).sendKeys("testleaf@gmail.com");
		//10	Click find leads button
				driver.findElement(By.xpath("//button[text()='Find Leads']")).click();
				Thread.sleep(5000);
		//11	Capture name of First Resulting lead
				 
        WebElement firstLead = driver.findElement(By.xpath("(//div[@class='x-grid3-cell-inner x-grid3-col-firstName']/a)[1]"));
		String leadName = firstLead.getText();
		System.out.println(leadName);
		//12	Click First Resulting lead
		firstLead.click();			
//		//13	Click Duplicate Lead
	driver.findElement(By.linkText("Duplicate Lead")).click();
		//14	Verify the title as 'Duplicate Lead'
		String DuplicateTitle = driver.getTitle();
		System.out.println(DuplicateTitle);
		String duplicateHeader = driver.findElement(By.xpath("//div[@class='frameSectionExtra']/preceding-sibling::div")).getText();
		System.out.println(duplicateHeader);
		//15	Click Create Lead
		driver.findElement(By.xpath("//input[@type='submit' and @name='submitButton']")).click();
		//16	Confirm the duplicated lead name is same as captured name
		String createdName = driver.findElement(By.id("viewLead_firstName_sp")).getText();
		System.out.println(createdName);
		if (createdName.equals(leadName)) {
			System.out.println("Duplicate created - Scriprt Passed");
		}else System.out.println("Script Failed Duplicate name mismatched");
		
		driver.quit();
	}

}
