<img src="https://www.splunk.com/content/dam/splunk2/images/social/D2E-social.jpg" width=25% height=25%>
<h1>Perform a Query With Splunk</h1>

<h2>Overview</h2>
SIEM tools such as Splunk are an important part of a security analyst's toolbox because they provide a platform for storing, analyzing, and reporting on data from different sources.
In this activity, we'll be introduced to the Splunk platform. We will use Splunk Cloud to upload data and perform basic searches on the data.
Creating effective searches is an important skill because it enables us to quickly and accurately find the information we are looking for within a large amount of data. Quick and accurate searching is especially useful during incident response, because we might need to swiftly identify and address a security incident. Effective search techniques also help us efficiently identify patterns, trends, and anomalies within data.
<br />

<h2>Scenario</h2>
We are a security analyst working at the e-commerce store Buttercup Games. We've been tasked with identifying whether there are any possible security issues with the mail server. To do so, we must explore any failed SSH logins for the root account.  

<h2>Create Splunk Account</h2>

1 - Go to the [Splunk Cloud Platform Trial](https://www.splunk.com/en_us/download/splunk-cloud/cloud-trial.html) page and create an account.
<br />

<img src="https://github.com/Hashdan-M/images/blob/main/Splunk/Create-your-account.png" >
<br />
2 - Check the inbox for the verification email from Splunk
<br />

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/Verify-your-email-pt-2.png" >
<br />
3 - Activate a Splunk Cloud trial
<br />

<img src= "https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/start-trial-pt-1.png" >

<img src= "https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/plunk-Cloud-login-information.png" >

<h2>Upload Data Into Splunk</h2>

To operate effectively, it's essential that SIEM tools ingest and index data. SIEM tools collect and process data so that it becomes searchable events that can be queried, viewed, and analyzed. So far, we have created a Splunk account and activated and accessed the Splunk Cloud free trial, but our Splunk Cloud instance does not contain any data. We will need to upload data into Splunk to start querying. We will use sample data taken from the Google Cybersecurity Professional Certificate course.

Navigate to Splunk Home from the Splunk Cloud free trial instance.

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20sign%20in.PNG"/></a>

On the Splunk bar, click ***Settings***. Then click the ***Add Data*** icon.

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20add%20data.PNG"/></a>

Click ***Upload***.

Click the ***Select File*** button.

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20select%20file.PNG"/></a>

We will upload the ***tutorialdata.zip*** file and click ***Open***.

Click the ***Next*** button to continue to ***Input Settings***.

By the ***Host*** section, select ***Segment in path*** and enter ***1*** as the segment number.

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20segment.PNG"/></a>

Click the ***Review*** button and review the details of the upload before we submit. The details should be as follows: 

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20review.PNG"/></a>

Click ***Submit***. Once Splunk has ingested the data, we will receive confirmation that the file was successfully uploaded.

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20success%20upload.PNG"/></a>

<h2>Perform a Basic Search</h2>

From the ***Apps*** dropdown menu, select ***Home***

Take a moment to examine the Splunk Cloud interface

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20interface.PNG"/></a>

Now that we've uploaded the data into Splunk, we will perform our first query to confirm that the data has been ingested, indexed, and is searchable. Follow these steps to perform a query:

Navigate to Splunk Home. (To return to Splunk Home, click the Splunk Cloud logo on the Splunk Cloud page.)

Click ***Search & Reporting***. Close any pop ups that appear.

In the search bar,  enter the search query:
***index=main***

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20search.PNG"/></a>

This search term specifies the index. An index is a repository for data. Here, the index is a single dataset containing events from an index named main.

Select ***All Time*** from the time range dropdown to search for all the events across all time.

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20all%20time.PNG"/></a>

Click the search button. Note that the search button is represented by the magnifying glass icon. 

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20search%20button.PNG"/></a>

Our search should retrieve thousands of events.

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20events.PNG"/></a>

<h2>Evaluate the Fields</h2>

When Splunk indexes data, it attaches fields to each event. These fields become part of the searchable index event data. This helps security analysts easily search for and find the specific data they need. Now that we've run our first query, examine the search results and the fields.

For each event the fields are ***host***, ***source***, and ***sourcetype***. Under ***SELECTED FIELDS***, examine the same fields.

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20fields.PNG"/></a>

Examine the field values by clicking on the field under ***SELECTED FIELDS***. We should observe the following:

***host***: The host field specifies the name of the network host from which the event originated. In this search there are five hosts:

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20host.PNG"/></a>

- ***mailsv*** - Buttercup Games' mail server. Examine events generated from this host.

- ***www1*** - This is one of Buttercup Games' web applications.

- ***www2*** - This is one of Buttercup Games' web applications.

- ***www3*** - This is one of Buttercup Games' web applications.

- ***vendor_sales*** - Information about Buttercup Games' retail sales.

***source***: The source field indicates the file name from which the event originates. We should identify eight sources. Notice ***/mailsv/secure.log***, which is a log file that contains information related to authentication and authorization attempts on the mail server.

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20source.PNG"/></a>

***sourcetype***: The sourcetype determines how data is formatted. We should observe three sourcetypes. Examine ***secure-2***.

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20sourcetype.PNG"/></a>

<h2>Narrow the Search</h2>
Because we've been tasked with exploring any failed SSH logins for the root account on the mail server, we'll need to narrow the search results for events from the mail server.

<br />
<br />

Under ***SELECTED FIELDS***, click ***host*** and click ***mailsv***.

Notice that a new term has been added to the search bar: ***index=main host=mailsv***.

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20index.PNG"/></a>

The search results have narrowed to over 9000 events that are generated by the mail server.

<h2>Search for a Failed Login for Root</h2>
Now that we've narrowed our search results to events generated by the mail server, continue to narrow the search to locate any failed SSH logins for the root account. 

<br />
<br />
Clear the search bar.

Enter ***index=main host=mailsv fail* root*** into the search bar.

This search expands on the search from the previous task and searches for the keyword ***fail****. The wildcard tells Splunk to expand the search term to find other terms that contain the word "fail" such as "failure", "failed", etc. Lastly, the keyword ***root*** searches for any event that contains the term "root".

Click ***search***.

<img src="https://github.com/Hashdan-M/images/blob/28c818049069d025dc42e0faa9161532b11fcf0d/Splunk/splunk%20root.PNG"/></a>

Our search should have retrieved search results for over 300 events. Navigate to other pages of the search results to observe the events not listed on the first page of results.

<h2>Evaluate the Search Results</h2>

**Answer questions about the search results**

1. How many events are contained in the main index across all time?

2. Which field identifies the name of a network device or system from which an event originates?

3. Which of the hosts used by Buttercup Games contains log information relevant to financial transactions?

4. How many failed SSH logins are there for the root account on the mail server?

**Answers**   

1. 109,864 events
2. ***host***
3. ***vendor_sales***
4. 346

<h2>Key Takeaways</h2>

In this activity, we used Splunk Cloud to perform a search and investigation. Using Splunk Cloud, we were able to:

- Upload sample log data 

- Search through indexed data

- Evaluate search results

- Identify different data sources 

- Locate failed SSH login(s) for the root account
