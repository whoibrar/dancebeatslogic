## The Twitch Tale

I did something unusual and ~slightly~ out of my comfort zone. I streamed on twitch for the first time, 3h 47mins in total. 

I don’t usually watch Twitch, except for occasionally browsing over the [Software and Game development category](https://www.twitch.tv/directory/game/Software%20and%20Game%20Development) when I’m procrastinating. One day I might find myself watching a solo-dev from Germany fixing some obscure Unity C++ bug in the indie game they’ve been working from their home studio for two years. Another day, I might find a high school student from Thailand learning CSS-flexbox on their 14th day of #100daysOfCode. I don’t always understand 100% of the problem they are trying to solve or the thing they’re learning, yet each time they fix a bug or complete a level, I feel the same equal joy and excitement as the streamer. They streamers are generally very proactive in answer questions and engaging with chat too. I enjoy watching these streams, and I find it interesting to see how different people think, work and learn in real time.

Each time after watching such a stream, I would leave thinking *“Maybe some day I should do it too”*. But I don’t have a good camera, or those fancy neon lights. Heck, I don’t even have a proper microphone. *“Nah, I’ll probably do it after I get all those”*, I’d tell myself. And that was how it was. 

Today, out of nowhere, a sudden realization hit me: whenever I’m watching a stream, I never actually cared about any of those fancy setups or neon lights. Sure, they do add to the overall ~aesthetics~ they don’t matter. I watch because of the person and the thing they were working on. I know, It sounds obvious and duhhh, but it took me a while to figure that out. So, there It was in my face: either do it now or I’ll probably keep finding excuses.

Streaming was a surreal experience, I was magnitudes more productive than past two days combined. My goal for the day was just to finish one submodule, but I ended up finishing all four and moving to the next course, [Python Data Science Toolbox 1](https://www.datacamp.com/courses/python-data-science-toolbox-part-1). I have been using OBS for quite a while now to record my self programming, so it was rather simple connecting OBS with Twitch and just had to click one button to start streaming.

Really glad, I pushed myself to click on the stream button, fortunately or unfortunately the stream has been auto delete by twitch, and I forgo to record myself. 

<details><summary>Twitch Stats</summary>
- 0.0 Average Viewers  <br>
- 4 Follows  <br>
- 3h47m Time Streamed  <br>
- 1.0 Unique Viewers  <br>
- 1 Unique Chatters  
</details>
---

## Mathplotlib

It a plotting library

- To use Matplotlib in Python, we use the following code to import the library: **`import matplotlib.pyplot as plt`**.
- **`plt.clf()`** is used to clear the previous plot.
- Matplotlib provides various types of plots that can be created using its functions.
    - **`plot()`** is used to create a line plot.
    - **`scatter()`** is used to create a scatter plot.
    - **`hist()`** is used to create a histogram.
- Scaling options can be used in Matplotlib.
    - **`xscale('log')`** makes the plot logarithmic.

### Plot

- Set the plot with `plt.plot(X,Y)`
    - X, Y values to be plotted on respective axes

### Scatter

- adding `alpha` will set the opacity (1 max).

### Histograms

Histograms are classic bar charts. Each one is split into little buckets called as bins. Too few bins will oversimplify reality and won't show you the details. Too many bins will overcomplicate reality and won't show the bigger picture.

- **`plt.hist(vals, bins=3)`** can be used to create a histogram with 3 bins.

```python
vals = [1,8,2,8,9,5]
plt.hist(vals, bins=3)
plt.show()
```

### Labeling

- **`plt.xlabel("This will show up for x axis")`** is used to set the label for the x-axis.
- **`plt.ylabel("This will show up for y axis")`** is used to set the label for the y-axis.
- **`plt.title("What this plot is about")`** is used to set the title for the plot.
- **`plt.text(X_val,Y_val,"Text to show")`** adds text inside the chart.
- `plt.yticks([0,2,4,6,8,10],['0','2B','4B','6B','8B','10B'])` is used to set the y-ticks.
    - Second argument specifies the labels for each one
- `plt.grid(True)` adds grid to the plot.

## Dictionary

- Key must be an immutable object
- Differences between lists and dictionaries
  - Dictionaries are indexed by unique keys while lists by numbers
  - Lists are collection of values, the other is lookup table with unique keys
    

## Pandas

It is a library for data manipulation and analysis, build on top of Numpy.

- To use Pandas in Python, we use the following code to import the library: **`import pandas as pd`**.
- An existing dictionary can be turned into a Pandas DataFrame by using **`pd.DataFrame()`**.
- **`.index(rowLabels)`** can be used to set the row labels.
- **`pd.read_csv('fileName')`** can be used to convert a CSV file to a Pandas DataFrame.
- The first column can be set as the row label by specifying the **`index_col`** argument inside **`pd.read_csv()`**.
- accessing columns
    - `brics["country"]` → 1D labelled array
        - type → `pandas.core.series.Series`
    - `brics[["country"]]` → Data Frame
        - type → `pandas.core.frame.DataFrame`
- accessing rows
    - `loc` → label based & `iloc` → integer position
        - The single bracket version gives a Pandas Series, the double bracket version gives a Pandas DataFrame.
        - `brics.loc["RU"]` gives pandas series for row
        - `brics.loc[["RU"]]` gives padas dataFrame for row
        - `brics.loc[["RU","IN","CH"],["country","capital"]]`
            - shows the intersection of these
        - `brics.loc[:,["country","capital"]]` also works the same by selecting all rows
- Recap
  - Square Brackets 
    - Column access `brics[["country","capital"]]`
    - Row access : only through slicing `brics[1:4]`
  - loc (label based)
    - Row access `brics.loc[["RU","IN","CH"]]`
    - Column access `brics.loc[:,["country","capital"]]`
    - Row and Column access : `brics.loc[["RU","IN","CH"],["country","capital"]]`

---

- Filtering pandas dataframe
    - 3 Steps
        1. Select column
        2. Make the comparision
        3. Use above result to filter out and select required
    - Using prev example `brics[brics["area"]>8]`
        - `brics["area"]` will get the areas column
        - `column-values>8` makes the comparison and gives boolean array
        - `brics[boolean-array]` gives the final required result

---

- Numpy’s logical operators also works directly on pandas.
- To filter data in pandas using logical operators, we can use the code like this : `brics[np.logical_and(brics["area"] > 8, brics["area"]<10)]`
- Iterating over np arrays can be done using  `for val in np.nditer(my_array):`
- Iterating over a pandas dataframe using a simple for loop will run the iterations on the columns. To iterate over the rows, we need to use **`for label, row in brics.iterrows()`**.
- Generate a new column by using existing columns `apply()`
    - `brics["name_len"]=brics["country"].apply(len)`
        - New column with `name_len` will be added to the dataFrame
    - `cars["COUNTRY]=cars['country'].apply(str.upper)`
        - New column with uppercased name is added

---

## Questions

- Why call it ticks ?
- `plt.scatter(gdp_cap, life_exp, s = pop)` explain the third argument
- What’s a seed in a random number generator and why does it matter.

---
