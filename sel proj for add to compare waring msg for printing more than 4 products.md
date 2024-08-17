//senario
1.launch browser
2.acess flipkart application
3.search for iphone 12
4.click on add to compare for 1st,3rd,5th,24th i.e last
5.make sure try to add more than 4 products (u will get waring msg)


package com.Attribute;
import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class BasicDevice {

	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub
		
	
				// TODO Auto-generated method stub
				WebDriver driver=new ChromeDriver();
				driver.get("https://www.flipkart.com/");
				Thread.sleep(2000);
				WebElement srch=driver.findElement(By.xpath("//input[@placeholder='Search for Products, Brands and More']"));
		        srch.sendKeys("iphone12");
		        srch.submit();
		        Thread.sleep(2000);

		        List<WebElement> addToCom = driver.findElements(By.xpath("//span[text()='Add to Compare']"));
		         for(int i=0;i<addToCom.size();i++) {
		        	 if(i==0||i==1||i==2||i==4||i==23) {
		        		 addToCom.get(i).click();
		        		 }
		        	
				
		        	 
		         }
		         
	}

}
