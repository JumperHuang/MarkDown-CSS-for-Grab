## Questions for Grab
### Update 2017-08-15
1.	If merchant modify function is necessary for merchant web portal. If yes, a Merchant Modify interface should be defined.
A: It makes sense. And the info can not be change: Government ID, Email ID;
2.	In our consideration, manual inquiry for transaction status is not needed in Merchant App, pls confirm that.
A: remove the manual inquiry function.
3.	In our mechanism for static QR code transactions, there is a check code (4 digits number) generated when the transaction is complete, and this check code will display both on customer's mobile phone and merchant App notification. The merchant can use this code to identify the transaction is paid by which customers.
A: deploy this function and specify the detail later.
4.	Change resend interval (1) the transaction notification resend interval: 2s, 2s, 5s, 10s, 10s, and 30s. (2) Other interface resend interval: 5s, 5s, 5s
A: Ok
5.	For the refund transaction initiated on Grab's XM portal, Grab only need to send a refund transaction result notification to CIL, and the refund notification interface should be defined. 
A: Ok
6.	Since Grab need T+0 settlement, how to process the transaction data inconsistency between Grab and CIL. Basically, CIL will generate a settlement file (the interface is defined in document: Interface Specification for Grab) and send to Grab every workday.
A: Grab will generate a reconciliation document and provide it to CIL.
7.	What merchant info should be send to Grab system through the Merchant Create and Merchant Modify interface? (based on document: CIL Web Portal Datapoint)
A: In document datapoint.
8.	As we know, UUID is a universally unique identifier consist of 32 byte number or letter. But it is not convenient to check the transaction ID or merchant ID if they obey the format of UUID. We suggest a 18 byte number for transaction ID and 15 byte number for merchant ID, and we can define the specific meaning of these ID later.
A: Will discuss this problem internal and response CIL later.

### Update 2017-08-18
##### About Merchant portal / App
- We design 2 ways to assign a new Grab user on merchant portal: 
 1. A portal user should be assigned by Grab administrator user. Merchant portal will not support a self-sign-in user. If Grab user want to login with Google or Facebook user authorization, if can be bind after the user being assigned.
 2. Grab staff register a portal user independently in Sign In web page and the user has no permission before Grab administrator assign the character to the user.
- Permission management system will provide 3 different characters for Grab administrator to choose when assign permission to different users, they are: Administrator, Operator and Auditor. Each character has constant permission in merchant portal.
- If one user need multiple characters?
- Character Describe
- When initiate refund transaction, 
 1. If a Authorize Code is needed to check the operator permission. If yes, the working flow is as follow:
Before initiate a refund transaction on merchant portal, Grab user should enter a Authorize Code for security confirm, this Authorize Code is defined as a fixed 6 digits number. On the other hand, when merchant user initiate a refund transaction on merchant App, they should also enter the Authorize Code. Each merchant user has his own 6 digits Authorize Code and it can be set/reset on merchant portal.
 2. If refund transaction needs a approve level (audit working flow) before refund request send to Grab. 
- What contents should be included in the merchant list under menu merchant information, merchant operator and merchant audit?
- If merchant App need to support merchant user modifying merchant information on App?
- If it is necessary to verify the authenticity or validity of the key information of merchant? Such as Email ID, mobile phone number and bank account, etc.
- Merchant App should support what Android/iOS firmware version and what mobile phone/pad brand and version; Merchant portal should support what browse brand and version, and screen resolution.
