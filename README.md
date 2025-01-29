# 🏏ICC Men's_T20Cricket_WorldCup2022_DataAnalysis🏆

![ICC MEN'S t20](https://images.icc-cricket.com/image/upload/t_ratio21_9-size60/prd/mdshkinerjyzccdxwc5j)

![Power Bi](https://img.shields.io/badge/power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)

## Table of Contents :

- [Problem Statement](https://github.com/yogeshkasar778/PowerBI_Project-ICCMen-s_T20_Cricket_World_Cup_2022_data_analytics#problem-statement-)
- [Datasource](https://github.com/yogeshkasar778/PowerBI_Project-ICCMen-s_T20_Cricket_World_Cup_2022_data_analytics#datasource-)
- [Data Collection](https://github.com/yogeshkasar778/PowerBI_Project-ICCMen-s_T20_Cricket_World_Cup_2022_data_analytics#data-collection)
- [Data Transformation](https://github.com/yogeshkasar778/PowerBI_Project-ICCMen-s_T20_Cricket_World_Cup_2022_data_analytics#data-transformation)
- [Data Modelling](https://github.com/yogeshkasar778/PowerBI_Project-ICCMen-s_T20_Cricket_World_Cup_2022_data_analytics#data-modelling)
- [Data Analysis Expression (DAX)](https://github.com/yogeshkasar778/PowerBI_Project-ICCMen-s_T20_Cricket_World_Cup_2022_data_analytics#data-analysis-expression-dax)
- [Report](https://github.com/yogeshkasar778/PowerBI_Project-ICCMen-s_T20_Cricket_World_Cup_2022_data_analytics#dashboard)
- [Tools, Software and Libraries](https://github.com/yogeshkasar778/PowerBI_Project-ICCMen-s_T20_Cricket_World_Cup_2022_data_analytics#tools-software-and-libraries-)
- [References](https://github.com/yogeshkasar778/PowerBI_Project-ICCMen-s_T20_Cricket_World_Cup_2022_data_analytics#references)

## Problem Statement :

In This project Created a Power BI Dashboard which helps to review and compare performances of all the players in T20 Men's Cricket World Cup 2022 tournament. This dashboard also enables us to select the best 11 of the tournament based on their performance based on defined selection criteria which is included as a part of problem statement.

## Datasource :

Scrapped all the data regarding match and world cup from www.espncricinfo.com and all details of player career performace and collect data on [brightdata](https://brightdata.com/)

## Data Collection:
Scrapped all the data regarding match and world cup and all details about players career from [brightdata](https://brightdata.com/) using Beautiful Soup library and Jupyter Notebook is used to convert the json files into the dataframes and then these dataframes into csv file for further data analysis on power bi.

## Data Transformation:
Performed initial data cleaning after scrapping such as player name correction, handle missing value, match id linking etc. using Pandas. Transformed the final data for dashboard using Power Query of Power BI.

## Data Modelling:
Connected all the datasets with based on some defined primary keys such as team and match ids. Also, created many measures, calculated columns and parameters for data analysis and dash boarding using DAX.

## Data Analysis Expression (DAX)
Measures used in visualization are:

- Total Runs = `SUM(t20_batting_summary[runs])`

- Total Innings Batted =`COUNT(t20_batting_summary[matchID])`

- Total Innings Dismissed = `SUM(t20_batting_summary[Out])`

- Batting Avg = `DIVIDE([Total Runs],[Total Innings Dismissed],0)`

- Total balls faced =`SUM(t20_batting_summary[balls])`

- Strike rate = `DIVIDE([Total Runs],[total balls faced],0)*100`

- Batting Possition = `ROUNDUP(AVERAGE(t20_batting_summary[battingPos]),0)`

- Boundary % = `DIVIDE(SUM(t20_batting_summary[Boundary runs]),[Total Runs],0)*100`

- Avg. balls faced = ` AVERAGE(t20_batting_summary[balls])`

- wickets = `SUM(t20_bowling_summary[wickets])`

- Balls Bowled = `SUM(t20_bowling_summary[balls])`

- Runs Conced = `SUM(t20_bowling_summary[runs])`

- Economy = `DIVIDE([Runs Conced],([Balls Bowled]/6),0)`

- Bowling Strike Rate =`DIVIDE([Balls Bowled],[wickets],0)`

- Bowling Avrage = `DIVIDE([Runs Conced],[wickets],0)`

- Total Innings Bowled = `DISTINCTCOUNT(t20_bowling_summary[matchID])`

- Dot Ball % =` DIVIDE(SUM(t20_bowling_summary[zeros]),SUM(t20_bowling_summary[balls]),0)`

- Player selection = `if(ISFILTERED(t20_players_info[name]),"1","0")`

- Display Text = `if([Player selection] = "1"," ","Select Player(s) by clicking the player's name to see their invidual or combined strength")`

- Color Callout Value =`if([Player selection]="0","#E8D166","#1D1D2E")`

- boundary runs batting =`t20_batting_summary[fours]*4 + t20_batting_summary[sixes]*6`

- boundary runs bowling =`t20_bowling_summary[fours]*4+t20_bowling_summary[sixes]*6`

## Reports:
Data visualization for the dataset was done using Microsoft Power BI Desktop:

### 📊 Player Analysis 

|    Power Hitters/ Openers      |
| --------------- |
|![2022 T20 Cricket World Cup Dashboard- Best Final 11-2](https://user-images.githubusercontent.com/81465377/211144386-48070a65-7e8b-4370-af44-121b878b554b.jpg)|

![hover_effect](https://user-images.githubusercontent.com/81465377/211144410-6e11c0cd-ab86-4357-b272-9019f5efa445.jpg)

![individual_stats](https://user-images.githubusercontent.com/81465377/211144427-bfb260dc-3586-4db2-879c-6d84f4e8ca2d.jpg)

 | Anchors/ Middle Order |
 | --------------- |
|![2022 T20 Cricket World Cup Dashboard- Best Final 11-3](https://user-images.githubusercontent.com/81465377/211144441-423d3ba3-76ab-49bf-b0d7-9b107ca2086f.jpg)|


 | Finisher |
 | --------------- |
|![2022 T20 Cricket World Cup Dashboard- Best Final 11-4](https://user-images.githubusercontent.com/81465377/211144456-6eb2581f-4574-4961-b693-4c8ff0dd7b19.jpg)|


| All Rounder |
| --------------- |
|![2022 T20 Cricket World Cup Dashboard- Best Final 11-5](https://user-images.githubusercontent.com/81465377/211144466-43003158-fe3e-41c0-b02a-ee4db2c53379.jpg)|


| Specilist Fast Bolwers |
| --------------- |
|![2022 T20 Cricket World Cup Dashboard- Best Final 11-6](https://user-images.githubusercontent.com/81465377/211144473-03ca6186-b8e8-419f-87a1-786f6a2d62a6.jpg)|


| Final Best 11 Players |
| --------------- |
|![2022 T20 Cricket World Cup Dashboard- Best Final 11-8](https://user-images.githubusercontent.com/81465377/211144486-4b48e1fc-fab3-4bb0-b660-7b4da5be627d.jpg)|


## Tools, Software and Libraries :

1.Jupyter Notebook

2.Python

3.Pandas

4.Webscraping

5.Beautifual Soup

6.Power Query Editor

7.Power BI

8.Anaconda Envirement

## References

https://codebasics.io/courses

https://2022.t20worldcup.com/

https://stats.espncricinfo.com/ci/engine/records/team/match_results.html?id=14450;type=tournament

https://www.espncricinfo.com/series/icc-men-s-t20-world-cup-2022-23-1298134/namibia-vs-sri-lanka-1st-match-first-round-group-a-1298135/full-scorecard

https://brightdata.com/cp/data_collector/collectors/c_lefxe7xf2rj3m5b1b3/code?draft_id=lefxeciy8d6v38d3d

## 💬 Feedback and Questions

If you have any feedback or questions about the project, please feel free to ask. We appreciate your input and are here to help. You can reach out by opening an issue on GitHub or by emailing me at [yashgs97312@gmail.com].

Thank you for exploring the ICC Men's T20 World Cup 2022 Analysis Project! We hope you find it useful and informative.

Happy Analyzing!
