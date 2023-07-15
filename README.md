## Analyzing the Rise of Modern Slang Words in Pop Music

### Overview
For this project, I set out to explore the rise of modern slang words. By analyzing the occurrence of these words in top music charts from 2010 to 2022, I aimed to understand their emergence and trends in popular culture. The analysis revealed that each of the selected slang words (lit, drip, dope, woke, bae, and flex) became more prevalent in songs over the 12-year period.

I got to work on datframes that I created myself with top song charts and lyrics data that I scraped from the [Music Charts Archive](https://musicchartsarchive.com/). 

### Data Collection
All of the data was scraped from the Music Charts Archive website, which publishes the weekly top 50 charts over the years. I had to scrape in steps, saving the htmls for each year, week and song webpage to a separate directory to avoid putting too much strain on the websites server. The html files are in directories named year-htmls, weekly-htmls, and song-htmls, respectively. It was from the song html pages that I was able to scrape the lyrics that I used for my analysis. Unfortunately not all of the songs had their own webpage, and thus lyrics to include in my analysis, but most did.

I was looking at 2010 - 2022, which includes over 600 weeks of top 50 charts (35,350 entries). Since the charts are weekly, there were a ton of repeated songs, as many of the songs stay on the charts for more that one week. For the sake of this analysis, I decided to group the data by year, counting each song only once per year, regardless of how many times it appeared on the charts that year. I found that there were 3,262 unique songs in my dataframe, calculated how often each song appeared on the weekly charts, and grouped those results by number of appearances. The results of this analysis are saved as `grouped_counts.csv` in the directory titled `csvs`.

I selected a number of popular slang words (lit, drip, dope, woke, bae, and flex) and counted how often each one appeared in the scraped song lyrics. In addition to counting the number of times each slang word appears, I made a separate dataframe that simply counts how many songs from the charts mention each word at all. I think this equalized the playing field when comparing the prevalence of  each word, since some songs could mention the same word 9 times (take  Pharrell Wiliams' “Come Get It Bae”). The export of this analysis can be found in `slang_by_year.csv` and `all_slang_count.csv`. I only exported and visualized the lyrical count for the word ‘bae’ (`bae-lyrical-mentions.csv`), but the rest can be found in my jupyter notebook (`music-chart-project.ipynb`). 


### Lessons Learned
This was a major exercise in scraping for me, but I was lucky that the format of the html was pretty standard across all webpages. I faced a few hiccups along the way, like the song webpages using the same div class for most elements on the page. I got around that by pulling the text of all of those elements, and only taking the longest one from each page (Thanks,  Soma!). 

I also spent a lot of time thinking about how I should analyze the data since it was split up by week and many of the songs repeated. Had I been more advanced, I think I could have gotten more creative about how I measured a word’s lyrical count over time, while also attributing the percentage of those mentions to each given song. I had the idea in my head but I wasn’t quite able to figure out how to implement it. This project convinced me that it’s worth spending more time mastering the visualization process because it’s invaluable in helping you share exactly what it is you’re trying to say.   
 
