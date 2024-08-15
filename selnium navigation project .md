//SELINUM NAVIGATION
*.acess to browser first(note)
1.acess flipkart
2.maximize window
3.clcik on BuyNow button
4.enter phone number in text filed and clcick enter nd pass phone phone using sendkeys
5.continue button, resendotp button and loginButton
6.navigate to previous web
7.acess to addtocart button
8.acess to additems button
9.acces to savelater button
10.acess to ,move to cart button
11.acess to crosscancelbutton(eg:x)
12.acesss to cab=ncel buuton 
13.quit the browser page


package section1;

import java.util.List;
import java.util.Random;
import org.openqa.selenium.By;
import org.openqa.selenium.Dimension;
import org.openqa.selenium.Point;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class LaunchingBrowser {

    public static   void main(String[] args) throws InterruptedException {
        // Set up WebDriver
        WebDriver driver = new ChromeDriver();
        
        //access flipkart app
     driver.get("https://www.flipkart.com/apple-iphone-11-white-128-gb/p/itme32df47ea6742?pid=MOBFWQ6B7KKRXDDS&lid=LSTMOBFWQ6B7KKRXDDSULUZ0N&marketplace=FLIPKART&q=iphone+11&store=tyy%2F4io&srno=s_1_1&otracker=search&otracker1=search&fm=organic&iid=c79ff4cc-462d-4479-8384-d4fab77ed59a.MOBFWQ6B7KKRXDDS.SEARCH&ppt=browse&ppn=browse&ssid=zbsry2oc000000001723708578757&qH=f6cdfdaa9f3c23f3");
    Thread.sleep(2000);//waiting for 2 seconds
    
        //window is max,mini
        driver.manage().window().maximize();
        Thread.sleep(2000);
      
       WebElement btnBuyNow= driver.findElement(By.xpath("//button[@type='button']"));
       btnBuyNow.click();
        
       Thread.sleep(2000);
       WebElement phnNo=driver.findElement(By.xpath("//input[@type='text']"));
       phnNo.click();
       phnNo.sendKeys("9742261785");
       Thread.sleep(2000);
       
   //    WebElement btnContinue=driver.findElement(By.xpath("//button[@type='submit']"));
  //     btnContinue.click();
  //     Thread.sleep(20000);
       
  //    WebElement btnResendOtp=driver.findElement(By.xpath("//span[normalize-space()='Resend?']")); //text()-->not working
  //    btnResendOtp.click();
  //   Thread.sleep(5000);
       
  //     WebElement btnLogin=driver.findElement(By.xpath("//button[@type='submit']"));
  //     btnLogin.click();
   //    Thread.sleep(2000);
       
       driver.navigate().back();
       Thread.sleep(2000);
       
       WebElement btnAddToCart= driver.findElement(By.xpath("//button[@class='QqFHMw vslbG+ In9uk2']"));//button[@class='QqFHMw vslbG+ In9uk2']//*[name()='svg']//*[name()='path' and contains(@d,'M15.32 2.4')]
       btnAddToCart.click();
       Thread.sleep(2000);
       
   
       WebElement btnAddItems= driver.findElement(By.xpath("//span[normalize-space()='Add Item']"));
       btnAddItems.click();
       Thread.sleep(2000);
       
     
       
       WebElement btnSaveForLater= driver.findElement(By.xpath("//div[normalize-space()='Save for later']"));
       btnSaveForLater.click();
       Thread.sleep(2000);
     
       
       WebElement btnMoveToCart= driver.findElement(By.xpath("//div[normalize-space()='Move to cart']"));
       btnMoveToCart.click();
       Thread.sleep(2000);
       
       WebElement btnCrossCancel= driver.findElement(By.xpath("//img[@class='zDmZ1J']"));
       btnCrossCancel.click();
       Thread.sleep(2000);
       
       WebElement btnCancel= driver.findElement(By.xpath("//div[@class='sBxzFz fF30ZI t9UCZh']"));
       btnCancel.click();
      Thread.sleep(5000);
     
     driver.quit();
 
    }
}


