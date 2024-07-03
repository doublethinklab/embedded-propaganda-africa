# Embedded Propaganda in African Media

## Overview

In collaboration with China Digital Times, we looked at the concept of "embedded propaganda" (EP) in African news media.
EP is the practice of republishing PRC state media under a local masthead.
We define three different types of EP:
1. **Attributed**: where PRC state media are credited as the source of the story.
2. **Un-Attributed**: where PRC state media are not credited, and no credit is given.
3. **Re-Attributed**: where PRC state media are not credited, and credit is re-assigned to another party, such as the local newspaper.
These can be seen as gradations in the manipulative nature of the practice of embedded propaganda, with (3) the most severe.

We collected data from news websites in a number of African countries, and developed a computational methodology to identify these three types of EP with high precision.
The findings here represent the output of a pilot study to prove this methodology.
Stay tuned for a deeper report from China Digital Times, that digs deeper into the findings, and points an interesting way forward for evidence-based monitoring and analysis of EP.

## Methodology

We collected large numbers of articles from PRC state media, and local African media, during the period 2022-01-01 to 2022-12-31 (a full year).
The articles were all in English.
We used semantic similarity technology to identify candidate matches between a candidate (African media) article and a source (PRC state media) article.
Encoding was performed using the pretrained sentence transformer, [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2).
We encoded each paragraph of each article.
Comparing the paragraphs of each article with cosine similarity, we used a threshold of 0.9.
We considered two articles a match if at least half of their paragraphs were a semantic match.

We validated our methodology on a subset of findings, and fine-tuned the methodology until human validated precision was 100%.

## Findings

This pilot study looks at the following websites from Ghana, Kenya, and Uganda.

Uganda
- observer.ug 
- redpepper.co.ug
- busiweek.com
- monitor.co.ug
- dailyexpress.co.ug
- independent.co.ug
- newvision.co.ug

Kenya
- thecoast.co.ke
- businessdailyafrica.com
- live.k24tv.co.ke
- games.standardmedia.co.ke
- k24tv.co.ke
- businesstoday.co.ke
- tuko.co.ke
- kenya-today.com
- theeastafrican.co.ke
- standardmedia.co.ke
- kenyanews.go.ke
- nairobiwire.com
- kenyans.co.ke
- kbc.co.ke
- the-star.co.ke
- capitalfm.co.ke
- kenyan-post.com

Ghana
- dailystatesman.com.gh
- adomonline.co
- adomonline.com
- theheraldghana.com
- peacefmonline.com
- myjoyonline.com
- citinewsroom.com
- myinfo.com.gh
- thebftonline.com
- dailyguidenetwork.com
- graphic.com.gh
- ghanaweb.com
- publicagendagh.com
- newsghana.com.gh
- ghanaiantimes.com.gh
- mynewsghana.net
- thechronicle.com.gh
- modernghana.com
- pulse.com.gh
- 3news.com
- browngh.com
- yen.com.gh

The analysis below pertains to all outlets for which we identified at least one instance of embedded propaganda.

The total number of EP from each site is as follows:

![Percentage of Embedded Propaganda](https://github.com/doublethinklab/embedded-propaganda-africa/blob/main/Figures/count_ep.png?raw=true)

The percentage of EP (i.e., total number of EP divided by number of articles we collected) from each site is as follows:

![Percentage of Embedded Propaganda](https://github.com/doublethinklab/embedded-propaganda-africa/blob/main/Figures/percent_ep.png?raw=true)

For the top-3 sites, the volume over the period of 2022 is as follows:

![Percentage of Embedded Propaganda Types](https://github.com/doublethinklab/embedded-propaganda-africa/blob/main/Figures/top3_over_time.png?raw=true)

We break down the EP types per site as follows:

![Percentage of Embedded Propaganda Types](https://github.com/doublethinklab/embedded-propaganda-africa/blob/main/Figures/ep_types.png?raw=true)

## Data

The results for each country can be found in the `Data` folder.

The statistics that were used to produce the plots above can be found in 
the file `Data/Embedded Propaganda Statistics.csv`.
