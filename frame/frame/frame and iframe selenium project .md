//selenium project onm frame/iframe-->frame is like webpage and iframe is webpage inside another web page so there is technique to work on both.
//different frame for switching and below used in the program also
//1. driver.switchTo().frame(id);
//2. driver.switchTo().frame(name);
//3. driver.switchTo().frame(WebElement);
//4. driver.switchTo().frame(index);

// for switching from one frame to another frame is
//   --> driver.switchTo().defaultContent();



// there are 3 types
//1.browser window
 driver.switchTo().window();

 //2.alerts
  driver.switchTo().alert();
   driver.switchTo().accept();
    driver.switchTo().dismiss();

 //3.frame--> the above i have declared   



package com.Attribute;

import java.time.Duration;
import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

public class BasicDevice {

    public static void main(String[] args) throws InterruptedException {
        WebDriver driver = new ChromeDriver();
        WebDriverWait myWait = new WebDriverWait(driver, Duration.ofSeconds(50));
        
        driver.get("https://ui.vision/demo/webtest/frames/");
        driver.manage().window().maximize();
                WebElement f2 = driver.findElement(By.xpath("//frame[@src='frame_2.html']"));
        driver.switchTo().frame(f2);
        driver.findElement(By.xpath("//input[@name='mytext2']")).sendKeys("welcome");

        // Switch back to the main page
        driver.switchTo().defaultContent();
        
        WebElement f3 = driver.findElement(By.xpath("//frame[@src='frame_3.html']"));
        driver.switchTo().frame(f3);
        WebElement element = myWait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//input[@name='mytext3']")));
        element.sendKeys("selenium");
        
        driver.switchTo().frame(0);// in frame3 there inside one more page switch by index or id or name or webelement
         // normally perform same operation like how i will apply on different pages--> eg: how i use in top framw3 and frame4
     

        driver.switchTo().defaultContent(); // Switch back to main content if necessary
        
        WebElement f5=driver.findElement(By.xpath("//frame[@src=\"frame_5.html\"]"));
        driver.switchTo().frame(f5);
        driver.findElement(By.xpath("//a[text()='https://a9t9.com']")).click();
        
        WebElement logo=driver.findElement(By.xpath("//a[@id='logo']//img[@alt='UI Vision by a9t9 software - Image-Driven Automation']"));
        logo.isDisplayed();
        System.out.println( logo.isDisplayed());
        
        
        //this is flipkart example logo the above is not working so worlking and checking for it.
//        driver.navigate().to("https://www.flipkart.com/");
//        WebElement logo=driver.findElement(By.xpath("//img[@title='Flipkart']"));
//      
//        System.out.println( logo.isDisplayed());
      
        driver.quit();
    }
}
