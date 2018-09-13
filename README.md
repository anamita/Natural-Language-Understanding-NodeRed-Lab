# Natural Language Understanding in Node-RED

## Hands-On Lab

JeanCarl Bisson | jbisson@us.ibm.com | @dothewww
Helen Lam | helen.lam@ibm.com | @helennnsays
Anamita Guha | anamita.guha@ibm.com | @anamitag

**Introduction**
The Natural Language Understanding service analyzes text to extract meta-data from content such as concepts, entities, keywords,
categories, sentiment, emotion, relations, semantic roles, using natural language understanding. This tutorial uses the Node-RED boilerplate in IBM Cloud with the Natural Language Understanding service found under the **Starter Kit** section of the IBM Cloud
catalog. To get started using the Natural Language Understanding service, you’ll need to create service credentials. A digital copy of this lab and code snippets can be found at: http://ibm.biz/node-red-natural-language-understanding.

**Learning Objectives**
After this tutorial, you will be able to:

- Instantiate a Node Red Starter Kit and a Watson Cloud service (Natural Language Understanding API) on IBM's Cloud
- Bind a Watson service to a Node Red application
- Send a news article URL to the NLU API, and retrieve a table of the response in a table containing the concepts, entities, keywords,
- categories, sentiment, emotion, relations, and semantic roles

**Prerequisites**
Create an [IBM Cloud Account](https://console.bluemix.net/).
Log into [IBM Cloud](https://console.bluemix.net/login).

**Estimated Time**
You should be able to complete in 45 - 60 minutes.

**Step 1 - Set Up Your Node Red Boilerplate**

1. Log in and click on Catalog in the top right nav. bar.
![](https://d2mxuefqeaa7sj.cloudfront.net/s_24EE0666F224CD27E72F26041F4521C1DF0F229C7CDD0C52E547CB024B22846E_1536802926926_Hello1.png)

2. Click on “Starter Kits” in the left hand menu. Then click on the “Node Red Starter” option for the boilerplate. You will get:
- a Cloudant database instance to store your flow configuration
- a collection of nodes that make it easy to access various IBM Cloud services, including Watson, IoT and Blockchain services to name just a few
3. Write a name for your Node Red Boilerplate. You can write “node red” somewhere in the title, so you will not confuse with your other future IBM Cloud applications.
![](https://d2mxuefqeaa7sj.cloudfront.net/s_24EE0666F224CD27E72F26041F4521C1DF0F229C7CDD0C52E547CB024B22846E_1536803109239_Screen+Shot+2018-09-12+at+9.44.16+PM.png)

4. It will take a few minutes (5–15 minutes) to instantiate. Once it is finished instantiating, you will see the green circle beside the name of your app where it will state “running.” 

Click on “Visit App URL” to get to your new Node Red boilerplate.

![](https://d2mxuefqeaa7sj.cloudfront.net/s_24EE0666F224CD27E72F26041F4521C1DF0F229C7CDD0C52E547CB024B22846E_1536803327692_Screen+Shot+2018-09-12+at+9.46.10+PM.png)

5. Once you click on Visit App URL, you will be taken to your new Node Red app with a few set up instructions. You can choose to add a username or password, or leave unsecured. It is up to you. 
![](https://d2mxuefqeaa7sj.cloudfront.net/s_24EE0666F224CD27E72F26041F4521C1DF0F229C7CDD0C52E547CB024B22846E_1536803369768_Screen+Shot+2018-09-12+at+9.46.59+PM.png)


A few other options are available, just keep clicking “next” until you get to this final page. Click “Go to your Node-RED flow editor.” 

![](https://d2mxuefqeaa7sj.cloudfront.net/s_24EE0666F224CD27E72F26041F4521C1DF0F229C7CDD0C52E547CB024B22846E_1536803420258_Screen+Shot+2018-09-12+at+9.47.09+PM.png)

6. You will see your first flow. You are ready to begin your first Node Red flow. Congrats!
![](https://d2mxuefqeaa7sj.cloudfront.net/s_24EE0666F224CD27E72F26041F4521C1DF0F229C7CDD0C52E547CB024B22846E_1536803441275_Screen+Shot+2018-09-12+at+9.47.20+PM.png)



