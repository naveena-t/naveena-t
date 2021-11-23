package week2_day1_session;



import org.apache.poi.util.SystemOutLogger;
import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import io.github.bonigarcia.wdm.WebDriverManager;



public class SeleniumCreateLead {
	 
	
	public static void main(String[] args) {
		 WebDriverManager.chromedriver().setup(); 
		 ChromeDriver driver = new ChromeDriver();
		 driver.get("http://leaftaps.com/opentaps/control/main");
		 driver.manage().window().maximize();
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
		
		driver.findElement(By.linkText("Create Lead")).click();
		
		driver.findElement(By.id("createLeadForm_companyName")).sendKeys("Name");
		driver.findElement(By.id("createLeadForm_firstName")).sendKeys("Name");
		WebElement firstname = driver.findElement(By.id("createLeadForm_firstName"));
		System.out.println(firstname.getText());
		driver.findElement(By.id("createLeadForm_birthDate")).sendKeys("09/15/21");
		driver.findElement(By.id("createLeadForm_lastName")).sendKeys("LastName");
		driver.findElement(By.id("createLeadForm_primaryPhoneCountryCode")).clear();
		driver.findElement(By.id("createLeadForm_primaryPhoneCountryCode")).sendKeys("23");
		
		
		driver.findElement(By.id("createLeadForm_primaryPhoneAreaCode")).sendKeys("0411");
		driver.findElement(By.id("createLeadForm_primaryPhoneExtension")).sendKeys("85214796325");
		driver.findElement(By.id("createLeadForm_primaryEmail")).sendKeys("jackjones@gmail.com");
		driver.findElement(By.id("createLeadForm_primaryPhoneNumber")).sendKeys("985236412");
		driver.findElement(By.id("createLeadForm_primaryPhoneAskForName")).sendKeys("PrimaryName");
		driver.findElement(By.id("createLeadForm_primaryWebUrl")).sendKeys("23");
		
		
		
		driver.findElement(By.id("createLeadForm_generalToName")).sendKeys("ToName");
		driver.findElement(By.id("createLeadForm_generalAddress1")).sendKeys("Address1");
		driver.findElement(By.id("createLeadForm_generalStateProvinceGeoId")).sendKeys("Alabama");
		driver.findElement(By.id("createLeadForm_generalCity")).sendKeys("GeneralCity");
		driver.findElement(By.id("createLeadForm_generalPostalCode")).sendKeys("641006");
		driver.findElement(By.id("createLeadForm_generalPostalCodeExt")).sendKeys("789562314");
		driver.findElement(By.id("createLeadForm_generalAttnName")).sendKeys("AttnName");
		driver.findElement(By.id("createLeadForm_generalAddress2")).sendKeys("Address2");
		
		driver.findElement(By.className("smallSubmit")).click();
        
		String title = driver.getTitle();
		System.out.println(title);
		
}		
		
		

	}


