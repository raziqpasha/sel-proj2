//selnium project 3
1.access to browser
2.acess flipkart webpage
3.maximize the window
4.donot minimize bcz once u minimize the window it will close enteir the browser which will be cureently in execution or else after writing all ur scripts use minimize //driver.manage().window().minimize();
//and thread.sleep(seconds) as per now if ur in beinging stages of learning selnium think that it very to use important for browser to acess the remaining scripts.
5.click on "add tp compare" check box // the maximum it will compare 4 product in flipkart ,check in other different webpages like amazon,myntra etc it will be more or less products can be compared.
6.then print the compared element is true or false.

package section1;

import java.util.List;
import java.util.Random;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class LaunchingBrowser {

    public static void main(String[] args) throws InterruptedException {
        // Set up WebDriver
        WebDriver driver = new ChromeDriver();
        driver.get("https://www.flipkart.com/");
        Thread.sleep(2000);
        driver.manage().window().maximize();
        Thread.sleep(2000);
        
        WebElement search=driver.findElement(By.xpath("//input[@class=\"Pke_EE\"]"));
        search.sendKeys("iphone12");
       
        
        search.submit();
        
      List<WebElement> items=  driver.findElements(By.xpath("//span[text()='Add to Compare']"));
      
      for(int i=0;i<items.size()-1;i++) {
    	  if(i==0||i==1||i==5||i==items.size()||i==21||i==3) {  //here the product is minimum selected 4 only
    		                                                           //      or
    		                                                    // remove the condition(if) then also it will run clearly             
    	  items.get(i).click();
    	  
    	  Thread.sleep(2000);
    	  }  
      }
      WebElement popup=driver.findElement(By.xpath("//div[text()='You have already selected 4 products']"));
      boolean validate=popup.isDisplayed();
      System.out.println(validate);

    }
}

