//selenium condition method
1.  isDisplayed()  --> EX.it is used for like login, create account buttion
2.  isEnabled()    --> EX.it is used for like textfilrd
3.  isSelected()   --> EX.it is used for like radio, check box buttons


package com.Attribute;

import java.util.Scanner;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class BasicDevice {
    public static void main(String[] args) throws InterruptedException {
        WebDriver driver = new ChromeDriver();
        driver.get("https://www.facebook.com/?stype=lo&deoia=1&jlou=AfcYIfIESTU-6WmLDzHmxAiaU8tonJkfVdywpbIdK4uSI4Qbo6I6F4YZ9jfTQr9GUQswCutCCamlIUjXRwj2xWUS4uYCRUBn_asFL2IhkrMzMQ&smuh=60553&lh=Ac869kzT1DFejxhrec8");
        Thread.sleep(1000);
        
        WebElement display=driver.findElement(By.xpath("//button[text()='Log in']"));
        System.out.println(display.isDisplayed());
        Thread.sleep(1000);
        
        WebElement enable=driver.findElement(By.xpath("//input[@type=\"text\"]"));
        System.out.println(enable.isEnabled());
        Thread.sleep(1000);
        
        WebElement creatClick=driver.findElement(By.xpath("//div[@class=\"_6ltg\"]//a[text()=\"Create new account\"]"));
        		creatClick.click();
        	    Thread.sleep(1000);
        
        WebElement select=driver.findElement(By.xpath("//span[@class=\"_5k_2 _5dba\"]/label[text()=\"Male\"]"));
        select.click();
        System.out.println(select.isSelected());
    }
}
