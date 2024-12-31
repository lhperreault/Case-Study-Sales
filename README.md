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
I filter and get a list of all the CXO's in all these companies. I got around 600. There's no way to download these unless you pay for an extension to do so. Instead I manually do it which does take time. You have to copy and paste by 25 at a time. Copy and paste it to a word doc. This will take like 10 min. Then take the doc and ask chat gpt to make the data into a dataset. This data set should have the CXO name, company name, position, time been there, time in position. I put this into excel and download it. I bring it to VS Code using python and merge it on Company Name with the Hubspot Prospects.
Similarly I search, copy and paste, and merge Count of IT people(if any), IT contact name, count of employees.
## Implementation

## Improvements
## Other Case Studies 
Getting prospects from hiring sites that are hiring for IT. 
