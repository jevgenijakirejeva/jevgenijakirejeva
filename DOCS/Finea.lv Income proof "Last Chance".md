# Finea.lv Income proof "Last Chance"
This document includes several topics, for your convenience most important themes are highlighted:
* [Overal information](#Overal-information)
	*  [How it works](#How-it-works)
* [Whats new in Front-office](#Whats-new-in-Front-office)
* [Whats new in Back-office](#Whats-new-in-Back-office)
* [Demo](#Demo)
* [Related articles](#Related-articles)

## Overall information 
<a id="Overal-information"></a>
To improve scoring process and get most accurate data from customers, is improved application submit process in the following way:

*Once client submits an application and scoring process is finished on risk side, given not enough income for particular loan is found in KIB income and bank statement data, Risk team Instead of reject will ask customers to submit another bank statement of another bank. The idea is that client will have option to use another bank with salary/additional income, what will gives us more chance for evaluation.*

This feature is pretty same as in Salem's product, the difference is that on Finea and DaliDali we can offer two options based on Risk's Limit Model answer:
* Pass Kevin again with another bank;
* Upload income statement;
---
### How it works:
<a id="How-it-works"></a>

**1st case**:

Kevin Flow Block will be called in the Risk Flow after  ***Scoring-Limit Model***. Then If  Limit Model returned  ***different_bank_account_needed = 1*** for client will be shown Kevin with Widget where he will need to try another bank and get authorized with it. If the client pass Kevin again, then scraped data needs gets stored in DB. Then application returnes to the ***Scoring-Limit Model*** and then it can either ask to pass Kevin with another account or ***continue or reject*** application according to the existing logic.

**2nd case**:

Kevin Flow Block will be called in the Risk Flow after  ***Scoring-Limit Model***. Then If Limit Model provided  key-value indicating to that ***Manual Document Upload*** is expected from customer ***bank_statement_upload_needed=1***, client will be asked to upload a bank statement in front office and after that in Back Office will be generated a task for Bank Statement verification.

Supported file formats: `PDF`, `JPEG`, `TIFF`, `PNG`.

For full flow, see [Finea flow - Kevin last chance](https://wiki.sunfinance.group/display/RT/v1.1+Finea+Flow+-+Kevin+Last+Chance).


## Whats new in Front-office
<a id="Whats-new-in-Front-office"></a>

Depending on what Limit Model returned, been integrated in client's flow two web pages: 
* Bank statement submission where is shown only Kevin's widget;
*  Bank statement manual upload which is absolutely new one and where are displayed: clear instructions, an upload button, and options for the user to view, remove, or add more files before proceeding;
> In case if been asked to pass Kevin again, client will see page [Bank statement submission](https://wiki.sunfinance.group/display/RD/Finea+flow?preview=/465422100/530200208/Screenshot%202024-07-16%20at%2011.01.18.png#4654221003060912956e645c98a8c2e9a9edc2223);

> In case when Limit Model returned that client has to upload bank statement in front office client will see [Bank statement manual upload](https://wiki.sunfinance.group/display/RD/Finea+flow?preview=/465422100/530200208/Screenshot%202024-07-16%20at%2011.01.18.png#4654221003060912956e645c98a8c2e9a9edc2223) page;

Statement upload will be applied during registration and during repeated application apply.

For full client's registration flow, see [Finea.lv Customer journey](https://wiki.sunfinance.group/display/countries/Finea.lv+Customer+Journey) and [DaliDalii.lv Customer journey](https://wiki.sunfinance.group/display/countries/DaliDali.lv+Customer+journey).

## Whats new in Back-office
<a id="Whats-new-in-Back-office"></a>

As been mentioned in [Overall information](#Overal-information) paragraph in 2nd case description once client uploaded bank statement in back office automatically creates task named "***Bank Statement verification***" for agent for manual check. Task UI and scenarios are described in [Bank statement verification (Finea&DaliDali specific)](https://wiki.sunfinance.group/display/countries/%5BLMS%5D+Applications#id-%5BLMS%5DApplications-Applicationstatuses.).

For application's entity been added few more statuses, so agents can be aware of what is happening with application. 

*New statuses*:
* `Bank statement request`;
* `Bank statement provided`;
* `Bank statement manual upload`;
* `Bank statement check`;
* `Bank statement confirmed`;

Full information about application statuses and flow can be found in [[LMS] Applications](https://wiki.sunfinance.group/display/countries/%5BLMS%5D+Applications#id-%5BLMS%5DApplications-Applicationstatuses.)


In back office is added new document type named  `bank-statement`  which will be displayed in back office after client clicked on "*Pievienot documentus*" button, chose file and uploaded file. File will be available in client's card in "**Documents**" tab and in "**Documents**" section in common section list.

## Demo
<a id="Demo"></a>


## Related articles
<a id="Related-articles"></a>

[Salem income statement upload](https://wiki.sunfinance.group/pages/viewpage.action?spaceKey=countries&title=Salem.kz+Income+statement+upload);

[Finea.lv Customer journey](https://wiki.sunfinance.group/display/countries/Finea.lv+Customer+Journey);

[DaliDalii.lv Customer journey](https://wiki.sunfinance.group/display/countries/DaliDali.lv+Customer+journey);

[[LMS] Applications](https://wiki.sunfinance.group/display/countries/%5BLMS%5D+Applications#id-%5BLMS%5DApplications-Applicationstatuses.);

[Bank statement verification (Finea&DaliDali specific)](https://wiki.sunfinance.group/display/countries/%5BLMS%5D+Applications#id-%5BLMS%5DApplications-Applicationstatuses.);
