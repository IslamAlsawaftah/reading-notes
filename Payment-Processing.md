### How to read Technical Documents as fast as possible

1. Establish why you are reading it

If you don't know what you are trying to find, you'll either fall asleep or mindlessly stare at the words in each section.

2. Get an overview of the content and structure of the document

3. Take 30s to 2 minutes to scan the rest of the document.

4. If you want, stop at the interesting parts and take a deeper look. Stop when it gets boring.

5. Look at the table of contents again. You'll have a deeper understanding of the document after you look again.

6. Choose what to read next based on interesting-ness or usefulness. If there's nothing useful, close the doc. You can say that you've read it from cover to cover.

### Merchant Accounts

It all starts with your bank checking account.

The Merchant Account is how you connect to the credit card processing network. 

An Internet Merchant Account is a merchant account that is able to accept online credit card transactions. 

Payment Gateway

The Payment Gateway is responsible for sending the credit card to the appropriate Internet Merchant Account over secure online channels. 

It is helpful to think of the Gateway as a router that sends the credit card information to the appropriate account.  It is also responsible for fraud checking and maintaining reliable links with the merchants.

### Application can interact with the Payment Gateway 

the user may simply be transferred to a web page on the Gateway for credit card processing.  When the transaction is complete, the user is transferred back to the application.  At no point does the application handle the credit card information.

## sophisticated applications, such as online registration

the user’s credit card and passes the information to the Gateway through a secure channel called an API (Application Programming Interface). Such programs are called third-party applications and are required to meet high security requirements.  One of these is that the credit card information should be passed to the Gateway and not stored on the application server.

### payment through online registration

1- User enters credit card information into the application

2- Credit card information is sent to the Payment Gateway via a secure channel

3- The Payment Gateway routes the credit card to the appropriate Internet Merchant Account

4- Internet Merchant Account connects to the Merchant Account for credit card processing.

5- The result is passed back to the Gateway and then the application.

### Validation, Refunds, and Settlement

online user will usually not see the specific reasons for the failure, such as a decline. (The reason for this is that too much information makes it easier for hackers to fake credit card transactions.) However, the management side of the Gateway and third-party applications may allow you to find out more specific reasons for the failure.

### Fees

The Merchant Account will have one or more of these fees

1- One-time setup fee

2- Recurring monthly fees

3- Per Transaction fees.  While there may be a fixed transaction fee (usually 25 cents or less), the most important fee is the Percentage Fee, which will typically range from 2.00-3.00% for MasterCard/Visa and 4.00-5.00% for American Express.

4- The Payment Gateway and, possibly, the Internet Merchant account will have this structure:

5- One-time setup fee (typically in the $100-200 range)

6- Recurring Monthly Fee (typically in the $20-60 range)

7-Per Transaction fee.  Some gateways waive this fee in favor of a higher monthly transaction fee.  Otherwise, this fee is relatively low on the order of 25 cents.  If you have large volume (3,000 or more transactions per month, for example), you may be better off paying a higher monthly fee instead of per transaction charges.




