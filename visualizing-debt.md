| [home page](https://itsmeriem.github.io/Meriem/) | [Ranking of News Orgs](news-ranking.md) | [visualizing debt](visualizing-debt.md) | [critique by design](critique-by-design.md) | [final project part 1](final-project-part1.md) | [final project part 2](final-project-part2.md) | [final project part 3](final-project-part3.md)  

# Visualizing Debt

## Part 1: Working with web-based visualization tools and data

### Bar Graph Imported from OECD Website

<iframe src="https://data.oecd.org/chart/7f2D" width="860" height="645" style="border: 0" mozallowfullscreen="true" webkitallowfullscreen="true" allowfullscreen="true"><a href="https://data.oecd.org/chart/7f2D" target="_blank">OECD Chart: General government debt, Total, % of GDP, Annual, 2021</a></iframe>

## Part 2: Working with Tableau

<div class='tableauPlaceholder' id='viz1699299725704' style='position: relative'><noscript><a href='#'><img alt='For the Top Borrowers, Government Debt-to-GDP ratio has gotten worse over time.Source: OECD Data ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;de&#47;debt-to-gdp-ration&#47;Sheet1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='debt-to-gdp-ration&#47;Sheet1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;de&#47;debt-to-gdp-ration&#47;Sheet1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /><param name='filter' value='publish=yes' /></object></div>               
<script type='text/javascript'>                    
  var divElement = document.getElementById('viz1699299725704');                    
  var vizElement = divElement.getElementsByTagName('object')[0];                    
  vizElement.style.width='100%';vizElement.style.height=(divElement.offsetWidth*0.75)+'px';                    
  var scriptElement = document.createElement('script');                    
  scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                   
  vizElement.parentNode.insertBefore(scriptElement, vizElement);               
</script>


## Part 3: Create my own visualization

<div class='tableauPlaceholder' id='viz1699414532341' style='position: relative'><noscript><a href='#'><img alt='Japan in a Tough Spot:Japan has the highest government debt of any developed nation ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Bo&#47;Book1_16994144817240&#47;Sheet1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='Book1_16994144817240&#47;Sheet1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Bo&#47;Book1_16994144817240&#47;Sheet1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /><param name='filter' value='publish=yes' /></object></div>                
<script type='text/javascript'>                    
  var divElement = document.getElementById('viz1699414532341');                   
  var vizElement = divElement.getElementsByTagName('object')[0];                    
  vizElement.style.width='100%';vizElement.style.height=(divElement.offsetWidth*0.75)+'px';                    
  var scriptElement = document.createElement('script');                    
  scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    
  vizElement.parentNode.insertBefore(scriptElement, vizElement);                
</script>

## Written Summary
The bar graph (imported from the OECD website) is successful at showing the ranking of debt-to-GDP ratio among OECD countries. At first glance, it's clear that Japan ranks the highest. However, the chart does not use colors in a smart way - its use of light blue and grey fade together. It is so simple that it becomes boring. As a busy viewer, I'd scroll past this chart. It does not grab my attention. 
The heat map made in Part 2 of this assignment focuses on the progression over time of government debt. This adds an additional dimension, as compared to the bar graph. Because of the ranking from highest to lowest and the use of color in a blue-to-orange gradient, two takeways easily pop up: Japan ranks the highest, and on average borrowing has gotten worse over time for the top borrowers. While the message is clear, it takes a couple of minutes to get there. By providing all the data points, the heatmap becomes overwhelming. Viewers need to scroll both vertically and horizontally to get the entire picture, which might risk losing their attention.
Finally, I decided to use a packed bubble chart as the third visualization. Unlike the heatmap, I wanted to highlight the current state of government debt. To do so, I limited the data to 2022 only. While not losing the simpliciy of the bar chart, I also wanted to fix one of its issues: I wanted to make a visualization that was eye-grabbing. The packed bubble chart provided me with this opportunity. I sorted the bubbles in descending order so that the highest ratios are concentrated in the middle of the cloud, and the lowest ones in the outer parts of the chart. Drawing from the heatmap, I used a similar color gradient since I believe that the blue-to-orange gradient is quite effective. To decrease eye-travel, I included the value of the debt-to-gdp ratio in the bubbles themselves. This is better than the bar chart where the viewer has to travel back and forth between the bar and the y-axis. I believe that the third visualization achieves the goal of being simple, clear and attention-grabbing.

[Data Source](https://data.oecd.org/gga/general-government-debt.htm)



