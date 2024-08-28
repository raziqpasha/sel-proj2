//package com.Attribute;
//
//import java.time.Duration;
//import java.util.List;
//
//import org.openqa.selenium.By;
//import org.openqa.selenium.JavascriptExecutor;
//import org.openqa.selenium.WebDriver;
//import org.openqa.selenium.WebElement;
//import org.openqa.selenium.chrome.ChromeDriver;
//import org.openqa.selenium.support.ui.ExpectedConditions;
//import org.openqa.selenium.support.ui.Select;
//import org.openqa.selenium.support.ui.WebDriverWait;
//
//public class BasicDevice {
//
//    public static void main(String[] args) throws InterruptedException {
//        WebDriver driver = new ChromeDriver();
//        WebDriverWait myWait = new WebDriverWait(driver, Duration.ofSeconds(50));
//        
//        driver.get("https://practice.expandtesting.com/dynamic-table");
//        driver.manage().window().maximize();
//       
//        int row=driver.findElements(By.xpath("//table[@class=\"table table-striped\"]//tr")).size();
//      System.out.println(row);//5
//   //  System.out.println(tab.getText()); //cannot invoke with primitive datatype means only non primitive datatype can have to use this
//      
//      int col=driver.findElements(By.xpath("//table[@class=\"table table-striped\"]//tr//td")).size();
//      System.out.println(col);//20
//      
//     String rowCol=driver.findElement(By.xpath("//table[@class=\"table table-striped\"]//tr[4]//td[3]")).getText();
//      System.out.println(rowCol);
//      
//     for(int r=1;r<=row;r++) {
//    	 for(int c=1;c<=col;c++) {
//    		String rC= driver.findElement(By.xpath("//table[@class=\"table table-striped\"]//tbody//tr["+ r +"]//td["+ c +"]")).getText();
//    		System.out.print(rC+" ");
//    	 }
//    	 System.out.println();
//     }
//}
//}


package com.Attribute;

import java.time.Duration;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.WebDriverWait;

public class BasicDevice {

    public static void main(String[] args) throws InterruptedException {
        WebDriver driver = new ChromeDriver();
        WebDriverWait myWait = new WebDriverWait(driver, Duration.ofSeconds(50));

        driver.get("https://practice.expandtesting.com/dynamic-table");
        driver.manage().window().maximize();

        // Counting the total number of rows in the table (excluding the header row)
        int row = driver.findElements(By.xpath("//table[@class=\"table table-striped\"]//tbody//tr")).size();
        System.out.println(row);  // Correct number of rows (e.g., 4)

        // Counting the number of columns in the first row
        int col = driver.findElements(By.xpath("//table[@class=\"table table-striped\"]//tbody//tr[1]//td")).size();
        System.out.println(col);  // Correct number of columns (e.g., 4)

        // Getting a specific cell value (row 4, column 3)
        String rowCol = driver.findElement(By.xpath("//table[@class=\"table table-striped\"]//tbody//tr[4]//td[3]")).getText();
        System.out.println(rowCol);

        // Iterating through the rows and columns to print each cell value
        for (int r = 1; r <= row; r++) {
            for (int c = 1; c <= col; c++) {
                String rC = driver.findElement(By.xpath("//table[@class=\"table table-striped\"]//tbody//tr[" + r + "]//td[" + c + "]")).getText();
                System.out.print(rC + " ");
            }
            System.out.println();  // Print a new line after each row
        }

        // Optionally close the browser
        driver.quit();
    }
}
