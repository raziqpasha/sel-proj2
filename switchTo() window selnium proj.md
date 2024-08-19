package com.Attribute;

import java.time.Duration;
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;
import java.util.Set;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

public class BasicDevice {
   

	public static void main(String[] args) throws InterruptedException {
    	WebDriver driver = new ChromeDriver();
    	WebDriverWait mywait=new WebDriverWait(driver,Duration.ofSeconds(20));
    	
    	
        driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login");
        driver.manage().window().maximize();
       // driver.findElement(By.xpath("//a[normalize-space()='OrangeHRM, Inc']")).click();
       
	mywait.until(ExpectedConditions.elementToBeClickable(By.xpath("//a[normalize-space()='OrangeHRM, Inc']"))).click();
       
         
         Set<String> windall=driver.getWindowHandles();
        // System.out.println(windall);
         List<String> list=new ArrayList(windall);
         
         String parentId=list.get(0);
        String childId=list.get(1);
        System.out.println(parentId);
        System.out.println(childId);
         
       
        for(String win:list) {
        	String title= driver.switchTo().window(win).getTitle();
        	 if(title.equals("OrangeHRM")) {
        		 System.out.println(driver.getCurrentUrl());
        	 }
         }
	
	}
}
