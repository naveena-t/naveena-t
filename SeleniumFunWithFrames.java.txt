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
import org.testng.Assert;

import io.github.bonigarcia.wdm.WebDriverManager;

public class SeleniumFunWithFrames {
	

	public static void main(String[] args) throws Exception {
		
		WebDriverManager.chromedriver().setup();
		
		ChromeDriver driver = new ChromeDriver();
		
		driver.get("http://leafground.com/pages/frame.html");
		
		driver.manage().window().maximize();
		
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		
	
		
		driver.switchTo().frame(0);
		driver.findElement(By.id("Click")).click();
		driver.switchTo().defaultContent();
		
		driver.switchTo().frame(1);
		
		WebElement fra = driver.findElement(By.id("frame2"));
		driver.switchTo().frame(fra);
		driver.findElement(By.id("Click1")).click();
		driver.switchTo().defaultContent();
		
		
		List<WebElement> totalfr = driver.findElements(By.xpath("//iframe"));
		System.err.println("Total Frame " +totalfr.size());
		
		
		
				
				
	}           

}
