package week2_day2_assignment;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;

import io.github.bonigarcia.wdm.WebDriverManager;

public class SeleniumDropDown {

	public static void main(String[] args) {
		WebDriverManager.chromedriver().setup();
		 ChromeDriver driver = new ChromeDriver();
		 driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		 driver.get("http://www.leafground.com/pages/Dropdown.html");
		 driver.manage().window().maximize();
		 String tit = driver.getTitle();
		 System.out.println(tit);
		 
		 WebElement drop1 = driver.findElement(By.id("dropdown1"));
		 Select sele = new Select(drop1);
		 sele.selectByIndex(4);
		 
		 WebElement drop2 = driver.findElement(By.name("dropdown2"));
		 Select sele1 = new Select(drop2);
		 sele1.selectByValue("4");
		 
		 WebElement drop3 = driver.findElement(By.id("dropdown3"));
		 Select sele2 = new Select(drop3);
		 sele2.selectByVisibleText("Loadrunner");
		 
		 WebElement drop4 = driver.findElement(By.xpath("//select[@class='dropdown']"));
		 Select sele4 = new Select(drop4);
		 sele4.selectByVisibleText("Loadrunner");
		 
		 WebElement drop5 = driver.findElement(By.xpath("(//div[@class='example']/select)[last()-1]"));
		 Select sele5 = new Select(drop5);
		 sele5.selectByIndex(4);
		 
		 WebElement drop6 = driver.findElement(By.xpath("(//div[@class='example']/select)[last()]"));
		 Select sele6 = new Select(drop6);
		 sele6.selectByValue("4");
		 System.out.println("All Drop Down Selected Successfully");
	}
	}
