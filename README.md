//Take Screctenshot  seelenium project


package com.Attribute;
import org.openqa.selenium.TakesScreenshot;

import java.awt.AWTException;
import java.awt.Robot;
import java.awt.event.KeyEvent;
import java.io.File;
import java.io.IOException;
import java.time.Duration;
import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.ExpectedCondition;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

import com.google.common.io.Files;

public class BasicDevice {

public static void main(String args[]) throws InterruptedException, IOException {
  		
  		WebDriver driver=new ChromeDriver();
  		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
  		driver.get("https://demoapps.qspiders.com/ui?scenario=1");
  		
  		Actions a=new Actions(driver);
    		WebElement MouseAct=driver.findElement(By.xpath("//section[text()='Mouse Actions']"));
  		MouseAct.click();
  		WebElement DragDrop=driver.findElement(By.xpath("//section[text()='Click & Hold']"));
  		DragDrop.click();
  		
  		WebElement DD=driver.findElement(By.xpath("//div[@id=\"circle\"]"));

  		a.clickAndHold(DD).perform();
  		Thread.sleep(5000);
  		
  	//	\ScreenShot//image.pingui
  		TakesScreenshot ts=(TakesScreenshot)driver;
  		File src=ts.getScreenshotAs(OutputType.FILE);
  		File dest=new File(".\\ScreenShot//image.ping");
  		Files.copy(src, dest);
  		driver.quit();
  	}


	
}

