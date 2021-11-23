package week2_day2_assignment;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.chrome.ChromeDriver;

import io.github.bonigarcia.wdm.WebDriverManager;

public class SeleniumEditTextBoxes {

	public static void main(String[] args) {
		
		WebDriverManager.chromedriver().setup();
		
		ChromeDriver driver = new ChromeDriver();
		
		driver.get("http://leafground.com/pages/Edit.html");
		
		driver.manage().window().maximize();
		
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		
		driver.findElement(By.id("email")).sendKeys("email@gmail.com");
		
		driver.findElement(By.xpath("(//input[@type='text'])[2]")).sendKeys("textadded");
		driver.findElement(By.xpath("(//input[@type='text'])[2]")).sendKeys(Keys.TAB);
		
		String Attri = driver.findElement(By.xpath("(//input[@type='text'])[3]")).getAttribute("value");
		System.out.println("Default value "+Attri);
		if (Attri.contains("TestLeaf")) {
		System.out.println("Default value displayed");	
		} else System.out.println("No default value entered");
		
		driver.findElement(By.xpath("(//input[@type='text'])[4]")).clear();
		
		boolean enab = driver.findElement(By.xpath("(//input[@type='text'])[5]")).isEnabled();
		
		if (enab) {
			System.out.println(" Text box is Enabled and can enter text values ");	
			} else System.out.println("Text box is disabled status");

		System.out.println("Validation Passed");
		
		driver.quit();
		

	}

}
