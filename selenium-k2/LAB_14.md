## Lesson 14
* Mouse Hover Action
* DropDown
* iFrame
* JS Alerts

The main points for how to handle those elements from the page was added into blog. But you can refer below code snippets
from the class to try yourself as homework.

## Mouse Hover Action
```
package api_learning;

import driver.DriverFactory;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.interactions.Actions;
import url.Urls;

import java.security.SecureRandom;
import java.util.ArrayList;
import java.util.List;

import static org.openqa.selenium.support.locators.RelativeLocator.with;

public class Lesson_14_MouseHover implements Urls {
    private static final By figureSel = By.className("figure");
    private static final By figureImgSel = By.tagName("img");
    private static final By figureDescSel = By.tagName("h5");
    private static final By figureImgLinkSel = By.tagName("a");

    public static void main(String[] args) {
        WebDriver driver = DriverFactory.getChromeDriver();

        try {
            // Navigate to Hovers page
            driver.get(baseUrl.concat(hovers));
            List<WebElement> figureElems = driver.findElements(figureSel);
            List<FigureData> figuresData = new ArrayList<>();
            Actions actions = new Actions(driver);

            // Get Figure data from UI
            if (figureElems.isEmpty())
                throw new RuntimeException("No figures on the page");
            else {
                for (WebElement figureElem : figureElems) {
                    // Mouse hover
                    actions.moveToElement(figureElem).perform();

                    // Get each figure data
                    WebElement figureImgElem = figureElem.findElement(figureImgSel);
                    String figureImgSrc = figureImgElem.getAttribute("src");
                    WebElement figureDescElem = figureElem.findElement(figureDescSel);
                    String figureDesc = figureDescElem.getText();
                    WebElement figureImgLinkElem = figureElem.findElement(figureImgLinkSel);
                    String figureImgLink = figureImgLinkElem.getAttribute("href");

                    FigureData figureData = new FigureData(figureImgSrc, figureDesc, figureImgLink);
                    figuresData.add(figureData);
                }
            }

            // Verify Figures data
            for (FigureData figureData : figuresData) {
                System.out.println(figureData);
            }

            // Randomly pick up
            WebElement randomUserAvatarElem = figureElems.get(new SecureRandom().nextInt(figureElems.size()));
            actions.moveToElement(randomUserAvatarElem).perform();
            WebElement userProfileLinkElem = randomUserAvatarElem.findElement(figureImgLinkSel);
            userProfileLinkElem.click();

            // Tag name h1
            System.out.println(driver.findElement(By.tagName("h1")).getText());

        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            driver.quit();
        }
    }

    public static class FigureData {
        private String imgSrc;
        private String imgDesc;
        private String imgLink;

        public FigureData(String imgSrc, String imgDesc, String imgLink) {
            this.imgSrc = imgSrc;
            this.imgDesc = imgDesc;
            this.imgLink = imgLink;
        }

        public String imgSrc() {
            return imgSrc;
        }

        public String imgDesc() {
            return imgDesc;
        }

        public String imgLink() {
            return imgLink;
        }

        @Override
        public String toString() {
            return "FigureData{" +
                    "imgSrc='" + imgSrc + '\'' +
                    ", imgDesc='" + imgDesc + '\'' +
                    ", imgLink='" + imgLink + '\'' +
                    '}';
        }
    }
}


```

## DropDown
```
package api_learning;

import driver.DriverFactory;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.support.ui.Select;
import url.Urls;

public class Lesson_14_DropDown implements Urls {

    public static void main(String[] args) {
        WebDriver driver = DriverFactory.getChromeDriver();

        try {
            // Navigate to Hovers page
            driver.get(baseUrl.concat(dropdownOptionPage));

            // Target Dropdown
            Select select = new Select(driver.findElement(By.id("dropdown")));

            select.selectByVisibleText("Option 1");
            Thread.sleep(1000);

            select.selectByIndex(2);
            Thread.sleep(1000);

            select.selectByValue("1");
            Thread.sleep(1000);

        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            driver.quit();
        }
    }

}


```

## iFrame

```
package api_learning;

import driver.DriverFactory;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.Select;
import url.Urls;

public class Lesson_14_iFrame implements Urls {

    public static void main(String[] args) {
        WebDriver driver = DriverFactory.getChromeDriver();

        try {
            // Navigate to Hovers page
            driver.get(baseUrl.concat(iFramePage));

            // Switch to iFarme
            driver.switchTo().frame(driver.findElement(By.cssSelector("[id$='ifr']")));


            // Clear default text then input the new ones
            WebElement editorInputElem = driver.findElement(By.id("tinymce"));
            editorInputElem.clear();
            editorInputElem.sendKeys("This is test ......");

            Thread.sleep(2000);

            // Switch back to default frame
            driver.switchTo().defaultContent();

            // Logic continue here....

        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            driver.quit();
        }
    }

}

```

## JS Alerts
```
package api_learning;

import driver.DriverFactory;
import org.openqa.selenium.Alert;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import url.Urls;

import java.time.Duration;

public class Lesson_14_JsAlert implements Urls {

    private static final By jsAlertSel = By.cssSelector("[onclick=\"jsAlert()\"]");
    private static final By jsAlertConfirmSel = By.cssSelector("[onclick=\"jsConfirm()\"]");
    private static final By jsAlertPromptSel = By.cssSelector("[onclick=\"jsPrompt()\"]");
    private static final By resultSel = By.cssSelector("#result");

    public static void main(String[] args) {
        WebDriver driver = DriverFactory.getChromeDriver();

        try {
            // Navigate to Hovers page
            driver.get(baseUrl.concat(jsAlertPage));
            WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
            WebElement resultElem = driver.findElement(resultSel);

            // JS ALERT | getText -> confirm
            driver.findElement(jsAlertSel).click();
            Alert jsAlert = wait.until(ExpectedConditions.alertIsPresent());
            System.out.println(jsAlert.getText());
            jsAlert.accept();
            System.out.println(resultElem.getText());
            System.out.println("===============");

            // JS ALERT CONFIRM
            driver.findElement(jsAlertConfirmSel).click();
            Alert jsAlertConfirm = wait.until(ExpectedConditions.alertIsPresent());
            System.out.println(jsAlertConfirm.getText());
            jsAlertConfirm.dismiss();
            System.out.println(resultElem.getText());
            System.out.println("===============");

            // JS ALERT PROMPT
            driver.findElement(jsAlertPromptSel).click();
            Alert jsAlertPrompt = wait.until(ExpectedConditions.alertIsPresent());
            System.out.println(jsAlertPrompt.getText());
            jsAlertPrompt.sendKeys("This is my texts...");
            jsAlertConfirm.accept();
            System.out.println(resultElem.getText());

        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            driver.quit();
        }
    }

}

```