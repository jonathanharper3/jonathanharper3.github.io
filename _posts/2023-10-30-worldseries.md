---
layout: post
title:  "world series pitching analysis"
date:   2023-10-30
description: could we have predicted paul seward's home run pitch?
categories: blog
---

In the bottom of the ninth on October 27, 2023, Paul Sewald had a 0-0 count on Corey Seager, a man on first, a two-run lead, and a 93.6 miles per hour four-seam fastball.  One pitch later, Paul Sewald had a blown save, an energized crowd, and was looking at a Rangers team that would go on to win the first game of the World Series. Corey Seager isn’t a bum – he’s gone for 33 home runs this year, which is tied for the sixteenth most in the majors. He’s also the 2020 World Series MVP. This homer, while huge, shouldn’t have been a surprise at all to anyone watching. But Paul Sewald, who has been an ace for the Diamondbacks this post-season, also didn’t give him any surprises with his first pitch up to the plate.

<iframe width="560" height="315" src="https://www.youtube.com/embed/zxB24tsJxzo?si=9ERCNuu7bPzpyUy5" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Paul Sewald has two pitches in his arsenal. A four seamer and a sweeper. And as far as stats go, these two pitches have served him well. He’s earned 34 saves and 94 strikeouts this season, with six saves and fourteen strikeouts coming this post-season thus far over nine innings pitched. Pretty good numbers. The bottom of the ninth homer by Corey Seager currently represents the only runs Sewald has given up this post-season as well. The Diamondbacks clearly value him quite a bit, as he’s the only post-season pitcher on the roster with a save and one of only two pitchers who have been given save opportunities. I was personally cheering for the Phillies during the NLCS and grew to respect and fear and kind of despise Sewald’s abilities on the mound.

But, for better or worse, he gave up a critical two-run homer to Corey Seager in the World Series, and that’s probably what he’ll be remembered for by many Diamondback fans if the Rangers end up winning it all this year. I’ve been trying to understand pitching over the last month through data compiled by baseballsavant.mlb.com. This includes pitch percentages, pitch sequences, and zone percentages. By looking at Paul Sewald’s data over the 2023 season, we may find some information that can show us how predictable his zone 2, four seamer was on the first pitch of a two-pitch sequence.

As stated earlier, Sewald has two pitches: A four seamer (FF) and a sweeper (ST). He throws his four seamer 57% of the time and his sweeper the other 43%. These percentages are true for all pitches and for first pitches of an at-bat. Maybe this is on purpose or maybe it’s just the law of large numbers (not sure 1,037 pitches would be considered a large enough number, though). Seager only had one at-bat and six pitches against him during the regular season (FF, ST, FF, FF, FF, ST for a walk), so he may not be very familiar with his pitching style as a batter. He likely had done his research though through film, word of mouth, or watching from the dugout, and it’s likely he knew Sewald’s tendencies. Let’s say that Seager had done his research on Sewald and was looking specifically for that high and over the plate four seamer that he smacked into right field. What’s the likelihood he would get it, based on Sewald’s pitches that year?

There’s a pretty good chance Seager would get at least one fastball in his at-bat. Sewald averaged 4.2 pitches per at-bat, and with a 57% four seamer rate, at least 2 of those are likely to be fastballs. For the first pitch, Seager may expect a fastball slightly more than a sweeper, as Sewald has thrown 33 more first-pitch fastballs and 149 more total fastballs this year than sweepers. He shouldn’t feel the need to jump if he gets a shifty sweeper instead of his preferred four seamer. Not yet at least. He has a full count ahead of him and can lay off.

There’s a significantly smaller chance Sewald would throw a ball high and across the middle of the plate. On a first pitch of an at-bat, he’s most likely to throw it either high and outside (zone 11) or low and inside (zone 14), both at a 16.7% rate. If this is the case, Seager could lay off and see how the ump is calling it. High and over the middle (zone 2) is tied for the fifth most likely strike to be thrown at a 4.9% rate, which is pretty unlikely. It’s a little (only a little) more likely that Sewald would throw into zone 2 when you consider all of his pitches this season. For strikes, zone 2 ranks third most likely at a 6.5% rate. Again, Sewald tends to operate mostly on the outside of the batter’s box, with zone 11 showing up 17.3% of the time and zone 14 showing up 17.1% of the time. If Seager has a good awareness of the batter’s box and the ump is calling balls and strikes fairly, then this shouldn’t be a problem.

Side note: this isn’t always the case. Sewald throws balls into zones 11, 12, 13, and 14 46.5% of the time. These should be called balls, but 25% of Sewald’s throws outside of the batter’s box are either balls called strikes, swinging strikes, or foul balls while only 6.8% are hit into play. Of those balls hit into play, 75.8% are routine field outs. This is compared to the 20.0% that are hit into play from the strike zone, only 56.8% of which are field outs. Sewald’s main purpose as a closer is to not give up runs. Runs come from big hits. If he can lower the chance of big hits, he’s going to do so, and we see a significant number of pitches thrown outside the strike zone as a result.

It's fun to look at the stats, and it gives us better insight into how different players may approach an at-bat. Predicting what pitch Corey Seager is going to see for his first at-bat against Paul Sewald in game one of the 2023 World Series is useless, though. We already know that Sewald hung a four seamer high and down the middle of the plate. We know that Seager connected with this pitch and sent it sailing into the right field bleachers. And we know that this gave the Rangers the momentum they needed to win the game. Trying to predict which pitch Corey Seager will see from Paul Sewald later on in this World Series may be more useful. I’m not at a point where I’m ready to do this type of work yet, but looking at how pitchers operate has been fairly interesting for me, and I plan to continue it into the upcoming months to see if useful, actionable information can result from this work!

Failed attempt:

I really wanted to use unsupervised learning this month to cluster similar pitchers together and see if the data in these clusters could reasonably predict what type of pitch would most likely come next. I used k-means clustering to group these pitchers together, with a higher number of variables informing the clusters. These variables included percentage thrown in each zone, percentage of each pitch, number of pitches, and the release speed mean. Variables could look like this:

Zone 1: .0034<br>
Zone 2: .0067<br>
Zone 3: .0042<br>
…<br>
Zone 14: .0149<br>
FF: .3221<br>
SL: .1275<br>
CH: .1824<br>
…<br>
PO: 0<br>
CU: 0<br>
ST: 0<br>
…<br>
number_of_pitches: 4

I used a silhouette score to grade each cluster and determine which cluster would be best to use and saw that the highest silhouette score came when there were 2 clusters. This score hovered around .50. I ultimately used 5 clusters, which had a silhouette score of .45, but when observing the data visually, it was impossible to really tell what was defining each cluster. I think this is likely due to the higher variable count paired with the lower value add for each variable. I envisioned someone like Paul Sewald being clustered with other two- to three-pitch closers that operated around the edges. However, I got a blob of pitchers that had little similarities when all was said and done.

All is not lost, however! I’ve seen a few articles of people clustering pitchers using different methods, and this has given me some new ideas. I’ll try to rethink my approach and see if I can add anything meaningful to the topic in future iterations.
