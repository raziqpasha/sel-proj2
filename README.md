// SEL PROJECT ON CHECKBOXES ANS SAME CAN PERFORM ON RADIO BUTTONS TOO
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
        WebDriverWait mywait = new WebDriverWait(driver, Duration.ofSeconds(20));
        
        driver.get("https://www.flipkart.com/search?q=iphone12&otracker=search&otracker1=search&marketplace=FLIPKART&as-show=on&as=off&as-pos=1&as-type=HISTORY");
        driver.manage().window().maximize();

        
        List<WebElement> checkBoxes = mywait.until(ExpectedConditions.visibilityOfAllElementsLocatedBy(By.xpath("//input[@type='checkbox']")));
        
        // Iterate and click each checkbox
        for (WebElement checkBox : checkBoxes) {
            
            // Ensure checkbox is clickable
            mywait.until(ExpectedConditions.elementToBeClickable(checkBox)).click();
        }
        
        // Close the driver
        driver.quit();
    }
}
