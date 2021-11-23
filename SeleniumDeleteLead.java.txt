package week2_day2_assignment;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import io.github.bonigarcia.wdm.WebDriverManager;

public class SeleniumDeleteLead {
	
	public static void main(String[] args) {
		 WebDriverManager.chromedriver().setup(); 
		 ChromeDriver driver = new ChromeDriver();
		 driver.get("http://leaftaps.com/opentaps/control/login");
		 driver.manage().window().maximize();
		 driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		 String tit = driver.getTitle();
		 System.out.println(tit);
		
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
		//11	Capture lead ID of First Resulting lead
		WebElement firstLead = driver.findElement(By.xpath("(//div[@class='x-grid3-cell-inner x-grid3-col-partyId'])[1]/a"));
		String leadId = firstLead.getText();
		System.out.println(leadId);
		//12	Click First Resulting lead
		firstLead.click();
		//13	Click Delete
		driver.findElement(By.linkText("Delete")).click();
		//14	Click Find leads
		driver.findElement(By.linkText("Find Leads")).click();
		//15	Enter captured lead ID
		driver.findElement(By.name("id")).sendKeys(leadId);
		//16	Click find leads button
		driver.findElement(By.xpath("//button[text()='Find Leads']")).click();
		//17 Verify message "No records to display" in the Lead List. This message confirms the successful deletion
		WebElement FinalMessage = driver.findElement(By.xpath("//div[text()='No records to display']"));
		String mesg = FinalMessage.getText();
		System.out.println(mesg);
		if (mesg.equals("No records to display")) {
			System.out.println("This message confirms the successful deletion  SCRIPT PASSED");	
		}else System.out.println("Script Failed");
		//18	Close the browser (Do not log out)*/
		driver.quit();
		}
        }
