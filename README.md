# Baseball Analytics
 
## Exploratory Data Analysis and Machine Learning

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a6/Major_League_Baseball_logo.svg/1200px-Major_League_Baseball_logo.svg.png" width=600>

<br>
<br>

### Introduction

This project uses data from Major League Baseball for:

 - exploratory data analysis
 - data visualizations
 - machine learning models
 - web scraping
 - API

----

### Dataset

All data used for exploratory data analysis, data visualziations and machine learning comes from the 2022 MLB season using the pybaseball library.

Web scraping takes data from Baseball Almanac.

API uses the MLB stats API

----

### Batting Stats

Batting stats from the 2022 season

**Qualified Batters with a Batting Average Over .300**

<img width="296" alt="batting_stats_1_ba" src="https://github.com/danielcho16/baseball_analytics/assets/82684796/dfc03fb2-308b-4509-b88e-3164b8ebace7">

<br>
<br>

**Batters with 30+ Home Runs**

<img width="293" alt="batting_stats_2_homeruns" src="https://github.com/danielcho16/baseball_analytics/assets/82684796/10a2feb7-023f-4643-98b2-90a24c23014c">

<br>
<br>

**Scatterplot of Home Runs vs At Bats**

![batting_stats_3_hr_vs_ab](https://github.com/danielcho16/baseball_analytics/assets/82684796/b79518b4-7eec-4ab5-97b8-4a054bff4f1a)

----

### Pitching Stats

Pitching stats from the 2022 season

**Qualified Starting Pitchers with an ERA under 3.00**

<img width="291" alt="pitching_stats_1_era" src="https://github.com/danielcho16/baseball_analytics/assets/82684796/48a23844-7581-47ae-8d5b-d4ce1a41fe62">

**Starting Pitchers with 200+ Strikeouts**

<img width="271" alt="pitching_stats_2_strikeouts" src="https://github.com/danielcho16/baseball_analytics/assets/82684796/82433769-906f-448c-860d-a434cac93bbb">

----

### Statcast Data and Data Visualizations

**Aaron Judge - NY Yankees**

Statcast data from the 2022 season for Aaron Judge

Result of Every Plate Appearance by Judge

![statcast_judge_1_pa_results](https://github.com/danielcho16/baseball_analytics/assets/82684796/a49ccbf3-35d2-4f54-85dc-3cdf1a0d6431)

<br>
<br>

Replot of Batted Ball Launch Speed and Launch Angle by Pitch Type by Judge

![statcast_judge_2_launch_speed_vs_launch_angle](https://github.com/danielcho16/baseball_analytics/assets/82684796/e1c17f9a-60a2-49da-8c0d-5e5605ba7c59)

<br>
<br>

Displot of Batted Balls Hit Distance by Pitch Type by Judge

![statcast_judge_3_batted_balls_distance](https://github.com/danielcho16/baseball_analytics/assets/82684796/c7abf1d3-0f29-4677-8299-b5a3d6eabc54)

<br>
<br>
<br>

**Clayton Kershaw - LA Dodgers**

Statcast data from the 2022 season for Clayton Kershaw

Count of Every Pitch Thrown by Kershaw

![statcast_kershaw_1_count_pitch_type](https://github.com/danielcho16/baseball_analytics/assets/82684796/1b13ab6e-f2f7-4ec1-9164-4cf32efb2d38)

<br>
<br>

Displot of Pitch Velocity by Pitch Type by Kershaw

![statcast_kershaw_2_pitch_velocity_pitch_type](https://github.com/danielcho16/baseball_analytics/assets/82684796/971c390c-2882-490b-b498-fac765b9f384)

<br>
<br>

Relplot of Pitch Velocity vs Spin Rate by Pitch Type by Kershaw

![statcast_kershaw_3_pitch_velocity_spin_rate](https://github.com/danielcho16/baseball_analytics/assets/82684796/cf697422-abcf-41fc-954d-0be8f8c1dcf7)

----

### Salary Data

**Scatterplot of Dollar Spent per Win for the LA Dodgers and Pittsburgh Pirates (1985-2016)**

![salary_data_dodgers_pirates_dollars_spent_per_win](https://github.com/danielcho16/baseball_analytics/assets/82684796/f091284f-5809-4344-881b-4ed01599f236)

----

### Machine Learning models

**Linear Regression**

Training and testing data uses data from the 2010-2022 seasons

Creating a linear regression model to predict a hitter's wRC+ for the next season

<br>

Train Test Split and Linear Regression

```
X = hits_df.drop(['Season','Name','wRC+_next_season'],axis=1)
y = hits_df['wRC+_next_season']

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

lr = LinearRegression()
lr.fit(X_train,y_train)
```

<br>

Training Data Mean and Mean Absolute Error

```
y_pred = lr.predict(X_train)

X_train['wRC+'].mean()
mean_absolute_error(y_pred,y_train)
```

<img width="302" alt="ml_lr_1_train_data_mean_mae" src="https://github.com/danielcho16/baseball_analytics/assets/82684796/f924519d-530e-4042-bd6c-22fcb597eee2">

<br>
<br>

Testing Data Mean and Mean Absolute Error

```
y_pred = lr.predict(X_test)

X_test['wRC+'].mean()
mean_absolute_error(y_pred,y_test)
```

<img width="302" alt="ml_lr_2_test_data_mean_mae" src="https://github.com/danielcho16/baseball_analytics/assets/82684796/66a1f8c6-ecfa-4a60-91ac-267d97ed4d27">

<br>
<br>

2022 Season Mean and Mean Absolute Error

```
y_pred = lr.predict(X)

hits_2022_df['wRC+'].mean()
mean_absolute_error(y_pred,y)
```

<img width="302" alt="ml_lr_3_2022_mean_mae" src="https://github.com/danielcho16/baseball_analytics/assets/82684796/8fdd0513-21b5-4e3c-a9e2-00225d514219">

<br>
<br>

Dataframe with actual wRC+ and predicted wRC+

<img width="426" alt="ml_lr_4_wrc+_predicted_wrc+" src="https://github.com/danielcho16/baseball_analytics/assets/82684796/3dd7c9f6-a98e-4a63-b572-b7cbe7a1909a">

<br>
<br>
<br>

**Classification - Decision Tree**














