1st prject on world population selenium


package com.Attribute;
import org.openqa.selenium.TakesScreenshot;

import java.awt.AWTException;
import java.awt.Robot;
import java.awt.event.KeyEvent;
import java.io.File;
import java.io.IOException;
import java.time.Duration;
import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.ExpectedCondition;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

import com.google.common.io.Files;

public class BasicDevice {


	  public static void printPopulation(WebDriver driver,String locator) throws InterruptedException {
    	  int count=1;
    	    while(count<=20) {
    	    	System.out.println(count+"sec");
    	    
    	    	if(count==20)
    	    		break;
        	    List<WebElement> currPopulation=driver.findElements(By.xpath(locator));

    	    for(WebElement po:currPopulation) {
    	   	//String pop=po.getText();
    	   	System.out.println(po.getText());
    	    }
    	    Thread.sleep(1000);
    		count++;
    	    }	    	    	
    	  }	    	

public static void main(String[] args) throws InterruptedException, AWTException, IOException {
	
  	  WebDriver driver =new ChromeDriver();
  	  driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
  	  driver.get("https://www.worldometers.info/world-population/");
  	  driver.manage().window().maximize();
  	  
  	  
  	
  	  
  	  String x_path_currPopulation="//div[@class=\"maincounter-number\"]";
   String todayBirth="//span[@rel=\"births_today\"]"; 
  	 String yearBirth="//span[@rel=\"births_this_year\"]";
  	
    
  	 System.out.println("current population");
  	  printPopulation(driver,x_path_currPopulation);
  	  
  	  System.out.println("today birth");
 	  printPopulation(driver,todayBirth);
 	  
 	System.out.println("yearth birth");
  	 printPopulation(driver,yearBirth);
  	
  	 Thread.sleep(3000);
  	TakesScreenshot ts=(TakesScreenshot)driver;
    File src=ts.getScreenshotAs(OutputType.FILE);
   File dest=new File("\\ScreenShot/image.jpg");
   Files.copy(src, dest);

   
   
  	 driver.quit();
  	    }
  	}


  
