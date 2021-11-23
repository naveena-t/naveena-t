package week2_day2_assignment;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.Dimension;
import org.openqa.selenium.Keys;
import org.openqa.selenium.Point;
import org.openqa.selenium.chrome.ChromeDriver;

import io.github.bonigarcia.wdm.WebDriverManager;

public class SeleniumButtonsHandle {

	public static void main(String[] args) {
		
		WebDriverManager.chromedriver().setup();
		
		ChromeDriver driver = new ChromeDriver();
		
		driver.get("http://leafground.com/pages/Button.html");
		
		driver.manage().window().maximize();
		
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		
		//Find position of button (x,y)
		Point location = driver.findElement(By.id("position")).getLocation();
		System.out.println( "Button Position of x,y = "+location);
		
		//Find button color
		
		String cssValue = driver.findElement(By.id("color")).getCssValue("background-color");
		System.out.println("Color RGBA Value " +cssValue);
		
		
		//Find the height and width
		Dimension siz = driver.findElement(By.id("size")).getSize();
		System.out.println("SIze of the element" +siz);
		
		//Click button to travel home page
		
		driver.findElement(By.id("home")).click();
		String currentUrl = driver.getCurrentUrl();
		System.out.println(currentUrl);
		System.out.println(driver.getTitle());
	}

}
