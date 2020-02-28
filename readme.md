# Exploring Ford GoBike System Data
## by Duyen Nguyen


## Dataset

> The dataset contains data for 4,256,681 anonymized trips with attributes including bike ID, start time, end time, duration of trip in seconds; ID, name, longitude, latitude of start station and end station; user information i.e. birth year, gender, user type, rental access method and whether user belongs to the Bike Share for All program.

There are two user types: Subscriber and Customer. User's genders include 'Male', 'Female' and 'Other'. Users can access the rental bikeshare program via the Lyft app or their own Clipper card.

The main interest in exploring this dataset is finding out how trip duration changes based on each day of the week, month and year. Another point of interest is the volume of trips taken each day, month and year. I would also like to determine whether user types, gender and age have any effect on trip duration.


## Summary of Findings

### Univariate Exploration

Trip duration in seconds has a very large range from 60 to well over 86,000, which makes the initial plot heavily skewed to the right with a very long tail. Therefore, I performed a log transformation on the x axis. The resulting histogram is unimodal and normally distributed with a peak at around 500 seconds.

The vast majority of users are male subscribers while females and other genders account for about a quarter of the user population. Most users are in their 20s, 30s, and 40s. However, there are some users with age over 90. This is almost impossible to happen and is likely to be errors in user input. These data will be removed from the dataset to avoid skweing further analysis.

As the datasets obtained only started in June 2017, the number of trips taken in 2017 is significantly lower than those of 2018 and 2019, which are almost equal to each other. However, data in 2019 ends in September so it is safe to assume that the number of trips have been steadily increasing each year. Trip volume increases towards the summer months and peaks in September before sharply decreases towards the end of the year. This trend makes perfect sense due to the warmer summer weather that is optimal for biking, while the colder winter weather means users tend to opt for other forms of transportation.

On a daily basis, the majority of trips tend to fall on the beginning of the week, peaking on Thursday, and plunges on weekends. This trend coincides with the normal work week from Monday to Friday, which also explains the bimodal distribution when it comes to time of the day trips are taken. Trip volume reaches two peaks consecutively at the beginning of a workday at 8 AM and again at the end of the workday at 5 PM. There is also a slight increase during lunch hours.

### Bivariate Exploration

As seen in the Univariate Exploration section, the vast majority of trip durations are under 2,000 seconds. As expected, the average trip duration remain relatively the same over the years. During each year, trips tend to be longer during the summer months. On a daily scale, weekend trips are significantly longer than weekday trips. This could signify the difference in purpose as weekday trips are potentially more task-oriented while weekend trips can be more leisure-oriented.

Between subscribers and customers, the former tend to take much shorter trips averaging 500 seconds, while the latter's average trip duration is about 750 seconds. This seems counter-intuitive since subscribers paying either monthly or yearly fee get to ride the first 45 minutes, or 2,700 seconds, for free, which should encourage them to take longer rides. A potential explanation for this difference is a subscriber possibly is willing to commit to a monthly/yearly payment because of higher frequency of usage, which means a wider variety of trip purposes and shorter trip durations. This, however, requires more data in user behaviors to come to a more definite conclusion.

Female users and users identify as 'Other' appear to take longer trips than males. There seems to be no correlation between trip duration and member's age, contrary to my initial assumption that trip duration decreases with age.

Based on the longitudes and latitudes of these locations, it can be inferred that most trips are made between three major cities of Bay Area: San Francisco, Oakland and San Jose, with the most trips made between San Francisco and San Jose, followed by San Francisco - Oakland and Oakland - San Jose.

### Multivariate Exploration

As observed in previous sections, average duration of trips tend to vary slightly at the beginning of the week and steadily increases towards the weekend. Meanwhile, number of trips on each day sees the opposite trend, decreasing slightly on Friday, significantly on Saturday and hitting bottom on Sunday. We can see this relationship clearer in a scatterplot. Although the negative correlation between these two features is relatively weak, this observation is helpful in gaining more insights into user behavior.

Upon a deeper look into demographics data, an interesting trend was found in member's age over the years. It appears that users of the Bay Wheels program are getting younger year after year. This reflects a change in awareness to the bikeshare program of the younger population.






## Key Insights for Presentation

### Distribution of trip duration (secconds)

It appears that trip duration has a very large range in values, from 60 to over 86,000. As there are outliers with extra large values, the next plot will be limited to trips lasting under 6,000 seconds. After a log transformation on the x axis, the data appears to be normally distributed with a peak at about 500 seconds, indicating the typical duration for a bike trip. However, because of the outliers, the average trip duration is about 800 seconds.

### Volume of trips in each year, month, day of the week and hour of the day

Trip volume increases towards the summer months and peaks in September before sharply decreases towards the end of the year. This trend makes perfect sense due to the warmer summer weather that is optimal for biking, while the colder winter weather means users tend to opt for other forms of transportation.

On a daily basis, the majority of trips tend to fall on the beginning of the week, peaking on Thursday, and plunges on weekends. This trend coincides with the normal work week from Monday to Friday, which also explains the bimodal distribution when it comes to time of the day trips are taken. Trip volume reaches two peaks consecutively at the beginning of a workday at 8 AM and again at the end of the workday at 5 PM. There is also a slight increase during lunch hours.

### Trip duration vs. number of trips on a weekly basis

It seems like on a weekly basis, number of trips and average duration of trips are potentially inversely correlated to each other. As observed in the two plots in this section, average duration of trips tend to vary slightly at the beginning of the week and steadily increases towards the weekend. Meanwhile, number of trips on each day sees the opposite trend, decreasing slightly on Friday, significantly on Saturday and hitting bottom on Sunday. In a scatterplot, we can see that negative correlation between these two features is relatively weak.