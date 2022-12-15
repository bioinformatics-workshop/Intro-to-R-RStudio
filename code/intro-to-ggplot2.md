# Introduction to ggplot2

In this session, we will work with data visualization using `ggplot2`. Although there are many systems in R for generating graphs, ggplot2 is the most versatile and elegant. We will use examples from the [R Graphics Cookbook](https://r-graphics.org).

> ggplot2 implements the **grammar of graphics**, a coherent system for describing and building graphs. With ggplot2, you can do more faster by learning one system and applying it in many places. [R4DS-Data Visualization](https://r4ds.had.co.nz/data-visualisation.html)

## Resources on ggplot2
---
- [The R Graphics Cookbook](http://www.cookbook-r.com/Graphs) by Winston Chang
- [Plotting Anything with ggplot2](https://youtu.be/h29g21z0a68) by Thomas Lin Pedersen (webinar)
- [R4DS-Data Visualization](https://r4ds.had.co.nz/data-visualisation.html) by Hadley Wickham & Garrett Grolemund
- [ggplot2: Elegant Graphics for Data Analysis](https://ggplot2-book.org/) is a more advanced and in-depth assessment of the theoretical underpinnings of ggplot2
- [Colorbrewer](https://colorbrewer2.org/) provides good recommendation for color selection
## Installation
---
Install R package through CRAN with:
```{r library}
install.package('ggplot2')
library(ggplot2)

install.packages("reshape2") # a package containing datasets
```

## Basic Syntax
---
```
ggplot(data = data_file, aes(x = , y = )) + geom_layer

    geom_bar()
    geom_histogram()
    geom_density()
    geom_boxplot()
    geom_point() # scatter plots
    geom_pie()
```
**data**: data to plot  
**aes**: aesthetic mappings between variables in the data  
**geom**: layer describing how to render the observations (data)  

## Layering Plots
---
We can layer multiple plots on top of each other. For example, if we want to plot histogram and density plots together, we use the '+' sign to add additional plots. 
```
ggplot(data = data_file, aes(x = , y = )) +
    geom_histogram() +
    geom_density()
```
## Saving Plots
---
Plots generated using ggplot2 can be saved to file using the `ggsave` function. The function will save, by default, the last plot to file.
```
ggsave(plotname, filename, output_parameters)

plt <- ggplot(data, aes(ratings)) + geom_hist()

# This will save the plot "plt" into a file name "histogram_plot.pdf" as a PDF with 300 dpi at 4in x 4in

ggsave(plt, "histogram_plot.pdf", width = 4, height = 4, dpi = 300)
```

**File formats**: pdf, png, jpeg, tiff, eps, ps, bmp, svg
