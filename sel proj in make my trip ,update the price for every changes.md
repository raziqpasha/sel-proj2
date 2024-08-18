//senario
1.launch Browser
2.Acess make mi trip
3.handle pop up(click or remove crossCancel)
4.click on departure
5.print the price of selected or update the price according every change on the same day.


package com.Attribute;

import java.util.Scanner;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class BasicDevice {
    public static void main(String[] args) throws InterruptedException {
        WebDriver driver = new ChromeDriver();
        driver.get("https://www.makemytrip.com/flights/");
        Thread.sleep(1000);

        // Close the modal
        WebElement srch = driver.findElement(By.xpath("//span[@class='commonModal__close']"));
        srch.click();
        Thread.sleep(1000);

        // Click on departure
        WebElement departureClick = driver.findElement(By.xpath("//span[normalize-space()='Departure']"));
        departureClick.click();
        Thread.sleep(1000);

        String initialValue = ""; // Initial value is empty
        Scanner s = new Scanner(System.in);
        System.out.print("Enter the number of iterations to check for updates: ");
        int n = s.nextInt();
        
        for (int i = 0; i < n; i++) {
            // Fetch the current value inside the loop
            WebElement highLatedBoxPriceInDeparture = driver.findElement(By.xpath("//div[@class=\"dateInnerCell\"]//p[contains(text(),'₹')]"));
            String currentValue = highLatedBoxPriceInDeparture.getText();
            
            // Check if the value has changed
            if (!currentValue.equals(initialValue)) {
                initialValue = currentValue;
                System.out.println("Updated value: " + currentValue);
            } else {
                System.out.println("Value remains the same: " + currentValue);
            }

            Thread.sleep(10000); // Wait for 10 seconds before the next iteration
        }

        driver.quit();
    }
}
