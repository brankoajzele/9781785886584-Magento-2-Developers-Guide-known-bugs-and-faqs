# 9781785886584-Magento-2-Developers-Guide-known-bugs-and-faqs
Place to keep track of known bugs and FAQs for Magento 2 Developer's Guide book written by Branko Ajzele, under ISBN-13 "9781785886584".


* **Page 91** - There is a line that says `'Foggyline\Office\Model\ResourceModel\Employee\Collection's`, which is wrong. The `s` char at the end of the line needs to be removed. Assuming this bug came to existence during copy-paste of the code from IDE to MS Word, where some of MS Word auto-correction features might have done this.
* **Page 149** - There is a line that says `{{widget type="Foggyline\\Office\\Block\\Widget\\Example" var1="1" var2="5"}}`. It is worth noting that double slashes `\\` are used only when WYSIWYG editor is disabled. If you are copy pasting example into WYSIWYG, then use single slash `\`.
* **Page 345** - Be sure to use the code from GitHub as full example. The book example is missing getStatusesOptionArray method.
