Feature Description:

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
work_rate: Player's work rate, combining attack and defense effort (text)
body_type: Player's body type description (text)
real_face: Whether the player's real face is represented in the game, 'Yes' or 'No' (text)
release_clause_eur: Release clause value of the player in Euros, if applicable (numeric)
player_tags: Tags describing the player's special skills or abilities (text)
player_traits: Traits representing the player's behavior on the field (text)
pace: Rating for the player's pace, 0-100 (numeric)
shooting: Rating for the player's shooting ability, 0-100 (numeric)
passing: Rating for the player's passing ability, 0-100 (numeric)
dribbling: Rating for the player's dribbling ability, 0-100 (numeric)
defending: Rating for the player's defending ability, 0-100 (numeric)
physic: Rating for the player's physical strength, 0-100 (numeric)
attacking_crossing: Rating for the player's crossing ability, 0-100 (numeric)
attacking_finishing: Rating for the player's finishing ability, 0-100 (numeric)
attacking_heading_accuracy: Rating for the player's heading accuracy, 0-100 (numeric)
attacking_short_passing: Rating for the player's short passing ability, 0-100 (numeric)
attacking_volleys: Rating for the player's volleying ability, 0-100 (numeric)
skill_dribbling: Rating for the player's dribbling skill, 0-100 (numeric)
skill_curve: Rating for the player's curve ability, 0-100 (numeric)
skill_fk_accuracy: Rating for the player's free-kick accuracy, 0-100 (numeric)
skill_long_passing: Rating for the player's long passing ability, 0-100 (numeric)
skill_ball_control: Rating for the player's ball control ability, 0-100 (numeric)
movement_acceleration: Rating for the player's acceleration, 0-100 (numeric)
movement_sprint_speed: Rating for the player's sprint speed, 0-100 (numeric)
movement_agility: Rating for the player's agility, 0-100 (numeric)
movement_reactions: Rating for the player's reactions, 0-100 (numeric)
movement_balance: Rating for the player's balance, 0-100 (numeric)
power_shot_power: Rating for the player's shot power, 0-100 (numeric)
power_jumping: Rating for the player's jumping ability, 0-100 (numeric)
power_stamina: Rating for the player's stamina, 0-100 (numeric)
power_strength: Rating for the player's physical strength, 0-100 (numeric)
power_long_shots: Rating for the player's long shots, 0-100 (numeric)
mentality_aggression: Rating for the player's aggression, 0-100 (numeric)
mentality_interceptions: Rating for the player's interceptions, 0-100 (numeric)
mentality_positioning: Rating for the player's positioning, 0-100 (numeric)
mentality_vision: Rating for the player's vision, 0-100 (numeric)
mentality_penalties: Rating for the player's penalty-taking ability, 0-100 (numeric)
mentality_composure: Rating for the player's composure, 0-100 (numeric)
defending_marking_awareness: Rating for the player's marking awareness, 0-100 (numeric)
defending_standing_tackle: Rating for the player's standing tackle ability, 0-100 (numeric)
defending_sliding_tackle: Rating for the player's sliding tackle ability, 0-100 (numeric)










Reasons to use PostgreSQL rather than NoSQL database:
1. Complex Queries and Aggregation
PostgreSQL supports efficient joins and aggregations, allowing to easily query across tables (e.g finding clubs by years, calculating averages). NoSQL databases often require more complex operations for similar queries.
2. Data Integrity Validation
With ACID compliance and support for constraints, PostgreSQL ensures accurate and consistent data (e.g valid age ranges or player ratings), which is harder to enforce in most NoSQL systems.
3. Feature-Related Dataset
Since this dataset contains player bio information, player ability information and club information, so PostgreSQL has more potential to create multiple sub-tables by using unique foreign keys. However, the NoSQL is a non-relation method.
