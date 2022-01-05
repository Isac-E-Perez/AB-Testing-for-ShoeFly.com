# A/B Testing for ShoeFly.com Project
### About: 

For this project, I implemented data analysis using R. I used the libraries readr, and dplyr which helped me to build the project. I analyze the data of ShoeFly.com to gain a better understanding and insight of the two different version of an ad, that were placed in emails, as well as in banners ads on Facebook, Twitter, and Google. The company wanted to know how the two ads performed on each of the different platforms on each day of the week. The project helps the company analyze the data using aggregate measures.  
 
### Note:

This data comes from ShoeFly.com 

  
### Results: 

First, I wanted to know which platfrom was getting the most views and named the variable *views_by_utm*.

```R
# define views_by_utm here:
views_by_utm <- ad_clicks %>%
group_by(utm_source) %>%
summarize(count = n())
head(views_by_utm)
```

```R
## # A tibble: 4 x 2
## utm_source count
##   <chr>    <int>
## 1 email     255
## 2 facebook  504
## 3 google    680
## 4 twitter   215
```

Afterwards, I found the percentage of users, by platform, who clicked on an ad. Then, I filtered *ad_click* to ensure that only those who clicked the ad would be counted and compared with.

**Original Data grouped by *utm_source*, *ad_clicked***

```R
## # A tibble: 6 x 3
## utm_source ad_clicked count
##   <chr>    <lgl>    <int>
## 1 email     FALSE     175
## 2 facebook  TRUE       80
## 3 google    FALSE     324
## 4 twitter   TRUE      180
## 5 google    FALSE     441
## 6 google    TRUE      239
```

**Percentage + Filter**

```R
# define percentage_by_utm here:
percentage_by_utm <- clicks_by_utm %>%
group_by(utm_source) %>%
mutate(percentage = count/sum(count)) %>%
filter(ad_clicked==TRUE)
head(percentage_by_utm)
```

```R
## # A tibble: 4 x 4
## utm_source ad_clicked count percentage
##   <chr>    <lgl>    <int>    <dbl>
## 1 email     TRUE      80     0.314
## 2 facebook  TRUE     180     0.357
## 3 google    TRUE     239     0.351
## 4 twitter   TRUE      66     0.307
```
  
Secondly, I wanted to know how many user were shown ad A or ad B from all platforms and clicked on it.  

**How many users were shown the add, *experiment_split*** 

```R
# define experiment_split here:
experiment_split <- ad_clicks %>% group_by(experimental_group) %>%
summarize(count=n())
head(experiment_split)
```

```R
## # A tibble: 2 x 2
## experimental_group count
##   <chr>    <int>
## 1 A          827
## 2 B          827 
```

Approximately the same number of epople were shown both ads.

**How many users clicked the add, *clicks_by_experiment***

```R
clicks_by_experiment <- ad_clicks %>%
group_by(ad_clicked, experimental_group) %>%
summarize(count=n()) %>%
filter(ad_clicked==TRUE)
head(clicks_by_experiment)
```

```R
## # A tibble: 2 x 2
## experimental_group count
##   <lgl>    <chr>    <int>
## 1 TRUE     A          310
## 2 TRUE     B          255
```
 
From the analyzed data we could see that ad A had more clicks than ad B. 

There is more information to gather though. We could also see how well each ad performed during the week by comparing ad A and B and following similar steps we done before.   
 
 **Ad A's performance during the week + percentage + filtered non-clicks**
 
```R
## # A tibble: 7 x 4
## # Groups: day [7]
##   day      ad_clicked count    percentage
##   <chr>          <lgl>      <int>    <dbl>
## 1 1 - Monday     TRUE          43    0.381
## 2 2 - Tudesday   TRUE          43    0.361
## 3 3 - Wednesday  TRUE          38    0.306
## 4 4 - Thursday   TRUE          47    0.405
## 5 5 - Friday     TRUE          51    0.398
## 6 6 - Saturday   TRUE          45    0.381
## 7 7 - Sunday     TRUE          43    0.394
```
 
 **Ad B's performance during the week + percentage + filtered non-clicks** 
 
```R
## # A tibble: 7 x 4
## # Groups: day [7]
##   day      ad_clicked count    percentage
##   <chr>          <lgl>      <int>    <dbl>
## 1 1 - Monday     TRUE          32    0.283
## 2 2 - Tudesday   TRUE          45    0.378
## 3 3 - Wednesday  TRUE          35    0.282
## 4 4 - Thursday   TRUE          29    0.250
## 5 5 - Friday     TRUE          38    0.297
## 6 6 - Saturday   TRUE          42    0.356
## 7 7 - Sunday     TRUE          34    0.312
```
 
After analyzing the data, ad A outperformed ad B on every day of the week except Tuesday and Sunday. It seems that ad A is the best choice for ShoeFly.com
