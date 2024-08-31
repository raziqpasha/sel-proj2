package com.Attribute;

import java.awt.AWTException;
import java.awt.Robot;
import java.awt.event.KeyEvent;
import java.time.Duration;
import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedCondition;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

public class BasicDevice {

    public static void main(String[] args) throws InterruptedException, AWTException {
    	
    		WebDriver driver =new ChromeDriver();
    		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
    		driver.get("https://www.orangehrm.com/en/book-a-free-demo/");
    		driver.manage().window().maximize();
    		driver.findElement(By.xpath("//input[@name=\"FullName\"]")).click();
    	//	send.sendKeys("rAZIQ",Keys.TAB,"sjrp@124",Keys.TAB,"RP",Keys.TAB,"Angola",Keys.TAB,"901938765",Keys.TAB);
    		
    		Robot r= new Robot();
    		r.keyPress(KeyEvent.VK_R);
    		r.keyRelease(KeyEvent.VK_R);
    		r.keyPress(KeyEvent.VK_A);
    		r.keyRelease(KeyEvent.VK_A);
    		r.keyPress(KeyEvent.VK_Z);
    		r.keyRelease(KeyEvent.VK_Z);
    		r.keyPress(KeyEvent.VK_I);
    		r.keyRelease(KeyEvent.VK_I);
    		r.keyPress(KeyEvent.VK_Q);
    		r.keyRelease(KeyEvent.VK_Q);
    }
}
    	
