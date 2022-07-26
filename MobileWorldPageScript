import java.util.Iterator;
import java.util.List;
import java.util.Set;


import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;

public class MobileWorldPage {
	public WebDriver driver;

	@BeforeMethod
	public void setUp() {
		System.setProperty("webdriver.chrome.driver",
				"C:\\Users\\prasanth.yesupogu\\Downloads\\Drivers\\chromedriver.exe");
		driver = new ChromeDriver();
		driver.get("https://mobileworld.azurewebsites.net/");
		driver.manage().window().maximize();
		
	}

	@Test(priority = 1)
	public void register() throws InterruptedException {
		driver.findElement(By.cssSelector(".btn.btn-warning.my-2.my-sm-0")).click();
		driver.findElement(By.linkText("Sign up")).click();
		driver.findElement(By.xpath("//input[@placeholder='First Name']")).sendKeys("prasanth");
		driver.findElement(By.xpath("//input[@placeholder='Last Name']")).sendKeys("Kumar");
		driver.findElement(By.xpath("//input[@placeholder='Enter Email']")).sendKeys("prasanth@gmail.com");
		driver.findElement(By.xpath("//input[@placeholder='Password']")).sendKeys("Kumar@1234");
		driver.findElement(By.xpath("//input[@type='date']")).sendKeys("06/19/1998");

		List<WebElement> gender = driver.findElements(By.name("gender"));
		gender.get(0).click();
		driver.findElement(By.xpath("//input[@type='number']")).sendKeys("9705754556");
		driver.findElement(By.xpath("//textarea[@placeholder='Short Bio']"))
				.sendKeys("My self Prashanth i want to buy a mobile in this page");
		// driver.findElement(By.xpath("//button[text()='Register']")).click();
		// System.out.println(driver.switchTo().alert().getText());
		// driver.switchTo().alert().accept();
		Thread.sleep(1000);
		driver.findElement(By.xpath("//button[text()='Sign In']")).click();

		System.out.println(driver.switchTo().alert().getText());
		driver.switchTo().alert().accept();
		
		
	}

	@Test(priority = 2)
	public void signIn() throws InterruptedException {
		// SignIn Functionality
		driver.findElement(By.xpath("//button[text()='SIGN IN']")).click();
		driver.findElement(By.id("username")).sendKeys("prashanth");
		driver.findElement(By.id("password")).sendKeys("prasanth123");
		driver.findElement(By.linkText("Log In")).click();

		// Selecting a Mobile and ordering functionality
		driver.findElement(By.linkText("All Mobiles")).click();
		driver.findElement(By.xpath("//tbody[@id='myTable']/tr[2]/td[5]/a")).click();

		// Moving to the child Tab
		Set<String> windows = driver.getWindowHandles();
		Iterator<String> it = windows.iterator();
		String parentId = it.next();
		String childId = it.next();
		driver.switchTo().window(childId);

		// Filling the order page
		List<WebElement> listname = driver.findElements(By.id("inputFirstName"));
		listname.get(0).sendKeys("Prashanth");
		listname.get(1).sendKeys("Kumar");
		driver.findElement(By.id("inputEmail")).sendKeys("test@gmail");
		driver.findElement(By.id("inputPassword")).sendKeys("prashanth123");
		driver.findElement(By.id("flexRadioDefault1")).click();
		driver.findElement(By.xpath("//input[@placeholder='00000000000']")).sendKeys("9705730561");
		driver.findElement(By.id(" address1")).sendKeys("Madupalli");
		driver.findElement(By.id("address2")).sendKeys("Madhira");
		driver.findElement(By.id("inputCity")).sendKeys("Khammam");

		WebElement ele = driver.findElement(By.id("inputState"));
		Select sc = new Select(ele);
		sc.selectByVisibleText("Goa");
		driver.findElement(By.id("inputZip")).sendKeys("507203");

		JavascriptExecutor js = (JavascriptExecutor) driver;
		js.executeScript("window.scrollBy(0,450)");

		driver.findElement(By.xpath("//input[@rel='samsung']")).click();
		driver.findElement(By.xpath("//input[@rel='apple']")).click();

		WebElement model = driver.findElement(By.xpath("//div[@class='apple']/select"));
		Select sc1 = new Select(model);
		sc1.selectByIndex(1);

		driver.findElement(By.xpath("//input[@placeholder='no of mobiles']")).sendKeys("20");
		WebElement howMany = driver.findElement(By.id("bought"));
		Select sc2 = new Select(howMany);
		sc2.selectByIndex(1);

		List<WebElement> listele = driver.findElements(By.id("gridCheck1"));
		listele.get(0).click();
		listele.get(1).click();

		driver.findElement(By.xpath("//button[@type='button']")).click();
		Thread.sleep(2000);
		System.out.println(driver.findElement(By.cssSelector(".modal-body")).getText());
		System.out.println("Raised a Ticket");
	

	}

	@Test(priority = 3)
	public void contactUs() {

		driver.findElement(By.id("navbarDropdown")).click();
		driver.findElement(By.linkText("Contact Us")).click();

		Set<String> windows = driver.getWindowHandles();
		Iterator<String> it = windows.iterator();
		String parentId = it.next();
		String childId = it.next();
		driver.switchTo().window(childId);
		driver.manage().window().maximize();

		driver.findElement(By.xpath("//input[@placeholder='Username']")).sendKeys("prasanth");
		driver.findElement(By.xpath("//input[@placeholder='Email']")).sendKeys("prasanth@gmail.com");
		driver.findElement(By.xpath("//input[@placeholder='Phone']")).sendKeys("9705752445");
		driver.findElement(By.xpath("//textarea[@placeholder='Message']"))
				.sendKeys("Hai myself prashanth iam facing an issue regarding the mobiles");
		driver.findElement(By.xpath("//input[@value='Send']")).click();		
		

	}

	@AfterMethod
	public void exit() {
		driver.quit();
	}

}
