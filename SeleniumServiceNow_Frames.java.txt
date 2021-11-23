package week4_Day1_assignments;

import java.io.File;
import java.io.IOException;
import java.time.Duration;
import java.util.ArrayList;
import java.util.List;
import java.util.Set;

import org.apache.commons.io.FileUtils;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;

import io.github.bonigarcia.wdm.WebDriverManager;

public class SeleniumServiceNow_Frames {
	
	
	
	

	
	
	/*Step1: Load ServiceNow application URL 
	
	
	
	Step5: Search “incident “ Filter Navigator
	Step6: Click “All”
	Step7: Click New button
	
	Step9: Read the incident number and save it a variable
	Step10: Click on Submit button
	Step 11: Search the same incident number in the next search screen as below
	Step12: Verify the incident is created successful and take snapshot of the created incident. */


	public static void main(String[] args) throws Exception {
		
		//ChromeDriver driver = new ChromeDriver();
		WebDriverManager.chromedriver().setup();	
		ChromeDriver driver = new ChromeDriver();
		
		driver.get("https://dev78662.service-now.com");
		
		driver.manage().window().maximize();
		
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(20));
		
		
		
		// Step2: Enter username (Check for frame before entering the username)
		WebElement frame = driver.findElement(By.id("gsft_main"));
		driver.switchTo().frame(frame);
		System.out.println("Switched into frame");
		driver.findElement(By.id("user_name")).sendKeys("admin");
		//Step3: Enter password 
		driver.findElement(By.id("user_password")).sendKeys("b5qCikfG5EDH");
	//	Step4: Click Login
		driver.findElement(By.id("sysverb_login")).click();
		
		driver.switchTo().defaultContent();
		System.out.println("Came out of frame");
		
		driver.findElement(By.id("filter")).sendKeys("incident");
		
		driver.findElement(By.xpath("(//div[text()='All' and @class='sn-widget-list-title'])[2]")).click();
		
		
		WebElement frame1 = driver.findElement(By.id("gsft_main"));
		driver.switchTo().frame(frame1);
		System.out.println("Again switched to frame");
		driver.findElement(By.id("sysverb_new")).click();
		//Step8: Select a value for Caller and Enter value for short_description
		driver.findElement(By.id("lookup.incident.caller_id")).click();
		
		driver.switchTo().defaultContent();
		System.out.println("Again Came out of frame"); 
		
		     	Set<String> windowHandles = driver.getWindowHandles();
				List<String> win = new ArrayList<String>(windowHandles);
				driver.switchTo().window(win.get(1));
				
		        driver.findElement(By.xpath("(//a[@role='button' and @class='glide_ref_item_link'])[1]")).click();		
		        
		        driver.switchTo().window(win.get(0));
				
		        WebElement frame3 = driver.findElement(By.id("gsft_main"));
				driver.switchTo().frame(frame3);
				System.out.println("Again switched to frame");
				
			
				driver.findElement(By.id("incident.short_description")).sendKeys("ashdjhasgdjhasd");
				//incident.number
				
				String inc = driver.findElement(By.id("sys_original.incident.number")).getAttribute("value");
				System.out.println("Incident Number" +inc);
				
				driver.findElement(By.id("incident.short_description")).sendKeys("ashdjhasgdjhasd");
				
				driver.findElement(By.id("sysverb_insert_bottom")).click();
				

				
				driver.findElement(By.xpath("//input[@placeholder='Search' and @class='form-control']")).sendKeys(inc,Keys.ENTER);
				
				String inc2 = driver.findElement(By.xpath("//a[@class='linked formlink']")).getText();
				System.out.println(inc2);
				System.out.println(inc);
				
				Assert.assertEquals(inc2,inc);
				
				File src = driver.getScreenshotAs(OutputType.FILE);
				File dest = new File("./Snaps/IncidentCreatedSuccess.png");
				FileUtils.copyFile(src, dest);
				
				System.out.println("Incident Created - Script passed");
				
				driver.quit();
				
				
				
				
	
		
		
		
		
		
		
		
	}

}
