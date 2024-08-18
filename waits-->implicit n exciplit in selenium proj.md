//selenium proj
1. wait--> implicit wait and explicit wait

package com.Attribute;

import java.time.Duration;
import java.util.List;
import java.util.Scanner;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

public class BasicDevice {
    public static void main(String[] args) throws InterruptedException {
    	WebDriver driver = new ChromeDriver();
    	
    	
    	//waits--> 1.implicit wait  2. explicity wait
    	
    	//implicit wait
    //	driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
    	
    	
    	//explicit wait
    WebDriverWait mywait=new WebDriverWait(driver,Duration.ofSeconds(10));
    
    
    
        driver.get("https://www.flipkart.com/");
      //  Thread.sleep(2000);
        driver.manage().window().maximize();
       // Thread.sleep(2000);
        
        
        //this is only used where there inteeruption in webelement after declaration of exciplicty wait also.
        //visibilityOfElementLocated has different in type -->like we can use for clicking(login buton) etc.
        WebElement srch=mywait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//input[@placeholder='Search for Products, Brands and More']")));
        srch.sendKeys("iphone12");
        srch.submit();
        
      List<WebElement> items=  driver.findElements(By.xpath("//span[text()='Add to Compare']"));
      
      for(int i=0;i<items.size()-1;i++) {
    	  if(i==0||i==1||i==5||i==8||i==20||i==23) {  //here the product is minimum selected 4 only
    		                                                           //      or
    		                                                    // remove the condition(if) then also it will run clearly             
    	  items.get(i).click();
    	  
    	  }  
    //	Thread.sleep(2000);
      }
      WebElement popup=driver.findElement(By.xpath("//div[text()='You have already selected 4 products']"));
      boolean validate=popup.isDisplayed();
      System.out.println(validate);

      
      driver.quit();
    }
    }
