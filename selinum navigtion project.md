//selinum navigation project
1.access browser
2.aces flipkart
3.maximize the window
4.search for iphone11
5.click on checkbox(apple)
6.click on first product item.



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
     driver.get("https://www.flipkart.com/?affid=affsiteplug&affExtParam1=36b1ab30020ed7105b275bf2ccf29257&affExtParam2=60827");
    Thread.sleep(2000);//waiting for 2 seconds
    
        //window is max,mini
        driver.manage().window().maximize();
        Thread.sleep(2000);
      
       
       //srch for iphone 11
       WebElement srch= driver.findElement(By.xpath("//input[@class=\"Pke_EE\"]"));
       srch.sendKeys("iphone11");
       srch.submit();
       
       //chick on apple check box
      WebElement clickOnAppleCheckbox= driver.findElement(By.xpath("//div[text()='Apple']"));
      clickOnAppleCheckbox.click();
       Thread.sleep(2000);
       
    
      
    //click on image of prd on which after clicking into apple checkbox  
  WebElement clickOnPrd=driver.findElement(By.xpath("//div[@class='KzDlHZ']"));
  clickOnPrd.click();
  
       
     
        
    }
}


