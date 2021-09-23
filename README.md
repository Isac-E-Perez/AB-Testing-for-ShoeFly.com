# A/B Testing for ShoeFly.com Project
### About: 

For this project, I implemented data analysis using R. I used the libraries readr, and dplyr which helped me to build the project. I analyze the data of ShoeFly.com to gain a better understanding and insight of the two different version of an ad, that were placed in emails, as well as in banners ads on Facebook, Twitter, and Google. The company wanted to know how the two ads performed on each of the different platforms on each day of the week. The project helps the company analyze the data using aggregate measures.  
 
### Note:

This data comes from ShoeFly.com 

  
### Results: 

First, I wanted to know which platfrom was getting the most views and named the value *views_by_utm*.

 <img width="234" alt="Screen Shot 2021-09-23 at 3 43 35 PM" src="https://user-images.githubusercontent.com/89553126/134581205-6f275991-59d5-492a-8151-28cb17618a9e.png">

<img width="179" alt="Screen Shot 2021-09-23 at 3 43 46 PM" src="https://user-images.githubusercontent.com/89553126/134581232-96d4b586-7f19-4ef9-a156-97868c08eedc.png">

Afterwards, I found the percentage of users, by platform, who clicked on an ad. Then, I filtered *ad_click* to ensure that only those who clicked the ad would be counted and compared with.

**Original Data grouped by *utm_source*, *ad_clicked***

<img width="267" alt="Screen Shot 2021-09-23 at 1 22 44 PM" src="https://user-images.githubusercontent.com/89553126/134562708-0ab687e7-1bb1-4c38-9129-c21b4ee0fd0b.png">

**Percentage + Filter**

<img width="329" alt="Screen Shot 2021-09-23 at 1 22 59 PM" src="https://user-images.githubusercontent.com/89553126/134562734-f87f80be-a985-4052-8dfc-e133c6b19d77.png">


 <img width="351" alt="Screen Shot 2021-09-23 at 1 23 04 PM" src="https://user-images.githubusercontent.com/89553126/134562743-ad23f721-6df1-41d0-926e-578deb0e3602.png">
  
Secondly, I wanted to know how many user were shown ad A or ad B from all platforms and clicked on it.  

**How many users were shown the add, *experiment_split*** 

<img width="525" alt="Screen Shot 2021-09-23 at 3 57 30 PM" src="https://user-images.githubusercontent.com/89553126/134582990-ce535b7c-7cc5-4e48-b921-96a180651a83.png">

<img width="234" alt="Screen Shot 2021-09-23 at 3 57 41 PM" src="https://user-images.githubusercontent.com/89553126/134583002-66d600ac-db03-4ade-9c11-d81661a90ba2.png">

Approximately the same number of epople were shown both ads.

**How many users clicked the add, *clicks_by_experiment***

<img width="356" alt="Screen Shot 2021-09-23 at 3 49 18 PM" src="https://user-images.githubusercontent.com/89553126/134581966-d233c3f8-5be1-420d-bb1a-a648476666a5.png">

<img width="320" alt="Screen Shot 2021-09-23 at 3 49 39 PM" src="https://user-images.githubusercontent.com/89553126/134581977-fd7![Uploading Screen Shot 2021-09-23 at 3.57.30 PM.png…]()
d2e41-d0f9-425d-a609-ee013cf03f97.png">

From the analyzed data we could see that ad A had more clicks than ad B. 

There is more information to gather though. We could also see how well each ad performed during the week.   
 
After analyzing the data, ad A outperformed ad B on every day of the week except Tuesday and Sunday. It seems that ad A is the best choice for ShoeFly.com

 

 
