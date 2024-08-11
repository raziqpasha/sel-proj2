//selnium basic proj
1.launch browser
2.access flipkart application
3.maxmize n minimize the window
4.resize and relocate the window
5.navigate the webpage(navigate().to("url"),back,forward,refresh)
6.acess the current webpage(title,url,pagesource)
7.quite or close the webpage.

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
     driver.get("https://www.flipkart.com/");
    Thread.sleep(2000);//waiting for 2 seconds
    
        //window is max,mini
        driver.manage().window().maximize();
        Thread.sleep(2000);
        driver.manage().window().minimize();
       Thread.sleep(2000);
        
       //its used tp set the size of webpage width n height.
        Dimension d=new Dimension(500,300);//(height,width)
        driver.manage().window().setSize(d);
        Thread.sleep(2000);
        
       //it take the webpage at point as given in the parameters 
        Point p=new Point(100,230);
        driver.manage().window().setPosition(p);
        Thread.sleep(2000);
        
        //it does navigation from one webpage application to another web page application or it can navigate multiple webpages also
        driver.navigate().to("https://www.myntra.com/shop/men");
       Thread.sleep(2000);
        driver.navigate().back();
        Thread.sleep(2000);
        driver.navigate().forward();
        Thread.sleep(2000);
        driver.navigate().refresh();
        Thread.sleep(2000);
        
        
        //it is used to get or print the current title,url,pagesource i,e (the frontend part) of webpage .
        String title=driver.getTitle();
        System.out.println("the current page title:"+title);
        Thread.sleep(2000);
        String curUrl=driver.getCurrentUrl();
        System.out.println("the current page url:"+curUrl);
       Thread.sleep(2000);
        String pageSrc=driver.getPageSource();
        System.out.println("the current pageSource:"+pageSrc);
        Thread.sleep(2000);
        
        //it will completely close of website //driver.close()-> can also use but it will not complete close in backend it will be running of website(but it will close in frontend) and when comes to driver.quit->it will completely close the website in front end and backend as well.
        driver.quit();
        
        
    }
}


