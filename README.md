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

Before proceeding with the other points, it is important to know the basics of solar power production. 

### What is a solar power plant?

<p align="center">
  <img width="542" height="238" src="https://github.com/luis-cj/data-science-solar-power-plant/blob/main/images/How_Solar_Power_Works.png">
</p>

A solar power plant is a facility that generates electricity using photovoltaic (PV) cells that convert sunlight into electricity. The PV cells are arranged in arrays or modules and connected to inverters that convert the direct current (DC) electricity produced by the cells into alternate current (AC) electricity that can be fed into the power grid or directly used to switch on electrical household appliances.

During the day, the PV cells produce electricity as long as there is sunlight, and any excess electricity can be stored in batteries or exported to the grid. At night or when there is not enough sunlight, electricity is drawn from the grid or from the batteries.

In this case only the generation data is taken into account assuming there are no batteries as energy storage systems.

### 2. Levers (action variables)
It is necessary to have some knowledge about how the energy is generated in a solar power plant. The data science team has been informed by the technical team on how the process works. 

With that, the levers (variables that affect the business objective, which in this case is generating AC power) are the following:

- **Irradiance**: the greater the irradiance the more DC power can be generated. But there is a limit since at very high panel temperatures the generation capacity is decreased.
- **Panel status**: it is important to have clean modules so they can perform at their full capacity.
- **Inverters' performance**: the process of transforming DC into AC is never 100% efficient. But the closer to 100% the better.
- **Sensors**: if sensors do not work correctly then it is not possible to detect potential plant failures.

### 3. KPIs
- Irradiance: is measured as the rate of solar energy hitting a surface per squared meter [W/m<sup>2</sup>].
- Ambient temperature and module temperature: measured by the sensors [??C].
- DC power: power measured in direct current from the panels to the inverters [kW].
- AC power: power measured in alternate current from the inverters to the grid [kW].
- Inverters' efficiency: ratio of the AC power delivered to the grid to the DC power generated by the PV panels [%].

### 4. Entities and data
The relevant entities we can retrieve data from in order to accomplish our objective are the following:

- Solar power plants: there are 2
- Inverters: there are many inverters in each plant
- Irradiance sensor: 1 for each plant
- Ambient temperature sensor: 1 for each plant
- Module temperature sensor: 1 for each plant

All the sensors retrieve data every 15 minutes, and the total data set comprises 34 days.

### 5. Seed questions
These are the first questions we need to start finding relevant insights. Different questions apply to each lever.

About irradiance:

- Is there enough irradiance every day?
- Is it similar for both power plants?
- What is its hourly distribution for each plant?
- How does it relate to ambient and module temperature?

About panel status (DC generation):

- What is the relationship between irradiance and DC generation?
- Is it affected by ambient or module temperature?
- Is it similar for both power plants?
- What is its daily distribution for each plant?
- Is it constant throughout the days?
- Has there been any failure?

About inverters' performance (AC generation):

- What is the relationship between DC and AC generation?
- Is it similar for both power plants?
- What is its daily distribution for each plant?
- Is it constant throughout the days?
- Is it constant for every inverter?
- Has there been any failure?

About sensors:

- Are the irradiance data reliable?
- Are the temperature data reliable?
- Are the DC data reliable?
- Are the AC data reliable?
- Are data between both power plants similar?

### 6. Analysis and insights
All the analysis is carried out in the following Jupyter Notebooks (Python):

[Solar power plant generation analysis - Python script (PART 1 - DATA QUALITY)](https://github.com/luis-cj/data-science-solar-power-plant/blob/main/solar_power_plant_part_1.ipynb)

[Solar power plant generation analysis - Python script (PART 2 - DATA TRANSFORMATION)](https://github.com/luis-cj/data-science-solar-power-plant/blob/main/solar_power_plant_part_2.ipynb)

[Solar power plant generation analysis - Python script (PART 3 - ANALYSIS AND INSIGHTS)](https://github.com/luis-cj/data-science-solar-power-plant/blob/main/solar_power_plant_part_3.ipynb)

### 7. Communication
For this project a report was generated in the format of a PowerPoint presentation, communicating all the analysis and found insights.
The report can be checked in the following file:

[Data analysis summary PDF](https://github.com/luis-cj/data-science-solar-power-plant/blob/main/solar_power_plant_conclusions.pdf)

## BONUS: Lessons learnt

- **Sometimes data do not make sense**. It is important to have good communication with the clients or stakeholders because at some point we may need some clarifications about data (missing values, wrong units, wrong dates, etc).
