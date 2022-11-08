## UFC Fight Feature Extraction

### Usage

- From the root i.e. `UFC-Predictions`, Simply run `python -m src.create_ufc_data`

### Details

- Forked from https://github.com/WarrierRajeev/UFC-Predictions, with web app removed, data quality improvement implemented (only using Unified MMA Rules), and new features engineered (loss by KO/TKO features). These improvements result in more balanced data with further important predictors of fight events.
- Event and fight stats data now being scraped from 2010 (as the boxing commissions adopted the Unified MMA Rules in July 2009) to present date.

### Details about the data

#### Context

Generally the underdog is in the blue corner and favourite fighter is in the red corner. Every row contains information about both fighters, fight details and the winner.

#### Content

Each row is a compilation of both fighter stats. Fighters are represented by 'red' and 'blue' (for red and blue corner). So for instance, red fighter has the complied average stats of all the fights except the current one. The stats include damage done by the red fighter on the opponent and the damage done by the opponent on the fighter (represented by 'opp' in the columns) in all the fights this particular red fighter has had, except this one as it has not occured yet (in the data). Same information exists for blue fighter. The target variable is 'Winner' which is the only column that tells you what happened.
Here are some column definitions:

#### Column definitions:

- `R_` and `B_` prefix signifies red and blue corner fighter stats respectively
- `_opp_` containing columns is the average of damage done by the opponent on the fighter
- `KD` is number of knockdowns
- `SIG_STR` is no. of significant strikes 'landed of attempted'
- `SIG_STR_pct` is significant strikes percentage
- `TOTAL_STR` is total strikes 'landed of attempted'
- `TD` is no. of takedowns
- `TD_pct` is takedown percentages
- `SUB_ATT` is no. of submission attempts
- `PASS` is no. times the guard was passed?
- `REV` are the number of reversals
- `HEAD` is no. of significant strinks to the head 'landed of attempted'
- `BODY` is no. of significant strikes to the body 'landed of attempted'
- `CLINCH` is no. of significant strikes in the clinch 'landed of attempted'
- `GROUND` is no. of significant strikes on the ground 'landed of attempted'
- `win_by` is method of win
- `last_round` is last round of the fight (ex. if it was a KO in 1st, then this will be 1)
- `last_round_time` is when the fight ended in the last round
- `Format` is the format of the fight (3 rounds, 5 rounds etc.)
- `Referee` is the name of the Ref
- `date` is the date of the fight
- `location` is the location in which the event took place
- `Fight_type` is which weight class and whether it's a title bout or not
- `Winner` is the winner of the fight
- `Stance` is the stance of the fighter (orthodox, southpaw, etc.)
- `Height_cms` is the height in centimeter
- `Reach_cms` is the reach of the fighter (arm span) in centimeter
- `Weight_lbs` is the weight of the fighter in pounds (lbs)
- `age` is the age of the fighter
- `title_bout` Boolean value of whether it is title fight or not
- `weight_class` is which weight class the fight is in (Bantamweight, heavyweight, Women's flyweight, etc.)
- `no_of_rounds` is the number of rounds the fight was scheduled for
- `current_lose_streak` is the count of current concurrent losses of the fighter
- `current_win_streak` is the count of current concurrent wins of the fighter
- `draw` is the number of draws in the fighter's ufc career
- `wins` is the number of wins in the fighter's ufc career
- `losses` is the number of losses in the fighter's ufc career
- `total_rounds_fought` is the average of total rounds fought by the fighter
- `total_time_fought(seconds)` is the count of total time spent fighting in seconds
- `total_title_bouts` is the total number of title bouts taken part in by the fighter
- `win_by_Decision_Majority` is the number of wins by majority judges decision in the fighter's ufc career
- `win_by_Decision_Split` is the number of wins by split judges decision in the fighter's ufc career
- `win_by_Decision_Unanimous` is the number of wins by unanimous judges decision in the fighter's ufc career
- `win_by_KO/TKO` is the number of wins by knockout in the fighter's ufc career
- `win_by_Submission` is the number of wins by submission in the fighter's ufc career
- `win_by_TKO_Doctor_Stoppage` is the number of wins by doctor stoppage in the fighter's ufc career

Newly added features:
- `last_fight_L_TKO_Doctor_Stoppage` binary flag for whether last fight was lost by Doctor's Stoppage
- `all_fights_L_TKO_Doctor_Stoppage` count of the amount of fights lost by Doctor's Stoppage
- `last_fight_L_KO/TKO` binary flag` binary flag for whether last fight was lost by KO/TKO
- `all_fights_L_KO/TKO` count` count of the amount of fights lost by KO/TKO

#### Acknowledgements

- Inspiration/fork/original source code that this work builds upon: https://github.com/WarrierRajeev/UFC-Predictions