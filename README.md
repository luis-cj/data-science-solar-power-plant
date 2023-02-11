# Data science project: solar power plant analysis using power generation data
Data science project analysing solar power plant generation data to help a renewable energy supplier make strategic decisions.

This is a **discovery project**, where the main goal is to explore the data sources, check hypotheses and find out new patterns and insights relevant for the business without requiring any machine learning algorithm.

## Context
A renewable energy supplier owns solar power plants that produce electrical energy. Two of those power plants present power production anomalies and the maintenance team does not know the root of the problem.

<p align="center">
  <img width="500" height="500" src="https://github.com/luis-cj/data-science-solar-power-plant/blob/main/images/plant2.gif">
</p>

Before sending the technical team to fix the problem the data science team is required to analyse the sensors' data to make a first approximation to the root cause of failure of the equipment.

## Methodology

### 1. Objective
Analyse the available data to find out what is causing the problem in the power plants and conclude if it is necessary to send a technical team to fix the problem in site.

### 2. Levers (action variables)
It is necessary to have some knowledge about how the energy is generated in a solar power plant. The data science team has been informed by the technical team on how the process works. 

With that, the levers (variables that affect the business objective, which in this case is generating AC power) are the following:

- **Irradiance**: the greater the irradiance the more DC power can be generated. But there is a limit since at very high panel temperatures the generation capacity is decreased.
- **Panel cleaning**: it is important to have clean modules so they can perform at their full capacity.
- **Inverters' performance**: the process of transforming DC into AC is never 100% efficient. But the closer to 100% the better.
- **Sensors**: if sensors do not work correctly then it is not possible to detect potential plant failures.
