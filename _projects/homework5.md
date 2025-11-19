---
title: 
---

In this assignment, I explored the UIUC Building Inventory dataset to understand historical construction trends and agency resource accumulation.

## Plot 1: Construction Timeline (Static)

This plot visualizes the timeline of building construction from 1900 to the present day. I chose a Line Chart encoding because the primary goal is to show trends over a continuous temporal variable (Year Constructed). The Y-axis utilizes a simple `count()` aggregation to highlight periods of high activity, such as the post-WWII expansion era. I filtered the data to exclude years prior to 1900 and removed invalid entries to ensure the timeline accurately reflects modern infrastructure development.

<vegachart schema-url="/assets/json/building_construction_by_year.json" style="width: 100%"></vegachart>

## Plot 2: Cumulative Growth by Agency (Interactive)

For the second visualization, I focused on the cumulative growth of infrastructure for the top 20 agencies. Instead of showing yearly construction, I used a `window transform` in Altair to calculate the **cumulative sum** of square footage. This design choice reveals the total scale of facilities managed by an agency at any point in history.

To handle the complexity of the dataset, I implemented an **Interactive Legend** rather than a standard dropdown. This allows the user to **Multi-Select** (using Shift+Click) specific agencies to compare their growth trajectories directly. The unselected lines fade to low opacity, solving the "spaghetti plot" issue common in multi-line time series data.

<vegachart schema-url="/assets/json/cumulative_growth.json" style="width: 100%"></vegachart>

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/ericpelinski/ericpelinski.github.io/blob/main/NAME_OF_YOUR_NOTEBOOK.ipynb" text="The Analysis" %}
</div>
