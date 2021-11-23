package week4_Day1_assignments;

import static org.testng.Assert.assertEquals;

import java.io.File;
import java.time.Duration;
import java.util.ArrayList;
import java.util.List;
import java.util.Set;

import org.apache.commons.io.FileUtils;
import org.openqa.selenium.Alert;
import org.openqa.selenium.By;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;

import io.github.bonigarcia.wdm.WebDriverManager;

public class SeleniumWindowHandleMergeContacts {
	

	public static void main(String[] args) throws Exception {
		
		WebDriverManager.chromedriver().setup();
		
		ChromeDriver driver = new ChromeDriver();
		
		driver.get("http://leaftaps.com/opentaps/control/login");
		
		driver.manage().window().maximize();
		
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		
		//2. Enter UserName and Password Using Id Locator
				WebElement username = driver.findElement(By.id("username"));
				username.sendKeys("demosalesmanager");
				System.out.println(username.getText());
				
		    	WebElement password = driver.findElement(By.id("password"));
				password.sendKeys("crmsfa");
	
		//3. Click on Login Button using Class Locator
		WebElement loginbutton = driver.findElement(By.className("decorativeSubmit"));
		loginbutton.click();
		
		 // 4. Click on CRM/SFA Link
		WebElement text = driver.findElement(By.linkText("CRM/SFA"));
		text.click();
		
		//5. Click on contacts Button
				driver.findElement(By.linkText("Contacts")).click();
				
				
				
		//6. Click on Merge Contacts using Xpath Locator
				driver.findElement(By.linkText("Merge Contacts")).click();
				
		// 7. Click on Widget of From Contact	
				driver.findElement(By.xpath("(//img[@alt='Lookup'])[1]")).click();
				
				Set<String> windowHandles = driver.getWindowHandles();
				List<String> win = new ArrayList<String>(windowHandles);
				driver.switchTo().window(win.get(1));
				System.out.println("switched to first window");
				
				
				
		//  8. Click on First Resulting Contact		
				driver.findElement(By.xpath("(//div[@class='x-grid3-cell-inner x-grid3-col-firstName']/a)[1]")).click();
				
				driver.switchTo().window(win.get(0));
				System.out.println("switched to parent window");
				
		//9. Click on Widget of To Contact
				driver.findElement(By.xpath("(//img[@alt='Lookup'])[2]")).click();
				Set<String> windowHandles1 = driver.getWindowHandles();
				List<String> win1 = new ArrayList<String>(windowHandles1);
				driver.switchTo().window(win1.get(1));

				
		//10. Click on Second Resulting Contact		
				driver.findElement(By.xpath("(//div[@class='x-grid3-cell-inner x-grid3-col-firstName']/a)[2]")).click();
				driver.switchTo().window(win1.get(0));
								System.out.println("switched to parent window");
				
		// 11. Click on Merge button using Xpath Locator
				
				driver.findElement(By.linkText("Merge")).click();
				
		// 12. Accept the Alert
				
				Alert alert = driver.switchTo().alert();  alert.accept();
				System.out.println("Alert handled");
				
		// * 13. Verify the title of the page
				
				String title = driver.getTitle();
				Assert.assertEquals(title, "View Contact | opentaps CRM");
				
				//ScreenSHot code
				
				File src = driver.getScreenshotAs(OutputType.FILE);
				File dest = new File("./Snaps/Passed.jpg");
				FileUtils.copyFile(src, dest);
				
				
				
				
				System.out.println("Script Passed");
				
				driver.quit();
				
				
				
				
				
	}           

}
