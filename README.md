 selenium project on ALERT POP-UPS
1.ok btn
2.cancel n ok btn
3.can send msg in text feild , alert  ok and cancel btn


package com.Attribute;

import java.time.Duration;
import java.util.List;

import org.openqa.selenium.Alert;
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
        WebDriverWait mywait = new WebDriverWait(driver, Duration.ofSeconds(20));
        
        driver.get("https://testpages.eviltester.com/styled/alerts/alert-test.html");
        
        //pop with OK button
//       WebElement al= driver.findElement(By.xpath("//input[@value=\"Show alert box\"]"));
//       al.click();
//       Alert myalert= driver.switchTo().alert();
//       System.out.println(myalert.getText());
//       myalert.accept();
        
        
      //pop with OK button and CANCEL button
//      WebElement al= driver.findElement(By.xpath("//input[@value='Show confirm box']"));
//      al.click();
//      Alert myalert=driver.switchTo().alert();
//   System.out.println(myalert.getText());
 //  myalert.accept();  // this is for OK button
//   Thread.sleep(5000);
//   myalert.dismiss();    // this is for CANCEL button

      
        //pop with OK button and CANCEL button--> and in text box can be writen also
//      WebElement al= driver.findElement(By.xpath("//input[@value=\"Show prompt box\"]"));
//      al.click();
//      Alert myalert=driver.switchTo().alert();
//      myalert.sendKeys("thanku");
//   System.out.println(myalert.getText());
//   Thread.sleep(5000);
 //  myalert.accept();  // this is for OK button

//  myalert.dismiss();    // this is for CANCEL button
        
    }
}
