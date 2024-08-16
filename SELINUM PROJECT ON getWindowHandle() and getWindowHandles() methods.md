// SELINUM PROJECT ON getWindowHandle() and getWindowHandles() methods
// and another get methods are 1. get() 2.getCurrentUr() 3.getPageSource() 4.getTitle().

package section1;

import java.util.Set;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class LaunchingBrowser {

    public static   void main(String[] args) throws InterruptedException {
    	WebDriver driver=new ChromeDriver();
    	driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login");
    	
    	Thread.sleep(2000);
    	
    	WebElement link=driver.findElement(By.linkText("OrangeHRM, Inc"));
    	link.click();
    	Thread.sleep(2000);
    	
    	
    String windowOne=driver.getWindowHandle();
  //  System.out.println(windowOne);
    
    Set<String> windowMultiple=driver.getWindowHandles();
//    System.out.println(windowMultiple);
    
    for(String windowAll :windowMultiple)
    if(windowAll.equals(windowOne)) {
    	driver.switchTo().window(windowAll);
    	break;
    }
    System.out.println(driver.getTitle());
    driver.switchTo().window(windowOne);
    
    System.out.println(driver.getTitle());
    	
       }
}
