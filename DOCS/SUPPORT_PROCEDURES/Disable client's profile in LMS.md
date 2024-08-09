# Disable client's profile in LMS
In Back Office is added option to disable client's profile by clicking on `DISABLE` button.

***WARNING:*** *As this proccess is not revertable before disabling client first **need to check** does client **has** any **unpaid/not closed loans and** does client has any **not allocated amounts**.*

* In case if client has unpaid loans, profile cannot be disabled and reporter has to be informed;
  
* In case when client has closed agreements/loans (`PAID`, `TERMINATED`, `CANCELLED`, `ABORTED`) double check is there any not allocated amount;
  * If yes, ask reporter is money been retuned to client. After cconfirmation disable profile;
    > In case if money wasn't returned and client is alright with that, disable profile.
    
    > In case if money wasn't returned and client is not satisfied with that, agent has to retund and then disable profile.
  * If no, disable profile;
    
* In case when client's agreement/loan is sold, need to confirm from reporter did this client paid all debts in third party company and no further manipulations with profile, loan and etc. will not happen);

***NOTE:*** *This option is available only with permission named `CLIENT_WRITE_DISABLE` in LMS back office for user groups **Hq Core Team** and **Op Admin**. More info about permission groups and rights see [[LMS] Operations permissions](https://wiki.sunfinance.group/display/countries/%5BLMS%5D+Operations+permissions).*

### How to disable proofile
1. Open needed client's profile in Back office;
2. Click on `DISABLE` button in the upper right corner;
3. Confirm the action;

<img src="https://github.com/jevgenijakirejeva/jevgenijakirejeva/blob/main/DOCS/SUPPORT_PROCEDURES/IMG/Disable-1.png" width="500" height="400"><img src="https://github.com/jevgenijakirejeva/jevgenijakirejeva/blob/main/DOCS/SUPPORT_PROCEDURES/IMG/Disable-2.png" width="500" height="400">
