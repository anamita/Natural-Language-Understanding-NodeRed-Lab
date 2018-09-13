# Natural	Language Understanding in Node-RED

## Hands-On	Lab

#### JeanCarl	Bisson | jbisson@us.ibm.com | @dothewww
#### Helen Lam | helen.lam@ibm.com | @helennnsays
#### Anamita Guha | anamita.guha@ibm.com | @anamitag

### Introduction
The	Natural Language Understanding	service analyzes	text	to	extract	meta-data	from	content	such	as	concepts,	entities,	keywords,
categories, sentiment, emotion, relations, semantic roles, using natural language understanding. This	tutorial	uses	the	Node-RED
boilerplate	in	IBM	Cloud with	the	Natural	Language	Understanding	service	found	under	the	 **Starter Kit** section	of	the	IBM	Cloud
catalog. To	get	started	using	the	Natural	Language	Understanding	service,	you’ll	need	to	create	service	credentials. A digital copy	of this lab and	code snippets can	be found at: http://ibm.biz/node-red-natural-language-understanding.

### Learning Objectives

After this tutorial, you will be able to:

* Instantiate a Node Red Starter Kit and a Watson Cloud service (Natural Language Understanding API) on IBM's Cloud
* Bind a Watson service to a Node Red application
* Send a news article URL to the NLU API, and retrieve a table of the response in a table containing the concepts,	entities, keywords,
categories, sentiment, emotion, relations, and semantic roles

### Prerequisites

Create an [IBM Cloud Account](https://console.bluemix.net/).
Log into [IBM Cloud](https://console.bluemix.net/login).

### Estimated Time

You should be able to complete in 45 - 60 minutes.

### Step 1 - Set Up Your Node Red Boilerplate

1. Log in and click on Catalog in the top right nav. bar.

2. Click on “Starter Kits” in the left hand menu. Then click on the
“Node Red Starter” option for the boilerplate. You will get:
* a Cloudant database instance to store your ow conguration
* a collection of nodes that make it easy to access various IBM Cloud
services, including Watson, IoT and Blockchain services to name just a few

3. Write a name for your Node Red Boilerplate. You can write “node
red” somewhere in the title, so you will not confuse with your other
future IBM Cloud applications.
4. It will take a few minutes (5–15 minutes) to instantiate. Once it is
nished instantiating, you will see the green circle beside the name of
your app where it will state “running.”

Click on “Visit App URL” to get to your new Node Red boilerplate.

5. Once you click on Visit App URL, you will be taken to your new Node
Red app with a few set up instructions. You can choose to add a
username or password, or leave unsecured. It is up to you.


6. A few other options are available, just keep clicking “next” until you
get to this final page. Click “Go to your Node-RED flow editor.”


7. You will see your first flow. You are ready to begin your first Node
Red flow. Congrats!


### Step 2 - Add	Natural	Language	Understanding Service in	IBM	Cloud

1. Click	on	the	 **Catalog** link	in	the	top-right	of	the	IBM	Cloud	Dashboard.	Under	the	AI	section,	click	on	the	 **Natural
    Language	Understanding** tile. <insert photo >
2. You	can	optionally	give	the	service	a	custom	name	or	leave	it	as	the	one	given.	Click  **Create**.
3. Click	on	 **Connections** in	the	menu	on	the	left.	<insert photo>
4. Click	 **Create	connection** on	the	right.
5. Click	 **Connect** next	to	the	Node-RED	application	you	created	earlier.
6. IBM	Cloud	will	prompt	to	restage	the	application.	Click	on	 **Restage**. The	application	will	restart	and	include	the	new	service
    credentials	in	the	environment.
7. When	the	application	has	finished	restaging,	open	the	Node-RED	Flow	Editor. If	you	already	have	Node-RED	open,	refresh
    the	page.

### Step 3 - Analyze	a	News	Article in	Node-RED

The	Watson	Natural	Language	Understanding	service	takes	either	a	body	of	text or	a	publicly-accessible	URL	to	content	which the
service	can	analyze.	In	this	section,	we	will	analyze	a	news article	that	is	accessible	via	an URL. You	can	also	choose	to	analyze	other
URLs	that	contain	a	body	of	text.

1. Add	a http node as	shown	below.
2. Add	a change node as	shown	below.	This	will	take	the	 _url_ query	parameter	and	place	it	in	the	message	 _payload_ to	be
    passed	to	the	Natural	Language	Understanding node	in	the	next	step. <replace these two with image>
3. Add	a	 node.	Check	the	options	that	you	want	to	be	included	in	the	response. You	can	narrow	the	results	by
    changing	the	maximum	values and/or by	unchecking	checkboxes	next	to	each	feature. For	this	lab,	we	have	enabled	all	the
    options	to	showcase	many	of	the	insights	returned	by	the Watson	service.
4. To	make	this application	versatile,	we’ll	split	the	flow	so	our	application	will return	the	results	in	two	formats.	The	first
    option	will	be where the	results	are	returned	in	JSON	format,	great	for	use	with applications	that	can	call	the web	endpoint
    and	consume	the	JSON.	The	second option	will	be	a	webpage	showing	the	data	in	a	human	readable	report.	Add	a
       node	as	shown	below.


5. For	the	flow	where	the	JSON	should	be	returned,	we	can	simply	return	the	contents	of	 _msg.features_ .	Add	a
    node as	shown	below.	This	will	move	the	results	from	the	 _features_ property	to	the	message	 _payload_.
6. For	the	flow	where	a	webpage	should	be	returned,	add	a	 node	with	the	HTML	from	the	file	at
    ibm.biz/BdiBpU

##### Get	the	code:

##### ibm.biz/BdiBpU

7. Add	a	 node.	Connect	the	nodes	together	as	shown	below.
8. Click	on	the	red	 button	in	the	top-right	corner	of	the	screen	to	save	and	deploy	your	changes.
9. Visit	a	news	website	and	copy	the	URL	of	a	publicly	accessible	news	article.	Make	sure	the	content	isn’t	behind	an
    authentication	wall where	you	need to	sign	in	to	access	the	content.


10. Open	a	browser	tab	and	visit	your	application’s	endpoint,	passing	in	the	URL	to	the	content:

```
http://<<MY-APP>>.mybluemix.net/analyze?url=<<URL-TO-STORY>>
```
- Replace	<<MY-APP>>	with	the	host of	the	Node-RED	application	you	chose.
- Replace	<<URL-TO-STORY>>	with	the	URL	of	the	content.
11. Depending	on	the	content	located	at	the	URL,	you	may	see	a	list	of	attributes	including	concepts,	entities,	keywords,
categories,	sentiment,	emotion,	relations,	semantic	roles and	more mentioned	within	the	text.
12. To	see the	JSON	representation of	the	content insert _format=json_ in the	URL query	string:

[http://<<MY-APP>>.mybluemix.net/analyze?](http://<<MY-APP>>.mybluemix.net/analyze?) **format=json** &url=<<URL-TO-STORY>>

13. Return	to	Step	#3	and	experiment	by disabling	some	of	the	features	to	see	how	the	results	change.	Try	analyzing other	URLs
    and	see	what	results	are	returned.
