In the chart below we see the $clubCount clubs that are part of this data set<sup>1</sup>. 
The size of each bubble reflects the amount of RA users that follow the club, 
while its colour denotes the *cluster* it belongs to. 

The clusters are calculated based on how similar the line ups for each pair of 
clubs are. If two clubs have booked many of the same artists and djs then they 
are more likely to be in the same cluster<sup>2</sup>.

Click on each club to see more details about it, which artists featured 
on their line up most often and which other clubs are similar. Use the filters 
in the upper left hand corner to find a specific club. Keep scrolling to learn more.

<details>
<summary>Show footnotes</summary>

1\. We looked at the most recommended clubs from the  are the top 20 regions in April 2020. Most regions had 8 "recommended" clubs. But some had far fewer, the South of Spain for instance [only had 2](https://www.residentadvisor.net/guide/es/south). The "Streamland" region was excluded entirely as it is not relevant for our purposes.

2\. To calculate clusters we first calculate the overlap in lineups between each pair of clubs. Based on how many bookings the two venues have in common we calculate what is called the [Jaccard index](https://en.wikipedia.org/wiki/Jaccard_index). 

From these calculations we create a [network](https://en.wikipedia.org/wiki/Graph_(discrete_mathematics) where the clubs are the nodes and their Jaccard index values are the edges connecting the nodes. We then run [community detection](https://en.wikipedia.org/wiki/Louvain_modularity) algorithms on the network to detect clusters or communities of clubs that are strongly internally connected. This ends up grouping together similar clubs.

</details>


--- 

Lets take a look at the clubs of a specific region. Here is 
[Berlin](https://www.residentadvisor.net/events/de/berlin), one of the worlds 
clubbing capitals.

It is noticeable that except for *Berghain / Panorama Bar* all these clubs belong 
to the same cluster. A similar pattern holds for quite a 
few regions and countries, perhaps because many clubs rely on local or domestic 
talent for many of their bookings while the superclubs book a wider variety 
of international talent?

--- 

But how similar are the most popular clubs on Resident Advisor?

Let's compare two great clubs, Berlin's *Berghain / Panorama Bar* and
*De School* in Amsterdam. Their line ups have a 9.58% overlap. We went into 
this project thinking that the line ups were more similar than they turned out to be. 
For these two clubs for instance, we assumed that the overlap would be greater 
since their music policies feel quite similar. 
 
Whether you find 10% high or low depends on your perspective of course. Should 
each city or club have their own distinct scenes and flavours? Or is it to be 
expected that big global names dominate clubs across continents?

As a whole, out of $combinations possible pairs of clubs, $linkCount pairs had some overlap 
and out of those the average overlap was $averageWeight%. *$source* and *$target* have 
the most similar line ups, with $weight% overlap in their bookings.

---

Now the graph has changed and shows the average number of bookings per artist 
per club, something we call "*the residency factor*". We take the number of unique 
artists booked at a club and divide that number by the total number of bookings, 
that shows us how often an artist is booked on average at that club<sup>3</sup>.

For clubs that rely more on residents, the same artists playing at a club regularly and repeatedly, 
this number would be higher whereas if you only book each artist once this number would be 1.

For example, let's say we had a club that booked _DJ X_ 10 times and _DJ Y_ 5 
times in 2019. Their *residency factor* would be 7.5, as there were a total of 15 
bookings (10+5) for 2 artists (15/2=7.5).

The average residency factor is $averageResidency and only a handful of clubs go above 2.

Click or hover on individual clubs to see more information on them.

<details>
<summary>Show footnotes</summary>

3\. A few caveats here. For this view we've filtered out clubs that had less than 10 dates or booked fewer than 20 artists in total in 2019. 

Furthermore all the data here is limited to djs and artists that have a profile on Resident Advisor. For some genres and scenes, like house and techno, this the coverage is near complete, but for <a href="https://www.residentadvisor.net/events/1281396">others</a> this data is sometimes incomplete.

</details>

--- 

Though the average residency factor seems low, there are plenty of regularly 
and repeatedly booked residents at these clubs. In fact the most booked artists 
in this data set are ones that are doing week after week at the same 
club. [Hitch](https://www.residentadvisor.net/dj/hitch) (76 bookings at <em>Input</em>),
[Raymundo Rodriguez](https://www.residentadvisor.net/dj/raymundorodriguez) (51 bookings at <em>Corsica Studios</em>) 
and [Dexon](https://www.residentadvisor.net/dj/dexon) (46 bookings at <em>Melkweg</em>) 
are the three most booked artists across the all these clubs.
 
But there are also a great number of one-off bookings, artists that were only booked 
once at a club in the year 2019. And these one time appearances bring the averages 
down across the board.  

In light of this we can infer that the appeal of these clubs to RA users is not 
primarly from honing and supporting local residents but by building on a wider, 
transient, globetrotting talent pool.

--- 

Let's now zoom out and look at the "*residency factor*" through the region the 
different clubs are in. In this chart the box represents the range of the 90% of 
the clubs within that region, the lines represent the outliers (5th and 95th 
percentile). The blue vertical line denotes the mean or average for that region. 
Click on a region to see the clubs that belong to it.


<details>
<summary>Show footnotes</summary>

We are still filtering out clubs with only a few dates (less than 10) and the 
ones that booked less than 20 artists. This is why some regions have more clubs 
than others and also why some regions were filtered out entirely (e.g. Los Angeles)

</details>

---

[Manchester](https://www.residentadvisor.net/guide/uk/manchester) and 
[Ibiza](https://www.residentadvisor.net/guide/es/ibiza) have the biggest range 
and the highest average and stand out from the other regions. 

Perhaps because Ibiza is a seasonal tourist destination clubs there rotate their 
bookings less because their audience is in constant rotation? This is pure 
speculation though and we have no theory for why Manchester clubs to book the 
same artists more often than the other regions.

We can also see that [Berlin](https://www.residentadvisor.net/guide/de/berlin) might 
be an outlier. In fact when you run this data through statistical analysis it 
suggests that Ibiza and Berlin are the two regions that do not come from the 
same underlying distribution when it comes to the "*residency factor*".<sup>4</sup>

<details>
<summary>Show footnotes</summary>

4\. P value < 1% using the Kolmogorov-Smirnov statistic for the residency factor 
of the various regions.

</details>