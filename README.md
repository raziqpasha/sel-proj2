//selinum project 
1.launch broswer
2.acess fli[kart browser
3.maximize browser
search for 1phone12


package section1;

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

    }
}

