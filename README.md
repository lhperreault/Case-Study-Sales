# Case-Study-Sales

This is a real life case study where I took a problem/inefficiency that myself and other coworkers were having and through trial and error I found a great solution. I am in an internship doing cold call sales for IT companies around the country, trying to get them business in their local area. Essentially, I and my team are sales reps for these IT companies. The goal for me is to find pain or interest in a call and book a meeting for the prospect and my CEO to meet and dive in deeper. 

In sales, it is important to understand the prospect you are calling the best you can. When you get a new list of contacts it takes time to go get this available info online through the many sources out there such as their website, FB, and LI. 
There are two main scenarios the companies I call have related to IT... the company has in-house IT or outsource it to an IT Company (MSP). Using Linked In Sales Navigator you can manual go on and see if this company has IT personal on staff. You can see when they started, the names of their positions, what they do, what software is used. You can find other CXO's in the company that might be decision makers. Finally, if you are wanting to take 10 min per contact you can see on LI Sales NAV if your prospect or other prospects in the company were in the news or posted recently on LI. 
As you can imagine, you can find a lot more great info by looking at their FB, website, X, Google My Business posts, or hiring websites.
The more info a sales rep can get the more personable and relevant he or she can come across when opening, asking questions, and pitching. If one was to really take the time to thoroughly go find all this info it would take about 15-20 a contact. 
Now, from what I understand most of my coworkers are gathering all this info, and mostly rely on the basics on LI Sales Nav which just takes 3 minutes a contact to gather. 

## Issue

The issue is the time it takes to research each prospect thoroughly is too long. With 200 prospects it would take 50 - 66 hours. Most of the guys have 4x200 contacts. This is why they only use at most 3 minutes to research a prospect. And many of them are doing it as they call which is not great because you lose focus and won't perform as well on a call. I felt this way as well. On days where I would have to research my contact as I went, I would make 50% of the calls I normally would and I wouldn't feel as focused and ready for an in-depth conversation. 

## Hypothesized Solution

I need to automate the research step of each prospect. I need to get the most available useful info out there. I need to display all this information efficiently allowing me to access, analyze, and use it when getting on a call. 

## Attempted Solutions

First I looked at what info I wanted to get. LI Sales NAV and LI was essentially all I needed. Some companies use FB/X to post updates. Some smaller ones put info on Google My Business. But the most important info is from LI and LI Sales Nav. This includes generic information about the company, personnel, and posts from the personnel. 
I looked for Hubspot integrations so that I could integrate LI and bring the data to various unused variables on Hubspot. Directly from LI Sales Nav was not possible. 
I looked into using Zapier or Make.com, but there is not a great integration to LI Sales Nav. I looked into using a regular API but again this wasn't great or easy to use.
Realizing how much data I could realistically include also made me realize there will not be enough space on the Hubspot prospect database view to list it all in a nice way.
![image](https://github.com/user-attachments/assets/5635709e-a579-43bc-b384-cc9602be1b0c)

I would have to scroll horizontally to see 3/4 of the important data. I realized I want to be able to control the view displaying and ordering it in the way I want. 
By looking deeper into Hubspot, I found that for each contact there was a company associated with it that had it's own info. This info was directly from LI. The way Hubspot is setup one cannot see this info in the view that I use to contact prospects in. I would have to do 3 extra clicks to get to it, and even once I got there it doesnt have all the info available on Sales Nav. In the company dataset, I found there is the LI company link. I also found I can upload prospects by certain key parameters to LI Sales Nav and create a list. This is what led me to the final solution. 

## Final Solution

I filter all the prospects to get my list. I get a list of their companies too. I download these two datasets with all their data. I have over 200 variables within 2 datasets. 
I upload the company dataset using the key parameters and 226 out of the 266 companies I have match. The missing 40 don't have LI essentially. I go on the list and click view in Search. In search you can filter with many options. 
I filter and get a list of all the CXO's in all these companies. I got around 600. There's no way to download these unless you pay for an extension to do so. Instead I manually do it which does take time. You have to copy and paste by 25 at a time. Copy and paste it to a word doc. This will take like 10 min. Then take the doc and ask chat gpt to make the data into a dataset. This data set should have the CXO name, company name, position, time been there, time in position. I put this into excel and download it. I bring it to VS Code using python and merge it on Company Name with the Hubspot Contacts.["COmpany Name"]. I added this code to the repository. 
Similarly, I search, copy and paste, and merge Count of IT people(if any), IT contact name, and count of employees to the company name. I have to do a fuzzy match to merge it with company name because LI Sales Nav doesn't bring back the exact company name. Some will add Inc. or co. etc. 
In the end I have 7 datasets. The datasets I'm left with are Company, Cyber1 (contacts), CXO, has_IT, new_IT, News, and Posts.
Below is the connection in Power Bi. 
![image](https://github.com/user-attachments/assets/da87b847-9bf9-408e-95a2-24abff2af8c8)

I chose Power Bi because of the Tool Tip feature where I can have a table and hover and see another page. With this I can visualize and order my contacts in the same order as I do in the Hubspot table and see all the data in one place easily and cleanly. Below is a rough draft of the final visual. I am hovering over a contact name and a pop up of all the info I collected neatly shows the data for that contact only.

![image](https://github.com/user-attachments/assets/c9d575c5-d980-4d6f-ae99-09c36bade338)

I can have this displayed on one screen and my hubpost and calling software on my other screen at work and easily scroll as I go updating the contacts in hubspot. 
At the end of the day or week. I can download the contacts data again and update it in VS CODE and Power BI because I will be changing lead status and adding notes which are two important features I can visualize in the Power BI dashboard.

## Implementation

I implemented it. I realized knowing whether they have internal IT or not was really helpful. So far it was pretty accurate. Most of the news and posts didn't help me much with opening statements and it was hard to make relevant questions. There were two that had relevant things to say but I am waiting for them to pick up. Knowing the other CXO is nice because I can use ZoomInfo to search for their mobile numbers easily. 
I realized I need to filter the news and posts a bit more because most of it is irrelevant and takes time to read. Also if there was a way to add the source so I could confirm it would be nice. 
Another thing is having to manually sort of update the info. It takes about 10 min to change the contact info. But when I search and add new posts it takes 20-30 minutes. 

## Improvements

## Other Case Studies 

Ultimately, I need to make this easy enough for my coworkers to do this. Right now, they would have to follow about 30 steps to do this themselves even if I set up the code and Power Bi Dashboard.
Getting prospects from hiring sites that are hiring for IT. Whether they are already a prospect or not I can call them to offer services. 
I can take contact data and call data and do some EDA on it. Furthermore, with all the data I can use ml to possible find the most likely prospects to need our services; I would need to extract all the data from my coworkers because they have months of call data. 
I would love to compile all the data I have, send it to a gpt agent that is trained on my "script' and questions I ask, and make real relevant questions based on each scenario. I know I can do this with Python and Chat GPT's API. 

