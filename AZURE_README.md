# Create New Account Azure Portal and Storage Account

## 1. Azure Portal

### Instructions:

1.  Kindly sign out of your Azure Portal if you're signed in.

2.  Click on your personal link: < Azure personalized Sign-in Link >.

3.  You will be asked to sign-in with your Microsoft account.

4.  Follow the step-by-step prompts to fill in the required information.

5.  For the system to ensure that you're the card holder registered in the account, after signing in using the link provided, you will be asked to enter your credit card information, please proceed and fill in the information.

6.  After you finish filling in the Credit card information, you will be asked to select a support plan, you can choose the basic plan if you don't need a support plan for now.

7.  After successful sign-in, check out the “QuickStart Center” (you can search for it using the search bar on the Azure Portal).

8.  After you enter the Azure Portal, go to the subscriptions sections and provide me with the subscription ID that appears, so I can ensure that everything is working fine from my end.

9.  Enjoy!

### Step to create an Azure account:

> via Vietnamese Phone Number

1. Use your phone (preferably androids) to access the link instead of the Laptop/PC, and open Mobile data instead of Wi-fi.

2. Open it in an incognito/private tab in Edge browser.

3. Clear cache and cookies first.

4. Click on "No Account? Create One".

5. On the phone verification page, select 'use a different number to verify my identity', and in the second phone number field, write the same phone number without the leading zero (eg: 12345XXXXX) after your select the country code, hit Verify "Text Me" or "Call Me".

6. If the previous step is not working, enter your landline number and click on "Call Me", do not select "Text Me"

7. Once you pass this step, continue as usual.

## 2. Azure Storage Account Service

1. Create Storage Account in the Azure Portal

2. Enable blob anonymous on azure. Go to Access level, set it to Blob (anonymous read access for blobs only) or Container (anonymous read access for containers and blobs).

3. Get AZURE_STORAGE_ACCESS_KEY, AZURE_STORAGE_ACCOUNT

## 3. Using Azure CLI

Run the following command to set the container's public access level:

```
az storage account update \
  --name <Your_Storage_Account_Name> \
  --resource-group <Your_Resource_Group_Name> \
  --allow-blob-public-access true
```
