## Towards datascience

Intuition to  ADAM and RMSprop optimizers.

<p>Few ideas before getting started.</p>

<h3>Exponentially weighted averages:<h3>

Lets take an example where temperature changes are captured over period of time, </p>


Θ1 = 2˚C  - Temperature at day1 </br>
Θ2 = 3˚C  - Temperature at day2 </br>
Θ3 = 5˚C  - Temperature at day3 </br>
...etc 
 
 Weighted averages, 
 V0  = 0 (Lets take initial value as 0)
 V1  =  0.9  V0   + 0.1 Θ1 
 V2  =  0.9  V1   + 0.1 Θ2
 V3  =  0.9  V2   + 0.1 Θ3
 .. etc

Here β = 0.9
Finally it's simple ,
   V(base)t = β V(base)t-1 + (1-β) Θ(base)t

t = current day.
V(base)t = weighted average at 't' day.
V(base)t-1 = weighted average at 't-1' day.
Θ(base)t = temperature at current day. 

In weighted averages we take history data into consideration along with current data , to get smoother curve.From above example we are taking previous weighted average with present temperature.

Because of this this distribution is resisted towards the outliers and sudden changes in the data.

Now, you might have a question that when  β= 0.9 how days number of days is been considered,

 days = 1/(1-β) = 1/(1-0.9) = 10 
 
 so if β = 0.9  approximately 10 days are taken.
       β = 0.98 approximately 50 days
       β = 0.5  approximately 2days

	   
Why we need weighted averages ?

 To have robust distribution that resists the sudden fluctuation in the data or outliers. Other that data science this is used in the share market graph to understand the ground truth of the market.
 





 







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
