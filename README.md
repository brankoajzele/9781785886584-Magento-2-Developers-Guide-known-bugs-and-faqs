# 9781785886584-Magento-2-Developers-Guide-known-bugs-and-faqs
Place to keep track of known bugs and FAQs for Magento 2 Developer's Guide book written by Branko Ajzele, under ISBN-13 "9781785886584".


* **Page 5** - There is a line that says `The var/magento/language-* directories`, which is wrong. It should say `The vendor/magento/language-* directories`
* **Page 91** - There is a line that says `'Foggyline\Office\Model\ResourceModel\Employee\Collection's`, which is wrong. The `s` char at the end of the line needs to be removed. Assuming this bug came to existence during copy-paste of the code from IDE to MS Word, where some of MS Word auto-correction features might have done this.
* **Page 118** - The `after` listeners do not necessarily accept one parameter ($subject), but can actually accept two parameters ($subject, $result). The `afterGetAddToCartUrl($subject)` example in the book uses one ($subject) parameter, thus making for incorrect wording / explanation on the "Using the after listener" paragraph on the page 118. The method `afterGetAddToCartUrl($subject)` could have easily be written as `afterGetAddToCartUrl($subject, $result)`, depending whether or not we needed $result variable within the body of `afterGetAddToCartUrl` method for something.
* **Page 122** - There is a not needed `space character` on the link inside the _construct() function. It is `Foggyline\Office\Model \ResourceModel\Department` and it should had been ``Foggyline\Office\Model\ResourceModel\Department``
* **Page 125** - Seems like there was an error in the github code (not the book), whereas the code did not show the messages appear. The fix for that code was committed in the approapriate module [here](https://github.com/ajzele/B05032-Foggyline_Office/commit/15ecf7e24da4855fcd9914d7be26325d176f9208). The B05032-Foggyline_Office module was tested again and it seems to be working OK. Be sure to clear Magento cache, cookies and browser storage during testing. Also, keep in mind that messages are written using JavaScript once the page is fully loaded - sometimes it takes up to few seconds for messages to show.
* **Page 149** - There is a line that says `{{widget type="Foggyline\\Office\\Block\\Widget\\Example" var1="1" var2="5"}}`. Please use a single slash `\` instead of double slashes `\\`.
* **Page 155** - The `foggyline_office_employee Employee Flat Data` needs to be removed from the list of indexers. This one is not default Magento indexer. This one is part of custom module installed during book writting.
* **Page 282** - Before the wording `Create an app/code/Foggyline/DailyDeal/Model/Product/Type/DailyDeal.php file with partial content` the file `https://github.com/ajzele/B05032-Foggyline_DailyDeal/blob/master/etc/sales.xml` should be created.
* **Page 332, 333** (change described below is optional - it is optional because it works as it is now, but it might be confusing since admin email template should be in adminthml area and not frontend area)
    * On page 332 the template with id `foggyline_helpdesk_email_template_customer` needs changing value from `area="frontend"` to `area="adminhtml"`. On page
    * On page 333 the `view/frontend/email/store_owner_to_customer.html` file needs to be moved into `view/adminhtml/email/store_owner_to_customer.html`
* **Page 345** - Be sure to use the code from GitHub as full example. The book example is missing getStatusesOptionArray method.
* **Page 372** - Class definition not right in the book, needs to be changed from `class Ticket` to `abstract class Ticket`. This has been updated in the GitHub [here](https://github.com/ajzele/B05032-Foggyline_Helpdesk/blob/master/Controller/Ticket.php).
* **XML syntax** - keep in mind that text values wrapped in XML elements need to be in single line, not broken into multiple lines, or else they wont work. If copy-pasting these into the code, be sure to adjust them into single line. See below:

    WRONG:
    ```
    <argument name="path" xsi:type="string">
    foggyline_helpdesk/ticket/index
    </argument>
    ```
    
    RIGHT:
    `<argument name="path" xsi:type="string">foggyline_helpdesk/ticket/index</argument>`
