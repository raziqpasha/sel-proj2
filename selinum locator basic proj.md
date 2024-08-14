//SELINUM LOCATORS

package section1;

import java.util.List;
import java.util.Random;
import org.openqa.selenium.By;
import org.openqa.selenium.Dimension;
import org.openqa.selenium.Point;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class LaunchingBrowser {

    public static   void main(String[] args) throws InterruptedException {
        // Set up WebDriver
        WebDriver driver = new ChromeDriver();
        
        //access flipkart app
     driver.get("https://demo.opencart.com/");
    Thread.sleep(2000);//waiting for 2 seconds
    
        //window is max,mini
        driver.manage().window().maximize();
        Thread.sleep(2000);
      
       // LOCATORS
        //1. locator By name
      driver.findElement(By.name("search")).sendKeys("oppo");
      
      
      //2. locator By id
      boolean categoryLogo= driver.findElement(By.id("category")).isDisplayed();
    System.out.println(categoryLogo);
    
    //3. locator by classname
   List<WebElement> totalNoOfWebLink=driver.findElements(By.className("list-inline-item"));
   System.out.println(totalNoOfWebLink.size());
    
   //locators By tagname
   WebElement buttn = driver.findElement(By.tagName("Privacy Policy"));
  buttn.click();
  
  //linktext
 // driver.findElement(By.linkText(""))
 
  
  //partial linktext
//  driver.findElement(By.partialLinkText(""))
       
     
        
    }
}


