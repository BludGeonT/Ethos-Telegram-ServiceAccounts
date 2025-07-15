# Ethos-Telegram-ServiceAccounts MODULE
EthosProject -> Telegram -> Service Accounts Management (Main Ethos Service Bots)

### Ethos-Telegram-ServiceAccounts References
- In any of the markdown files within the EthosProject, when you see a reference of SERVICE ACCOUNTS, that pertains to the accounts that we are going to work with in this MODULE.
- In any of the markdown files within the EthosProject I reference EthosProject Operators, that pertains to the employees or operators of the EthosProject website and GUI.

### Ethos-Telegram-ServiceAccounts Summary
The EthosProject will have many different MODULES that are used by the system.  MODULES are stand-alone portions of code and functions that all tie together to create a robust, but modular, way of working.

One of the root elements of EthosProject will be SERVICE ACCOUNTS.  SERVICE ACCOUNTS are our Telegram Bots that are created using @botfather on Telegram.  These are similar to the other bots that we will use for other operations but SERVICE ACCOUNTS are special in that a single bot can be used, or invited, by multiple Telegram groupchat channels.  Each of these channels that have a SERVICE ACCOUNT within them will be able to interact with it.  

The Ethos-Telegram-ServiceAccounts MODULE should be displayed along with the rest of the modules after an EthosProject operator clicks on MODULES and then clicks into Ethos-Telegram-ServiceAccounts which should open up a new screen that allows for management of these accounts including adding, editing, deleting, enabling, and disabling them.  In addtion, SERVICE ACCOUNTS may be assigned to one or multiple different MODULES.  This will be explained in the UI.md file for Ethos-Telegram-ServiceAccounts markdown file. 

### Ethos-Telegram-ServiceAccounts DATABASE Structure
We want to have a separate database set up soley for SERVICE ACCOUNTS.  The information within this database of SERVICE ACCOUNTS will be referenced and used to interact with other EthosProject MODULES.

The Database Structure should be as follows and named appropriately (EG:  ETHOS_SERVICEACCOUNTS):

- SERVICEACCOUNT_NAME:  This will be an alpha-numeric field containing the name of the bot given when it was created by @botfather (eg: ethos-md5sum-bot)
- SERVICEACCOUNT_ID:  This will be the ID of the bot created by @botfather and it will be a nuerical value only and should reject non-numeric values
- SERVICEACCOUNT_APIKEY:  This will be the value of the API key that was provided by @botfather upon the bot creation
- SERVICEACCOUNT_STATUS:  This will be a boolean value of either ENABLED or DISABLED.
- SERVICEACCOUNT_CREATOR:  This will be the name of the EthosProject operator that created the service account
- SERVICEACCOUNT_CREATION:  This will be a date value of the date that the SERVICE ACCOUNT was added into the Ethos-Telegram-ServiceAccount Database
- SERVICEACCOUNT_MODULES:  When creating a new SERVICE ACCOUNT, this field should exist but be empty to start.  As other EthosProject MODULES assign a SERVICE ACCOUNT to use, a value here of which module will be added.  This could potentially be from one EthosProject module, or multiple modules.  The values for this field will be added by the other MODULES that use it.  

### Ethos-Telegram-ServiceAccounts Workflow
When clicking on the Ethos-Telegram-ServiceAccounts MODULE, a new screen should open up a new page to manage the SERVICE ACCOUNTS.

This should be a interface that allows for adding, editing, deleting, enabling, or disabling SERVICE ACCOUNTS.

Keep in mind that other MODULES will need to reference these records, or accounts, that are in the SERVICE ACCOUNTS Database.  For example, the Ethos-MD5SUM MODULE will need to be able to select from a list of SERVICE ACCOUNTS to use for its main functionality.  When a SERVICE ACCOUNT becomes assigned by another MODULE, the MODULE will add its name into the SERVICE ACCOUNT DATABASE field above in the `SERVICEACCOUNT_MODULES`.  Knowing this, other modules will need write capabilities to this SERVICE ACCOUNTS database.

