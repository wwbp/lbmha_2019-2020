# lbmha_2019-2020
Language Based Mental Health Assessments for 2019 and 2020 by County-Week 

## `/data`
Contains the generated 2019 and 2020 mental health scores generated in _Robust language-based mental health assessments in time and space through social media_.
- `lbmha19to20.yw_cnty.csv`: scores for 2019 and 2020 measured directly from the Twitter data (does not include the 2019 adjustment)
  - `yearweek_cnty` [unique]: concatenation of the year, week number (ISO format), and county (fips code)
feat: either DEP_SCORE (depression) or ANX_SCORE (anxiety), derived from an adapted lexicon
  - `feat` Depression (DEP_SCORE) or Anxiety (ANX_SCORE)
  - `sum_n_lexwords` total count of words signalling the feat from all users in that yearweek_cnty
  - `wavg_score` weighted average of scores signalling the feat from all users in that yearweek_cnty, weights are meant to better align with actual demographics of population and only occurs when sufficient users are present
  - `avg_score` average of scores signalling the feat from all users in that yearweek_cnty are present
  - `std_score` standard deviation of scores signalling the feat from all users in that yearweek_cnty are present
  - `n_users` number of unique users measured in that yearweek_cnty
  - `cnty` redundant column for easy sorting
  - `yearweek` redundant column for easy sorting
  - `county_name` expanded name of the county
  - `state_abbr` standard state 2-letter abbreviation of state
  - `date` center date of the yearweek (Wednesday)
  - `date_range` Monday-Sunday of the ISO week