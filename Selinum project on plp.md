
// selinum project
1.launch browser
2.access flipkart application
3.search for iphone11
4.click on price low to high
5.fetch all product name(pdp->product list page)

package section1;

import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class LaunchingBrowser {

	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub
		WebDriver driver=new ChromeDriver();
		driver.get("https://www.flipkart.com/");
		Thread.sleep(2000);
	driver.manage().window().maximize();
	Thread.sleep(2000);
		WebElement srch=driver.findElement(By.xpath("//input[@class=\"Pke_EE\"]"));
		Thread.sleep(2000);
		srch.sendKeys("iphone11");
		Thread.sleep(2000);
		srch.submit();
		Thread.sleep(2000);
	//	//driver.navigate().to("https://www.flipkart.com/search?q=iphone11&otracker=search&otracker1=search&marketplace=FLIPKART&as-show=on&as=off&sort=price_asc");
		WebElement plh=driver.findElement(By.xpath("//div[text()='Price -- Low to High']"));
		plh.click();
		
		Thread.sleep(2000);
	List <WebElement> txt=	driver.findElements(By.xpath("//div[@class=\"KzDlHZ\"]"));
	for(WebElement alltxt:txt) {
		System.out.println(alltxt.getText());
	}
		
