---
title: "Homework 5"
date: 2025-11-19
tags: [data viz, altair, python]
---

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

In this assignment, I explored the UIUC Building Inventory dataset to understand historical construction trends and agency infrastructure accumulation.

## Plot 1: Buildings Constructed By Year

This plot visualizes the timeline of building construction for all agencies combined from 1900 to 2019. I chose a Line Chart encoding because the primary goal is to show trends over time (Year Constructed). The Y-axis uses count() aggregation to display the amounts of buildings constructed in a given year. 

I filtered the data to exclude years prior to 1900 since that data contains a lot of missing information, as well as to keep the visualization more relevant to current times. Doing this also allowed the width of the visualization to be reduced, making it easier to read and interperet.

I used ordinal encoding for the year, since I didn't want years to be expressed as a continuous numerical variable. By using ordinal encoding, each year was given its own "bucket", preventing any errors such as decimal points if you were to zoom in on the graph.
<div id="vis1"></div>

<script type="text/javascript">
  var spec1 = "{{ site.baseurl }}/assets/json/building_construction_by_year.json";
  vegaEmbed('#vis1', spec1).catch(console.error);
</script>

## Plot 2: Cumulative Growth by Agency

For the second visualization, I focused on the cumulative growth of infrastructure each agency. Instead of showing yearly construction, I displayed the cumulative amount of square footage owned by each agency in a line plot, which I think helps users understand and compare the infrastructural growth of different agencies throughout time. To reduce the clutter of having every single agency displayed at once, I implemented a dropdown select menu, allowing users to choose the agency being displayed on the plot. 

Similarly to Plot 1, I used ordinal encoding for the years. For the cumulative square footage (the Y axis), I used quantitative encoding because it is representative of a continuous numerical measurement of square footage. 

As for coloring, I didn't use any colormaps. Instead, I used nominal encoding to ensure each agency is represented by a distinct color, which helps add interesting visuals for users. 


<div id="vis2"></div>

<script type="text/javascript">
  var spec2 = "{{ site.baseurl }}/assets/json/cumulative_growth.json";
  vegaEmbed('#vis2', spec2).catch(console.error);
</script>

<div class="left">
{% include elements/button.html link="https://github.com/UIUC-iSchool-DataViz/is445_data/blob/main/building_inventory.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/ericpelinski/ericpelinski.github.io/blob/main/python_notebooks/Workbook.ipynb" text="The Analysis" %}
</div>
