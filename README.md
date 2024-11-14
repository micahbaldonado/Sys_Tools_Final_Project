# *Video Link: https://cmu.box.com/s/8mgpujfg59x5ory8w8dg12z1wqv5sl3r*

# We choose Option 1 as our course project.

## &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Rolian Tan &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Micah Baldonado


# Instructions:
1. We assemble all the functions, running process and output process in the 'final_sys_tools_project_code.ipynb' file, you can run it directly on the windows system.
2. the 'final_sys_tools_project_code-cloud.ipynb' is our results while runing on the cloud. 
3. Here are some path you need to modify:
    1. jdbc_driver_path = " " --- your jdbc .jar file
    2. dataset_folder_path  = " " --- your .csv data folder files
    3. db_properties['username']=" " --- postgres username
    4. db_properties['password']=" " --- passpord
    5. db_properties['url']= " " --- the url to link to the postgres
    6. db_properties['table']= " " --- the table name you want to write to
4. Make sure you have installed every libraries we imported. you can use 'pip install LIBRARY NAME' to install missing ones.
5. Finally, run the entire jupyter notebook code block by block, you could reimplement our results
6. If you have trouble doing this, you can refer to our demo video or create issues in this github repository. 

# Task 1
## Feature Description:

- `id`: Identifier combined by `sofifa_id` and `year`, unique (text)
- `sofifa_id`: Fifa player identifier (numeric)
- `player_url`: URL to the player's profile (text)
- `short_name`: Short name of the player (text)
- `long_name`: Full name of the player (text)
- `player_positions`: Positions the player can play (multiple positions, separated by commas) (text)
- `overall`: Overall player rating, 0-100 (numeric)
- `potential`: Potential player rating, 0-100 (numeric)
- `value_eur`: Market value of the player, Euros (numeric)
- `wage_eur`: Weekly wage of the player, Euros (numeric)
- `age`: Age of the player (numeric)
- `dob`: Date of birth of the player (date, yyyy-mm-dd)
- `height_cm`: Height of the player, centimeters (numeric)
- `weight_kg`: Weight of the player, kilograms (numeric)
- `club_team_id`: Club identifier, unique (numeric)
- `club_name`: Name of the club the player belongs to (text)
- `league_name`: Name of the league the club belongs to (text)
- `league_level`: Level of the league (numeric)
- `club_position`: Position the player plays in the club (text)
- `club_jersey_number`: Jersey number of the player (numeric)
- `club_loaned_from`: Name of the club the player is loaned from (text)
- `club_joined`: Date the player joined the club (date, yyyy-mm-dd)
- `club_contract_valid_until`: Year the player's contract is end (numeric)
- `nationality_id`: Nationality identifier, unique (numeric)
- `nationality_name`: Name of the player's nationality (text)
- `nation_team_id`: National team identifier, unique (numeric)
- `nation_position`: Position the player plays in the national team (text)
- `nation_jersey_number`: Jersey number of the player in the national team (numeric)
- `preferred_foot`: Player's preferred foot (text)
- `weak_foot`: Rating for the player's weaker foot ability, 1-5 (numeric)
- `skill_moves`: Rating for the player's skill moves, 1-5 (numeric)
- `international_reputation`: Rating for the player's international reputation, 1-5 (numeric)
- `work_rate`: Player's work rate, format (attack/defense) (text)
- `body_type`: Player's body type description (text)
- `real_face`: Whether the game has the player's real face data, 'Yes' or 'No' (text)
- `release_clause_eur`: Release clause value of the player, Euros (numeric)
- `player_tags`: Player's special skills (text)
- `player_traits`: The player's traits on the field (text)
- `pace`, `shooting`, `passing`, `dribbling`, `defending`: Rating for the player's [pace, shooting, passing, dribbling, defending], 0-100 (numeric)
- `physic`: Rating for the player's physical strength, 0-100 (numeric)
  
- `attacking_crossing`, `attacking_finishing`, `attacking_heading_accuracy`, `attacking_short_passing`,`attacking_volleys` : Rating for the player's attacking ability, from the aspects of [crossing, finishing, heading_accuracy, short_passing, volleys], 0-100 (numeric)

- `skill_dribbling`, `skill_curve`, `skill_fk_accuracy`, `skill_long_passing`, `skill_ball_control`: Rating for the player's ball skill from aspects of [dribbling, curve passing, free-kick, long passing, ball control], 0-100 (numeric)

- `movement_acceleration`, `movement_sprint_speed`, `movement_agility`, `movement_reactions`, `movement_balance`: Rating for the player's movement anilities from aspects of [acceleration, sprint speed, agility, reactions, balance], 0-100 (numeric)

- `power_shot_power`, `power_jumping`, `power_stamina`, `power_strength`, `power_long_shots`: Rating for the player's power from aspects of [shot, jumping, stamina, physical strength, long shots], 0-100 (numeric)

- `mentality_aggression`, `mentality_interceptions`, `mentality_positioning`, `mentality_vision`, `mentality_penalties`, `mentality_composure`: Rating for the player's mentality realated to aspects of [aggression, interceptions, positioning, vision, penalty-taking, composure]

- `defending_marking_awareness`: Rating for the player's marking awareness, 0-100 (numeric)
- `defending_standing_tackle`: Rating for the player's standing tackle ability, 0-100 (numeric)
- `defending_sliding_tackle`: Rating for the player's sliding tackle ability, 0-100 (numeric)


## Reasons to use PostgreSQL rather than NoSQL database:
1. Complex Queries and Aggregation
PostgreSQL supports efficient joins and aggregations, allowing to easily query across tables (e.g finding clubs by years, calculating averages). NoSQL databases often require more complex operations for similar queries.
2. Data Integrity Validation
With ACID compliance and support for constraints, PostgreSQL ensures accurate and consistent data (e.g valid age ranges or player ratings), which is harder to enforce in most NoSQL systems.
3. Feature-Related Dataset
Since this dataset contains player bio information, player ability information and club information, so PostgreSQL has more potential to create multiple sub-tables by using unique foreign keys. However, the NoSQL is a non-relation method.

# Task 3 - Machine Leaning
# Attention: Due to the different experiemnt results on local machine and on the cloud, we will use the local outputs as refernece. 
## Since this is a regression task so we choose regressors
### Pyspark model:
1. we use two mainstream regressor: DecisionTree Regressor, RandomForest Regressor
2. `DecisionTree`: Simplicity and ease of interpretability, making it suitable for quick insights.
3. `RandomForest`: Robustness and ability to reduce overfitting through ensemble learning, providing more reliable insights.
### Pyspark Parameter Tuning:
We use Paramgrid to find the best pairs of parameters as the tuning method. 
1. `DecisionTree`: mean absolute error (MAE) of 0.1869
2. `RandomForest`: a slightly higher MAE of 0.2003, may because of the limitation of the hyperparmeter settings or the performance threshold of the tree structure regressors on this large dataset.  
Here are the explaination of the hyper parametes:
1. `maxDepth`: Controls the depth of the trees. A higher maxDepth enables the model to capture more complex patterns, but it can lead to overfitting if set too high. For both models, tuning maxDepth was essential to balance model complexity and generalization.
2. `numTrees`: Specific to the Random Forest model, numTrees defines how many decision trees are used. More trees generally lead to better performance, but with diminishing returns and increased computational cost.
### Pytorch model:
1. We create two neural networks to compare: shallow NN, deep NN  
2. `SimpleNN`: Testing the model’s performance with fewer parameters and a simpler architecture. Leading to faster training times and less risk of overfitting on smaller datasets.  
3. `DeepNN`: More complex architecture with three hidden layers, which is designed to capture more intricate patterns or high-level features in the data.  
### Pytorch Parameter Tuning:  
  1. `Batch Size (bs)`: this minibatch could excellerate the training process and won't exceed the computation resource limits  
  2. `Learning Rate (lr)`: determines the pace of gradients updating, when lr goes from 1e-2 to 1e-3, with epochs fixed, it brings a 28% MSE drop for simpleNN (from 0.251 to 0.178) and a 33% MSE drop for deepNN (from 0.153 to 0.107)  
  3. `Epochs`: higher epochs will provide more times of training to make sure the model converges, when lr=1e-5, incresing the epochs from 20 to 40 brings no MSE drop for both simpleNN (0.251->0.297) and deepNN(0.153->0.161), which means the models are already converged.   
  4. `model_type`: this decides which model to use  
  compare with `simpleNN` and `deepNN`, we will find that: when the hyperparameter are the same, the deepNN is more complicated to learn more   features compared with simpleNN, so the deepNN always reach better MSE scores. 
    
