| [home page](https://itsmeriem.github.io/Meriem/) | [Ranking of News Orgs](news-ranking.md) | [visualizing debt](visualizing-debt.md) | [critique by design](critique-by-design.md) | [final project](final-project.md)


# Title
More info to come

# Step 1 and 2:

For this assignment, I chose to focus on this [visualization published by Business Insider]((https://www.businessinsider.com/federal-minimum-wage-workers-map-2018-10?r=US&IR=T)) showing "Workers Making Minimum Wage or Less". The associated MakeoverMonday Data can be found [here](https://data.world/makeovermonday/2023w18). For convenience, I am also attaching a screenshot of the visualization.

<img src="min_wage_viz.png" width="400"/>



# Step 3: Sketch out a Solution

Pulling from my critique above, I set out to resolve a ![image](https://github.com/ItsMeriem/Meriem/assets/149505081/8620323d-43c5-4fc7-9526-ce7fd9b2d365)
few issues in the original visualization. My goal was to: 

- Move away from state-to-state comparisons and focus on the story at a national-level.
- Focus both on "how many" people make at or below minimum wage but also "who" makes at or below min wage.
- Visualize percentages in a way that may be easier to understand. I find this specifically helpful when talking about percentages of percentages: like 67% of 1% is hard to grasp so I was hoping to find ways to make that easier to work with.

### Vizualization 1: 3-Panels "Unit" Chart

My first sketch aims to visualize percentages as dots and focuses on "who" makes below minimum wage. I envision these as three interactive panels. In panel 1, users could click on the one dot representing people making at or below $7.25, and that would trigger an effect where we zoom-in on the dot and then the one dot gets "divided" into 100 dots, leading us to the next panel. Find sketches below: 

[include image]

### Vizualization 2: Bar Chart

[include image]

### Vizualization 3: Line graph

[include image]

# Step 4a: Test the Solution

To test my sketches, I interviewed two people. I used the same set of questions for both interviewees and the same questions for all three visualizations. To protect anonymity, I paraphrased their answers.

### User 1: Young Progressional, mid 20s, college educated

#### Vizualization 1: 3-Panels "Unit" Chart

Meriem: Can you tell me what you think this is?

User 1: I think each panel is zooming-in at each level of who makes at or below minimum wage. You zoom in on the first dot and it divides it by people at vs people below minimum wage; and then dividing further by gender vs age. 

Meriem: Can you describe to me the story this is telling you?

User 1: A lot of people are making under minimum wage and most of them are women. And a good number of those are young.

Meriem: Is there anything you find surprising or confusing?

User 1: I find it suprising that so many people make under minimum wage.
What I find confusing is that the third panel has 2 variables. Having two variables (both age and gender) makes it confusing. The legend if also confusing: using both color and shade to represent age and gender is confusing.
Additionally, the title in third panel has nothing to do with age. In the third panel, it seems like half of them are younger and half of them are older. So what’s the point? What are you trying to say here? 

Meriem: Who do you think is the intended audience for this?

User 1: People who are interested in graphs about who makes less than minim wage. I don’t think the audience is people making less than minimum wage. Audience is to educate broadly

Meriem: Is there anything you would change or do differently?

User 1: If you want to make a point about age, you need to make it separately: on a separte panel.
For the first panel, you need to make me care. What does 1 out of a 100 mean? Can you compare it to something else? Like “that’s the number of people in Pittsburgh” 

Meriem: What do you think of the text (titles, legend etc..)? 

User 1: Good. But you need to stick to the story. There's nothing about age in the third title



#### Vizualization 2: Bar Charts

Meriem: Can you tell me what you think this is?

User 1: This is showing the number of women making less then or at minimum wage vs men, and it's showing age as well.

Meriem: Can you describe to me the story this is telling you?

User 1: Women make less money than men. I'm not sure about age. There’s more older than young women who are making less than 7.25.

Meriem: Is there anything you find surprising or confusing?

User 1: Confusing: Axes are not labelled. Age is not mentioned in the title. Mentioning age in the title will help the readers draw the conclusion. 

Meriem: Is there anything you would change or do differently?

User 1: I would change the title to say: “Of hourly workers making $7.25 or less, Women make up m….”



#### Vizualization 3: Line graph

Meriem: Can you tell me what you think this is?

User 1: This is showing how the number of hourly workers making at or less than 7.25 has decreased over time.

Meriem: Can you describe to me what this is telling you?

User 1: Number of hourly workers has decreased over time

Meriem: Is there anything you find surprising or confusing?

User 1: Very clear. Glad to see it has decreased

Meriem: Who do you think is the intended audience for this?

User 1: Anyone. Much easier to understand.

Meriem: Is there anything you would change or do differently? 

User 1: If you wanted to make it more interesting, you can add lines for gender and age. A line for women , a line for men etc… To show that trends are different for different subgroups

### User 2: Graduate Student, mid 20s

#### Vizualization 1: 3-Panels "Unit" Chart
#### Vizualization 2: Bar Charts
#### Vizualization 3: Line graph

# Step 4b: Reflection

Pulling from the two interviews recorded above and the in-class critique exercise, the following similarities came up:

- Users found the combination of color and shading (to represent gender and age) confusing and hard to understand.
- Stacked charts made it hard to compare different chunks.
- In Viz 1 and Viz 2, I did not include age in the titles but included it in the graph and legend. This was confusing to users.
- The titles could be phrased more clearly
- Generally, users liked Viz 1 but thought that its interactive aspect did not easily come through through hand-written sketches. I agree with this statement and I think this was one of the limitations of hand sketching an interactive design: I could not properly communicate my vision via the sketches and I had to explain it to the users.

Differences included:
- One of the users liked the simplicity and clarity of the line chart, but classmates (during the in-class critique) found the percentages to be hard to interpret with.

Upon reflecting on these comments, I decided to go forward with Visualization number 1. I think this visualization sets out to resolve a few issues discussed in my critique:
- Moving away from state-to-state comparisons and focusing on the picture at a national-level.
- Focuses both on "how many" people make at or below minimum wage but also "who" makes that.
-  Visualizes percentages in a way that may be easier to understand. I find this specifically helpful when talking about percentages of percentages: Like 67% of 1% is hard to grasp so I was hoping that the unit chart would help me visualize this.

And using the comments above, I made the following changes to my sketches:
- In all three panels, I added a legend that specifies the "size" of the dot (i.e 1 dot = 1 million people). As per the users' feedback, this would help visualize the extent of the population concerned.
- In Panel 1, I changed the title from "For every 100 hourly workers, 1 person makes $7.25 or less" to "For every 100 people getting paid hourly, 1 person makes $7.25 or less". The phrasing "hourly wokers" (used by the Bureau of Labor Statistics) was confusing to users.
- In Panel 3, I changed the legend to rely on color only. Instead of using shading to represent age, I used a difference in opacity of the same hue. I used light blue for older women, dark blue for younger women, light green for older men, and dark green for younger men.
- In Panel 3, I added a sub-title: "Contrary to popular belief that the lowest earners are teenagers, most are aged 25 or older". I used this to frame the reasons behind my addition of the age variable and to help users understand why considering age matters when we discuss minimum wage.


# Step 5: Built My Solution

In building the solution, the biggest challenge was learning how to make interactive designs in Tableau. My vision, as described above, is that each dot takes the users to a new panel (in a sense, each dot gets divided into a new panel of 100 dots). My vision included a "zooming-in" effect. This was very hard, almost impossible to do in Tableau. This is one of the limitations of Tableau. For future designs, I would consider using Figma or a similar design software to implement an interactive design - I think that would be easier (and nicer looking!)

The best workaround I found is to use the "navigation" buttons in Tableau to navigate between panels.
- To navigate from Panel 1 to Panel 2: click on the orange dot
- To navigate from Panel 2 to Panel 3: click on any red dot
- To navigate back to a previous panel: click the "back" button.

This is the best solution I found given the time and software constraints.

The navigation instructions should be pretty straightforward on the visualization itself. Please make sure you see all three panels.




<div class='tableauPlaceholder' id='viz1700024332299' style='position: relative'><noscript><a href='#'><img alt='Panel 1 ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Mi&#47;MinWagePanelDesign&#47;Panel1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='MinWagePanelDesign&#47;Panel1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Mi&#47;MinWagePanelDesign&#47;Panel1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /><param name='filter' value='publish=yes' /></object></div>               
<script type='text/javascript'>                   
  var divElement = document.getElementById('viz1700024332299');                    
  var vizElement = divElement.getElementsByTagName('object')[0];                    
  if ( divElement.offsetWidth > 800 ) { vizElement.style.width='1214px';vizElement.style.height='835px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.width='1214px';vizElement.style.height='835px';} else { vizElement.style.width='100%';vizElement.style.height='727px';}                  
  var scriptElement = document.createElement('script');                    
  scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                   
  vizElement.parentNode.insertBefore(scriptElement, vizElement);               
</script>
