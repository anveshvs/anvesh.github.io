

<h2>Intuition to  ADAM and RMSprop optimizers.</h2>

<p>Few concepts that are required , before getting started.</p>

<h4><u>Exponentially weighted averages:</u></h4>

<p>Lets take an example where temperature changes are captured over period of time, </p>


<div>Θ1 = 2˚C  - Temperature at day1</div> 
<div>Θ2 = 3˚C  - Temperature at day2</div> 
<div>Θ3 = 5˚C  - Temperature at day3 </div>
<div style="margin-bottom:20px;">...etc </div>
 

 <div>Weighted averages, </div>
 <div>V0  = 0 (Lets take initial value as 0)</div>
 <div>V1  =  0.9  V0   + 0.1 Θ1</div> 
 <div>V2  =  0.9  V1   + 0.1 Θ2 </div>
 <div>V3  =  0.9  V2   + 0.1 Θ3 </div>
  <div  style="margin-bottom:20px;">.. etc  </div>
 
 
<div> Here β = 0.9 </div>
<div style="margin-bottom:10px;"> Finally it's simple , </div>

<div style="margin-bottom:20px;font-size: 20px;margin-left:5em">
		  <b>  V<sub>t</sub> = β V<sub>t-1</sub> + (1-β) Θ<sub>t</sub></b></div>
<div>t = current day.</div>

<div>V<sub>t</sub> = weighted average at 't' day.</div>
<div>V<sub>t-1</sub> = weighted average at 't-1' day.</div>
<div  style="margin-top:20px;">Θ<sub>t</sub> = temperature at current day.</div>

<div style="margin-bottom:20px;">	
In weighted averages we take history data into consideration along with current data , to get smoother curve.From above example we are taking previous weighted average with present temperature.
</div>
<div style="margin-bottom:10px;">Because of this this distribution is resisted towards the outliers and sudden changes in the data.</div>

<div style="margin-bottom:10px;">Now, you might have a question that when  β= 0.9 how days number of days is been considered,</div>


<div style="margin-bottom:10px;"> days = 1/(1-β) = 1/(1-0.9) = 10 </div>

<div> so if β = 0.9  approximately 10 days are taken.</div>
    <div>   β = 0.98 approximately 50 days</div>
    <div style="margin-bottom:20px;">   β = 0.5  approximately 2days</div>
	  
<div style="margin-bottom:10px;color:red;">Why we need weighted averages ?</div>


<div style="margin-bottom:20px;"> To have robust distribution that resists the sudden fluctuation in the data or outliers. Other that data science this is used in the share market graph to understand the ground truth of the market.</div>

 



___________________________________________________________________________________

 







You can use the [editor on GitHub](https://github.com/towardsdatascience/towardsdatascience.github.io/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

<h1>V1 =  0.9  V0   + 0.1 Θ1 </h1>

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/towardsdatascience/towardsdatascience.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
