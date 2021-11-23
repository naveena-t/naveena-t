package week2_day2_assignment;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import io.github.bonigarcia.wdm.WebDriverManager;

public class SeleniumEditLead {
	/*http://leaftaps.com/opentaps/control/main
	
	* 1	Launch the browser
	* 2	Enter the username
	* 3	Enter the password
	* 4	Click Login
	* 5	Click crm/sfa link
	* 6	Click Leads link
	* 7	Click Find leads
	
	* 9	Click Find leads button
	* 10 Click on first resulting lead
	* 
	* 12 Click Edit
	
	
	* 15 Confirm the changed name appears
	* 16 Close the browser (Do not log out)
*/
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
		
String hrf = driver.findElement(By.linkText("Leads")).getAttribute("href");
System.out.println("Attribute href value = " +hrf);


		
	//6	Click Leads link
				driver.findElement(By.linkText("Leads")).click();
		//7	Click Find leads
				driver.findElement(By.linkText("Find Leads")).click();
		// 8	Enter first name
				driver.findElement(By.xpath("(//input[@name='firstName'])[last()]")).sendKeys("sathya");	
		// 9	Click find leads button
				driver.findElement(By.xpath("//button[text()='Find Leads']")).click();
				Thread.sleep(5000);	
		//10 Click on first resulting lead		
	      WebElement firstLead = driver.findElement(By.xpath("(//div[@class='x-grid3-cell-inner x-grid3-col-firstName']/a)[1]"));
				String leadName = firstLead.getText();
				System.out.println(leadName);
				firstLead.click();
		//11 Verify title of the page
				String EditTitle = driver.getTitle();
				System.out.println(EditTitle);
        //12 Click Edit
				driver.findElement(By.xpath("//a[text()='Edit']")).click();
				
			//	* 13 Change the company name
				driver.findElement(By.id("updateLeadForm_companyName")).clear();
				driver.findElement(By.id("updateLeadForm_companyName")).sendKeys("NewCompanyName");
			
			//	* 14 Click Update	
				driver.findElement(By.xpath("//input[@type='submit' and @name='submitButton']")).click();
		
				
				
				String NewCmpnyName = driver.findElement(By.id("viewLead_companyName_sp")).getText();
				System.out.println(NewCmpnyName);
				if (NewCmpnyName.contains("NewCompanyName")) {
					System.out.println("Company Name Updated - Scriprt Passed");
				}else System.out.println("Script Failed Company Name Not Updated");
			driver.quit();	
	}           

}
