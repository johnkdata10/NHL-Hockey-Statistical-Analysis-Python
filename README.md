# Project Background & Overview

I am using data found at http://www.inalitic.com/datasets/nhl%20player%20data.html
The data contains 22 categories of offensive statistics in the NHL for every season from 1940 to 2018.

I have had a lifelong interest in NHL hockey and have always been under the impression that players who rack up more offensive categories are more likely to score more points (goals and assists) in a season. I also suspect these players are more likely be on the team that wins the Stanley Cup.

# My goals for this project
To capture and analyze seasons of data from 1999-2018 to confirm or deny my impression that players who achieve higher offensive statistics lead to more goals and assists scored. I also want to explore how other factors, like a player's position, age, shots taken, and time-on-ice, may or may not result in higher points scored in each season.

# What I hope to learn from this data project.
I hope to identify any positive or negative significant patterns and correlations between 'Goals', 'Assists', and 'Points' and the following NHL offensive statistics: 'Season', 'Age', 'Team', 'Position', 'Games Played', 'Shots', 'Shot Percentage', 'Time-On-Ice', 'Blocks', and 'Hits'. More specifically, I hope to learn about which of the aforementioned offensive categories may or may not correlate to earning more 'Goals' and 'Assists' ('Points') in any given season. I also hope to learn about whether or not blocks and hits correlate with higher goals, assists, and points earned and which seasons and positions tallied the most goals and assists (points). I would also like to explore which position typically scores more goals and assists in a season.

# My hunch about what this data will reveal.
I have a hunch this data will reveal that players who earn higher offensive stats in categories like 'Games Played', 'Shots', and 'Time-On-Ice' are typically more likely to score more 'Goals' and 'Assists' ('Points') in a season than players who earn less in these categories. Also, based on the nature of each position, I have a hunch that left-wing (LW) and right-wing (RW) positions will score the most goals, centers (C) will earn the most assists, and defensemen (D) and centers (C) will earn the most 'Blocks and 'Hits' per season. I also have a hunch that 'Blocks' and 'Hits' will correlate less with 'Goals' and 'Assists' ('Points') earned in a season with the exception of a few outlier players.

# Population being represented by the data I've chosen
The population being represented is every NHL player from 1940-2018 who earned at least one offensive statistic in one category.

# Total sample size
37,826 rows and 28 rows which contains every NHL player who earned an offensive statistic from 1940-2018

# How the data was collected
The data was collected from publicly available NHL stats stored at https://www.hockey-reference.com/ and http://www.inalitic.com/datasets/nhl%20player%20data.html This is not a random sample and sampling weights are not used. The data collected contains only offensive categories during a specific period of time (1940-2018).

# Data dictionary and variables that will be used for this project.
1. Unnamed: 0 = (string type) combined data on season and player name
2Season = (integer type) year played by the corresponding NHL player - WILL BE USED
3Player = (string type) name of corresponding NHL player - WILL BE USED
4Age = (float type) age of corresponding NHL player - WILL BE USED
5Tm = (string type) team of corresponding NHL player - WILL BE USED
6Pos = (string type) position of corresponding NHL player - WILL BE USED
7GP = (integer type) games played by corresponding NHL player in in corresponding season - WILL BE USED
8. G = (string type) goals scored by corresponding NHL player in corresponding season - WILL BE USED
9. GPG = (float type) goals scored per game by corresponding NHL player in corresponding season - WILL BE USED
10. A = (string type) assists earned by corresponding NHL player in corresponding season - WILL BE USED
11. PTS = (string type) totals points scored by corresponding NHL player in corresponding season - WILL BE USED
12. +/- = (string type) plus\minus of corresponding NHL player in corresponding season
13. PIM = (string type) penalties in minutes by corresponding NHL player in corresponding season
14. EVG = (string type) even strength goals scored by corresponding NHL player in corresponding season
15. PPG = (string type) power play goals scored by corresponding NHL player in corresponding season
16. SHG = (string type) shorthanded goals scored by corresponding NHL player in corresponding season
17. GWG = (string type) game-winning-goals scored by corresponding NHL player in corresponding season
18. EVA = (string type) even strength assists scored by corresponding NHL player in corresponding season
19. PPA = (string type) power play assists earned by corresponding NHL player in corresponding season
20. SHA = (string type) shorthanded assists earned by corresponding NHL player in corresponding season
21. S = (string type) total shots of corresponding NHL player in corresponding season - WILL BE USED
22. S% = (string type) shot percentage of corresponding NHL player in corresponding season - WILL BE USED
23. TOI = (string type) total time-on-ice of corresponding NHL player in corresponding season - WILL BE USED
24. ATOI = (string type) average time-on-ice per game of corresponding NHL player in corresponding season
25. BLK = (float type) total number of blocks of corresponding NHL player in corresponding season - WILL BE USED
26. HIT = (float type) total number of hits by corresponding NHL player in corresponding season - WILL BE USED
27. FOwin = (float type) total number of face-off wins by corresponding NHL player in corresponding season
28. FOloss = (float type) total number of face-off losses by corresponding NHL player in corresponding season
29. FO% = (float type) total face-off win percentage of corresponding NHL player in corresponding season

# Project Findings

# Introduction
It is widely accepted among NHL fans that NHL players who rack up higher numbers in categories like shots, games played, and time-on-ice are more likely to score a higher number of goals and assists in a season. This report explores these assumptions by analyzing 20 seasons of offensive NHL statistics. The data was collected from publicly available NHL stats compiled at hockey-reference.com and inalitic.com in a CSV file. The data contains mostly offensive categories, and the population represented is every NHL player from 1940-2018 who earned offensive statistics in at least one category. The categories for analysis include a player’s position, goals, assists, points, shots, games played, time-on-ice, blocks, and hits. More specifically, each category was analyzed to discover how they correlate with higher goals and assists scored in a season, and which position typically earns the most goals, assists, blocks, and hits per season. The following four hypotheses are tested:

1. Players who earn higher numbers in games played, shots, and time-on-ice are more likely to score more goals and assists in a season.
2. Left-Wing (LW) and Right-Wing (RW) positions are the most offensive-minded players.
3. Centers (C) are the playmakers of the game.
4. Defensemen (D) and Centers (C) are the most physically demanding positions.

# Data Preparation and Analysis
The raw dataset contained 37,826 rows and 28 columns. All entries were converted to the proper data types, and entries with missing or nulls values were replaced with an integer value of ‘0’. All rows and columns with significant outliers were dropped, specifically players who achieved 100% shot percentage and/or 0-50 minutes of time-on-ice because in any given season, it is virtually impossible for players to achieve this. As a result, only players with 26 or more games played and more than 50 minutes of time-on-ice were retained in the original dataset in order to create a realistic benchmark for all statistics earned. From this, a total of 32,563 rows were eliminated leaving a remainder of 5,262 rows and 15 columns from seasons 1999-2018. Players were also separated into three categories: 1) Category 1 (goalsCat1) representing players who averaged 17 or more goals per season, 2) Category 2 (goalsCat2), representing players who averaged 14-16 goals per season, and 3) Category 3 (goalsCat3), representing players who averaged 0-13 goals per season. Table 1 provides more detail about the variables used throughout this exploratory data analysis.

# Hypothesis 1 – Higher Games Played, Time-On-Ice, and Shots Lead to More Goals and Assists.

# Games Played and Goals.
No significant patterns were revealed between the number of games played and goals scored. In fact, nearly 100% of players who played 80 or more games in a season scored less than 20 goals a season. This may indicate that quality of ice-time per game is more significant than the sheer number of games played. The hypothesis that more game played lead to mores goals scored was unsupported.

# Time-On-Ice, Goals and Assists.
High positive correlations were discovered between time-on-ice, goals, and assists. For example, to hit the 10-goal mark, players played at least 300 minutes; to hit the 20-goal mark, players played at least 700 minutes, and so on. Also, to hit the 10-assist mark, players played at least 300 minutes; to hit the 20-assist mark, players played at least 500 minutes, and so on. This makes sense because more time-on-ice naturally increases a player’s opportunities to rack up offensive stats. The hypothesis that more time-on-ice leads to more goals and assists was supported and suggests that coaches may want to increase their top players’ ice-time per game to increase their team’s scoring chances.

# Shots and Goals
Although goals shared positive correlations with a higher number of shots, the data revealed no clear indication that more shots automatically lead to more goals scored. For example, players who tallied 150 or more shots per season ranged between 5-30 goals per season. As a result, this hypothesis was unsupported, but it perhaps indicated that strategizing for better scoring opportunities is key to more goals rather than simply throwing pucks at the net.

#Hypothesis 2 – Left-Wing (LW) and Right-Wing (RW) are the most offensive-minded players.
The analysis did not support hypothesis 2 because the Center (C) position scored the largest portion of goals every year (Figure 3). This suggests that Centers (C) are arguably the most offensive-minded players on a team. From this, coaches may want to increase ice-time of their Centers (C) to increase their team’s scoring opportunities.

#Hypothesis 3 – Centers (C) are the playmakers of the game.
The analysis revealed that Centers (C) earn the most assists every year thus supporting hypothesis 3 that Centers (C) are the playmakers of the game. Based upon the nature of the position, this makes sense and reinforces the notion that Centers (C) are arguably the most offensive-minded players on a team. Again, coaches may want to increase ice-time for some, or all, of their Centers (C) due to the offensive nature of their position.

# Hypothesis 4 – Defensemen (D) and Centers (C) are most physically-demanding positions.
Hypothesis 4 was heavily confirmed as Defensemen (D) earned the most blocks every year by nearly a 2 to 1 margin. This makes sense because the Defenseman (D) position is designed to defend against offensive attacks, specifically to prevent shots-on-goal. Centers (C) recorded the most hits followed by Left-Wing (LW), Right-Wing (RW), and Defenseman (D). It makes sense that Centers (C) tallied the highest number of hits given the grit demanded of its position, but it was surprising to see Defensemen (D) with the least amount of hits given the rough nature of the position to defend against attacks in one’s own zone. This perhaps suggests that aggressive players are often assigned offensive-type positions like Center (C), Right-Wing (RW), or Left-Wing (LW) in order to provide Defensemen (D) more leeway to focus solely on blocks and defense.

# Conclusion
The data revealed that racking up higher numbers in offensive categories does not necessarily lead to scoring more goals. For example, hypothesis 1 was partially supported as increased time-on-ice lead to more goals and assists scored, but surprisingly, more games played did not. This indicated that the quality of ice-time in each game is more important than simply aiming to play a full season of 82 games. Moreover, although goals increased with a higher number of shots, there was no clear indication that a higher number of shots automatically lead to more goals scored. This highlighted that perhaps the key to scoring goals is a player’s or coach’s ability to formulate clever scoring opportunities, rather than simply relying on a player to throw pucks at the net. Again, hypothesis 1 was partially supported. Hypotheses 2 and 3 were also partially supported as Centers (C) were found to be the most offensive-minded, physically demanding position – while also being the playmaker – making them the most valuable position on a team. From this, coaches may want to consider increasing ice-time for all their Centers (C) in order to increase the team’s scoring chances. Additionally, general managers may want to consider investing larger sums of money to acquire more highly skilled Centers (C) or acquire players that enhance their Centers’ (C) abilities. Hypothesis 4 was partially supported as Defensemen (D) tallied the most blocks, but surprisingly, Defensemen (D) recorded the least amount of hits each season. This indicated that although the Defenseman (D) position is indeed physically demanding, aggressive players are likely assigned offensive positions in order to give Defensemen (D) more leeway to focus solely on preventing breakouts and protecting the net. No difficulties were experienced with the data but it would be interesting to take it a step further and analyze the dynamics of each position with other variables like plus/minus (+/-), penalties-in-minutes (PIM), power-play goals (PPG), and short-handed goals (SHG). It would also be interesting to see how Category 1 players compare to Category 2 and 3 players in the playoffs because playoff hockey is considered entirely different than regular season hockey.
