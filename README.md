# IEEE Women in Engineering UON: Create your first Smart Virtual Assistant on IBM Cloud 


In this workshop, we are going to create a  customer service Assistant for a bank. We are looking to automate some of the top questions that are reaching our agents via support chat on our site,in this scenario - people trying to transfer money to friends or family.

We will Start by redirecting people contextually into the bank's application if they have a transfer to make under $1000

## Prerequisites
- [IBM Cloud Account](http://ibm.biz/ieeexibm)
- 

## Step 1: Sign-up/Login to IBM Cloud

1.1- If you are an existing user, click on this link to Login: http://ibm.biz/ieeexibm 

And if you are not, don't worry! We have got you covered! There are 3 steps to create your account on IBM Cloud: 

1.2- Put your email and password. 

1.3- You get a verification link with the registered email to verify your account. 

1.4- Fill the personal information fields. 

** Please make sure you select the country you are in when asked at any step of the registration process.

![image](https://user-images.githubusercontent.com/16270682/140926329-d798e427-5b56-4b6c-bfe7-aacf4543b24c.png)

## Step 2: Create an instance of Watson Assistance service

2.1 - Fron Dashboard search for Watson Assistant service in catalog 

<img width="585" alt="1" src="https://user-images.githubusercontent.com/16270682/140980671-23b74739-acd5-4a1d-9ed5-fb164d05f0bf.PNG">


2.2 - Check the terms box and click on create. This will take you to a new window

<img width="825" alt="2" src="https://user-images.githubusercontent.com/16270682/140980692-2de653ce-f4ea-4bc2-89c6-a179d6a7eb8b.PNG">


2.3 - Click on Launch Watson Assistant to start building your chatbot

<img width="710" alt="3" src="https://user-images.githubusercontent.com/16270682/140980716-fe3b93a3-98b1-4128-b6c6-a4f236beb33c.PNG">


2.4 - Go to top right, select manage > Switch to new experience, it will prompt a confirmation message, click on switch.

<img width="957" alt="140980993-13e3a96b-29f1-4e8d-9e4e-50694575c48f" src="https://user-images.githubusercontent.com/16270682/141315408-eafea0d8-5fd8-4aab-a7fb-c16d80c44d12.PNG">


## Step 3: Create your first assistant

3.1- Name your assistant and click on create 
<img width="718" alt="6" src="https://user-images.githubusercontent.com/16270682/140990991-b532b434-4c16-4f07-91b7-7d52a1052f51.PNG">


3.2 - From the home window, select your first action, this will take you to a new window.
<img width="521" alt="7" src="https://user-images.githubusercontent.com/16270682/140990999-45272753-e681-4bf4-ac46-f9ce886457ab.PNG">


## Step 4: Create your First action

4.1 - click on  create a new action


<img width="611" alt="8" src="https://user-images.githubusercontent.com/16270682/141001953-15ebda6a-ed8f-4f9d-8819-667cd1ed9d24.PNG">


4.2 - add "I want to transfer $100 to my friend" and click save

<img width="439" alt="8-1" src="https://user-images.githubusercontent.com/16270682/141002029-eaeb7f69-002d-49e4-9ea8-02d657a91836.PNG">


#### We are going to setup 3 steps for our action


4.3 - change the title of the action in the top left to something more consumable - "Transfer funds"

4.6 - Step 1: In our first step, enter **"How much would you like to transfer?"** and Under options, we can define the type of response we anticipate from the user. select **currency** and click on next step

<img width="687" alt="8-2" src="https://user-images.githubusercontent.com/16270682/141002064-80f377c8-ff34-4d31-b6fb-d78342d82a0e.PNG">


4.7 - Step 2: In our second step, enter **"When do you want to make this transfer?"** select **date** 

***Note that the system can detect dates in plain language, not just formatted (e.g. tomorrow, two weeks from now, etc...)***

<img width="690" alt="10" src="https://user-images.githubusercontent.com/16270682/141002082-8c9cb0fc-7ac4-402b-8dbc-5284bfce3a04.PNG">



4.7 - Step 3 (a): In our third step, add a simple confirmation message to make sure we've got everything right. add "Just confirming, you want to transfer $ "$step1" on "$step2?"

Notice how we can use the $ sign to call upon pieces of information the user has already provided in an earlier step - these are called variables

<img width="718" alt="11" src="https://user-images.githubusercontent.com/16270682/141002097-be91b270-179d-45ea-91b2-6e2e5d55be56.PNG">

In this step, you can also define options for our customers from directly within the step itself - unlike most tools which require you to set up a separate "entity"
Let's add yes and no under **options**, We can even add some synonyms for Yes and No yeah, ya, nah, nope. Also change the skip step setting to "always ask".

![9914888687f9cbaed1444ecdbaf8cda81db0697b](https://user-images.githubusercontent.com/16270682/141095702-c458b50f-74a1-4352-9b50-5444ce8cf0b5.gif)


4.8 - Step 3(b): let's define what happens if the user selects Yes or No. In this step, user selects YES. 

To set this up, we will add a condition, which must be met for this step to be triggered

add **"Great, let's finish the transfer directly in our app where we will gather your account information and the transfer destination. Click here to continue."** 

Highlight "click here to continue" and make it a link. In the link, type the following:
"dtebank.com/transfer?date=(step1)&amount=(step2)" You can, in fact, add variables to your URL, if your transactional engine requires it
We must then indicate to the system that this step ends the action successfully

![a690876349b2fcc13fcb7a89c85b58d50d5061da](https://user-images.githubusercontent.com/16270682/141098228-7e311c80-4f79-406f-b7e7-adc355d198ea.gif)


4.9 - Step 3(c): let's define what happens if the user selects No. 

Add **"Whoops! Let's start over."**

In this case, instead of ending the action, we'd want to re-prompt previous steps so the user can start over. Select all of them so that the user goes back to the beginning of the action. Select every step (1-4) to re-prompt

![f69f5ff044209b769ae127327f5208fc53ab1807](https://user-images.githubusercontent.com/16270682/141099336-7a672246-3756-4b27-bd5b-6b16e1aee779.gif)


## Step 5: Preview

To test your chatbot, click on preview and try it out like below.

![ef0cd7abef668e469c138f68978aa47e54a56c2c](https://user-images.githubusercontent.com/16270682/141103224-b6baf2ec-d9e4-40a7-87d5-7faa9585f137.gif)


## Step 6: digressions

5.1 - Truly complex situations, such as when customers change the topic of a conversation entirely mid-flow, are called digressions. 

In this example, let's plan for scenarios where your customer asks what the transfer limit is during the transfer flow. To do this, we simply need to build a new action with a single step in response
Create new action > add example **"What is the transfer limit?"** then, Edit step 1 **"The maximum daily transfer limit for all customers is $10,000."**. And then: End the action


![5a5a803e7754df7a232738bd4096c23d593f7335](https://user-images.githubusercontent.com/16270682/141100667-340ad900-79ed-4f3f-a5eb-c781a476f7bd.gif)


## Step 7: Test Digression in Preview

7.1 - To test your chatbot's digression capabilities, click on preview and try it out like below. Here you can notice how Watson Assistant jumps back to previous step after digression.

![7297d2e493c47f0c553c97338eb389ad367a804a](https://user-images.githubusercontent.com/16270682/141104393-5158cc33-6469-4846-9ea5-56fb9ff91069.gif)


## Step 8: Integration

Now we will see how you can integrate your Watson Assistant as web-chat and with third party tools

#### Web Chat

8.1 - Open Navigation bar, select integration and select Web Chat. Keep the environment as draft and click confirm.

<img width="848" alt="12" src="https://user-images.githubusercontent.com/16270682/141107416-6d874d51-8682-46ea-b6ca-c791c8178cfe.PNG">
<img width="539" alt="13" src="https://user-images.githubusercontent.com/16270682/141107447-cbeb4ed2-923c-4e07-8752-9aebf9e92a10.PNG">


8.2 - Here you can customize your Chatbot as below

![a18ec6db6011caecea6f64180c74e55c66b4a416](https://user-images.githubusercontent.com/16270682/141112537-82e19203-b842-48d0-8e3a-2136a4451a59.gif)

8.3 - To integrate your chatbot with your application, simply copy the code from Embed section and paste it in Header of your application's HTML file and your chatbot will be integrated. You can test it locally as well as with your live application.


### Things you can Try Further:

[Develop an AI-infused automation tool to convert business FAQs to Watson Assistant-ready chatbot input](https://developer.ibm.com/articles/develop-an-ai-infused-automation-tool-to-convert-business-faqs-to-watson-assistant-ready-chatbot-input/?mhsrc=ibmsearch_a&mhq=watson%20assistant)





