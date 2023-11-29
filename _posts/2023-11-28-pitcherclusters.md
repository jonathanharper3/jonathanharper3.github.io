---
layout: post
title:  "pitching clusters"
date:   2023-11-28
description: can we try some sabermetrics?
categories: blog
---
Some of the most exciting baseball happens almost exclusively at the pitcher’s mound. I was reminded of this during the matchup between LSU and Wake Forest during the College World Series. Rhett Lowder and Paul Skenes both pitched master classes in a game that didn’t see a run until the eleventh inning, and I was on the edge of my couch cushion for most of the game. These performances are still fresh in my mind five months later and have had me thinking of how influential the pitcher is on the outcome of a game. You need nine strong innings to win a game, but one poorly pitched at-bat in a close game can shift the momentum enough to send a team spiraling. The fact that pitching is essentially an entirely different sport compared to the one that everybody else on the field is playing makes it all the more compelling. And so I decided to look a little further into it with 2023 MLB pitch data.

There were 479 pitchers in the MLB with 500 or more pitchers during the 2023 regular season. These pitchers threw 645,731 pitches to 654 different batters for 38,074 strike outs and 5,205 homers. Any pitcher will have their strengths and will try to lean on them, but a good pitcher will also know their batter’s weaknesses and will try to capitalize on them. Likewise, a batter should know what type of pitcher they’re facing and what they can expect in each at bat.

This can be an impossible task, though. A batter and pitcher may face each other once or twice in a season. New players are promoted into the majors every week and the new film becomes endless at some point. Players can spend their time exclusively watching film, but it may be possible to group players together and cut down the study time required to excel in the league. With this on my mind, I used a k-means clustering method to try and group pitchers together and see if these otherworldly talents share any similarities with each other.

I used eleven advanced metrics to group pitchers together. They are as follows:

Strikeouts / 9<br>
Hits / 9<br>
Walks / 9<br>
Home Runs / 9<br>
Ground Ball to Fly Ball Ratio<br>
Hard Contact Percentage<br>
Fastball Runs<br>
Offspeed Runs<br>
Swings Outside of the Strike Zone<br>
Swings Inside of the Strike Zone<br>
Swinging Strikes

I opted to use these stats in place of other statistics like pitch frequency and pitch sequences to hopefully avoid homogenous data. This type of data may be helpful when trying to predict what pitch comes next, but is more difficult to use when aiming to characterize a pitcher. These advanced metrics meant to separate types of pitchers from one another instead.

I used a silhouette score to try and find the optimal cluster amount and ultimately landed on seven. None of the silhouette scores were particularly high, with the seven cluster score landing at .172, and this seems to be attributed to the amount of metrics used when trying to cluster. This may be something to look at moving forward, as more data may result in better defined clusters, but these are some of the things that stuck out to me with the clusters that were built.

![k9](/images/baseball_k9.png)
![h9](/images/baseball_h9.png)
![bb9](/images/baseball_bb9.png)
![hr9](/images/baseball_hr9.png)
![gb2fb](/images/baseball_gb2fb.png)
![hc_perc](/images/baseball_hc_perc.png)
![fbc](/images/baseball_fbc.png)
![osc](/images/baseball_osc.png)
![o_swing](/images/baseball_o_swing.png)
![z_contact](/images/baseball_z_contact.png)
![ss_perc](/images/baseball_ss_perc.png)

The per 9 stats were included to identify good and bad pitchers. Those with high strikeouts and low walks, hits, and home runs would presumably be grouped together. Cluster seven looks to match this hypothesis as a cluster that is a tier above. This is backed up by the inclusion of Gerrit Cole, who is arguably the best active pitcher and just recently won the Cy Young award. Many other top pitchers are also included in this list, and a successful day against any of them will be rare. Meanwhile, a batter may see more success against a cluster five pitcher, where they’ll be more likely to find their pitch and get on base.

Cluster six also houses some interesting characteristics. In most clusters and across the dataset as a whole, a four seam fastball is twice as likely to be thrown as the next most frequent pitch, a slider. This shows that, as a batter, you are most likely to see a four seamer when up to bat, regardless of who you’re facing. However, a pitcher from cluster six is most likely to throw a sinker. A sinker is a fastball-type pitch but it dips as it approaches the batter. We may see batters chase these types of pitches when they generally end up outside the strike zone. However, cluster six has the highest walks per nine value and the lowest number of batters swinging at pitches outside of the strike zone. If a batter can sit on cluster six pitches or wait for a lower skill pitch, they’ll be more likely to end up on base.

This is nowhere near a comprehensive analysis but is a great starting point for those trying to learn more about pitching as a whole.
