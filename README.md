# ICC Men's T20-Cricket World Cup 2022 Data Analytics
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

### Player Analysis 

|    Openers      |
![Opener](https://github.com/user-attachments/assets/7d1c2c6d-fc32-454b-a195-e5ea88c90034)



 | Middle Order |
![Middle Order](https://github.com/user-attachments/assets/7d587918-ce26-4f76-98ef-df6446743389)



 | Finisher |
![Finisher](https://github.com/user-attachments/assets/2389a2de-6445-456d-8db4-c0f50fbb8c6b)



| All Rounder |
![All Rounder](https://github.com/user-attachments/assets/1ac38bf6-ffad-4cb3-bde1-26b3dfb1e68f)



| Specilist Fast Bolwers |
![Fast Bowlers](https://github.com/user-attachments/assets/31d00a57-4e1f-47d4-abcc-2a6fad076ea2)



| Final Best 11 Players |
![Final 11](https://github.com/user-attachments/assets/366b4839-768f-4009-8ba0-1fb073b64b2a)


| ToolTips |
![ToolTips1](https://github.com/user-attachments/assets/2cdd4836-ef57-404f-a056-4687c65f6411)



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

https://2022.t20worldcup.com/

https://stats.espncricinfo.com/ci/engine/records/team/match_results.html?id=14450;type=tournament

https://www.espncricinfo.com/series/icc-men-s-t20-world-cup-2022-23-1298134/namibia-vs-sri-lanka-1st-match-first-round-group-a-1298135/full-scorecard
