# Bug Bank Writeup

## Task Title:

Bug Bank

## Task Category:

Web

## Task Description:

Welcome to BugBank, the world's premier banking application for trading bugs! In this new era, bugs are more valuable than gold, and we have built the ultimate platform for you to handle your buggy assets. Trade enough bugs and you have the chance to become a premium member. And in case you have any questions, do not hesitate to contact your personal assistant. Happy trading!

## Goal:

Find a vulnerability in trading bugs to become a premium member.

## Walkthrough:

I singup on the given website using credentials:

Username: bbw

Password: bbw

![singup image](SignupAccount.png)

After signing up, a home page loaded. I observed few things on home page:

 - An account id
 - Bugs (initially 0)
 - Transfer Bugs Button
 - Settings Button
 - Logout Button
 - Transaction History
 
 ![home page image](home-page.png)

Transfer Bugs and Settings Buttons seemed interesting to me, so I thought to explore these.

#### Transfer Bugs

After clicking transfer bugs button, a popup showed up. 

![transfer bugs popup image](transfer-bugs-button.png)

In order to make a transfer, I need recipient id, amount and description.

#### Settings

After clicking settings button, a settings page loaded.

![settings page image](settings1.png)

![settings page image](settings2.png)

This page contains functionality for updating the details of user and upgrading to premium feature. We need 10,000 bugs in our account for upgrading to premium feature.

Now, I have explored both functionalities. I need to find a vulnerability in transfer bugs functionality which I will exploit to increase my account balance to 10,000 bugs and then upgrade to premium feature.

In order to test transfer funds functionality, I need a recipient's account id. So, I created one more account using credentials:

Username: bbw2
Password: bbw2

![bbw2 home page image](bbw2.png)

I copied the account id of bbw2. 

**c0c2d396-df8b-46ab-a5a7-839b00e7c065**

I logged in again into account of bbw. I tried to transfer 1 bug from bbw to bbw2. 

![unsuccessful transfer image](transfer1.png)

Transfer was unsuccessful, as there were 0 bugs balance in both accounts.

I tried to transfer negative -1 bug from bbw to bbw2.

![successful transfer image](transfer2.png)

It worked. Bug balance of bbw increased from 0 to 1. I immediately made a transfer of -10,000 bug from bbw to bbw2. 

![successful transfer image](transfer3.png)

Now there was 10,001 bug in bbw account.

![bbw balance image](balance.png)

I opened the settings page and click the upgrade button. After clicking the upgrade button, I got the flag.

![upgraded image](upgraded.png)
























 
