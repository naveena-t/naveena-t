package week4_Day1_assignments;

import static org.testng.Assert.assertEquals;

import java.time.Duration;
import java.util.ArrayList;
import java.util.List;
import java.util.Set;

import org.openqa.selenium.Alert;
import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;
import org.testng.Assert;

import io.github.bonigarcia.wdm.WebDriverManager;

public class FrameHandleAssignement3 {
	

	public static void main(String[] args) throws Exception {
		
		WebDriverManager.chromedriver().setup();
		
		ChromeDriver driver = new ChromeDriver();
		
		driver.get("https://chercher.tech/practice/frames-example-selenium-webdriver");
		
		driver.manage().window().maximize();
		
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		
		WebElement frame1 = driver.findElement(By.id("frame1"));
		
		driver.switchTo().frame(frame1);
		
		driver.findElement(By.xpath("//input[@type='text']")).click();
		
		
        WebElement frame2 = driver.findElement(By.id("frame3"));
		
		driver.switchTo().frame(frame2);
		
		driver.findElement(By.id("a")).click();
		
		driver.switchTo().parentFrame();
		
		driver.findElement(By.xpath("//input[@type='text']")).sendKeys("MAss");
		
		
		
		
		driver.switchTo().defaultContent();
//		
//		
        WebElement frame3 = driver.findElement(By.id("frame2"));
		
		driver.switchTo().frame(frame3);
		
		WebElement drop = driver.findElement(By.id("animals"));
		Select select = new Select(drop);
		select.selectByVisibleText("Big Baby Cat");
		
		driver.quit();
				
				
	}           

}
