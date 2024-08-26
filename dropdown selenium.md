//SELENIUM DROPDown
//1.select dropdown--->the dropdown i have design below
//2.bootstrap dropdown--->similar to select dropdown and normally use like xpath
//3.hidden dropdown---> it is basically hidden and there r ways to do ,see video is similar and can easily understand


package com.Attribute;

import java.time.Duration;
import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.Select;
import org.openqa.selenium.support.ui.WebDriverWait;

public class BasicDevice {

    public static void main(String[] args) throws InterruptedException {
        WebDriver driver = new ChromeDriver();
        WebDriverWait myWait = new WebDriverWait(driver, Duration.ofSeconds(50));
        
        driver.get("https://testpages.eviltester.com/styled/validation/input-validation.html");
      //  driver.manage().window().maximize();
        String jsCode=driver.getPageSource();
        System.out.println(jsCode);

        WebElement dropDown=driver.findElement(By.xpath("//select[@id=\"country\"]"));
        dropDown.click();
        
        Thread.sleep(5000);
        Select dropCountry=new Select(dropDown);
        // dropCountry.selectByVisibleText("Belgium");
        // dropCountry.selectByValue("Benin");
        dropCountry.selectByIndex(35);
        Thread.sleep(5000);
         dropDown.click();
         
         
         List<WebElement> op= dropCountry.getOptions();
         System.out.println(op.size()-5);
         
         
        for(WebElement option:op) {
        	String op1=option.getText();
        	if(op1.equals("Bhutan")) {
        //	System.out.println(op.get(i).getText());
        		option.click();
        }
    }
}
}
