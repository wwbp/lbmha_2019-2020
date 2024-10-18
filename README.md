# Language Based Mental Health Assessments for 2019 and 2020 by County x Week 
v1.0 data

Temporal measurements of well-being as described in [Mangalik et al., 2024](https://www.nature.com/articles/s41746-024-01100-0).

See the code used that produces and analyzes the data in [wwbp/robust_spatiotemp](https://github.com/wwbp/robust_spatiotemp)

Mangalik, S., Eichstaedt, J.C., Giorgi, S., Mun, J., Ahmed, F., Gill, G., V. Ganesan, A., Subrahmanya, S., Soni, N., Clouston, S.A. and Schwartz, H.A. (2024). [Robust language-based mental health assessments in time and space through social media](https://www.nature.com/articles/s41746-024-01100-0). <i>NPJ Digital Medicine, 7(1),</i> 109.

## `/data`
Contains the generated 2020 mental health scores generated in _Robust language-based mental health assessments in time and space through social media_. These scores control for 2019 findings.
- `lbmha_yw_cnty.csv`: depression and anxiety scores for 2020 measured from Twitter data. This data controls for the 2019 data, so 2019 is not included in this file.
  - `id` unique row identifier [0, 1, 2, ...]
  - `yearweek_cnty` concatenation of the year, week number (ISO format), and county (fips code)
feat: either DEP_SCORE (depression) or ANX_SCORE (anxiety), derived from an adapted lexicon [2019_01:36091, 2020_52:22069]
  - `score_category` Depression (DEP_SCORE) or Anxiety (ANX_SCORE)
  - `n_lexwords` total count of words signalling the feat from all users in that yearweek_cnty
  - `score` weighted average of scores signalling the feat from all users in that yearweek_cnty, weights are meant to better align with actual demographics of population and only occurs when sufficient users are present
  - `score_unweighted` average of scores signalling the feat from all users in that yearweek_cnty are present
  - `score_std` standard deviation of scores signalling the feat from all users in that yearweek_cnty are present
  - `moderate_reliability_criteria` whether the score is considered reliable based on the criteria of UT 50 [1 if true; 0 if false]
  - `high_reliability_criteria` whether the score is considered reliable based on the criteria of UT 200 [1 if true; 0 if false]
  - `n_users` number of unique users measured in that yearweek_cnty
  - `cnty` redundant column for easy sorting
  - `county_name` expanded name of the county
  - `state_abbr` standard state 2-letter abbreviation of state
  - `date` The Wednesday of the ISO week
  - `date_range` Monday-Sunday of the ISO weeks
  - `yearweek` redundant column for easy sorting
- `lbmha_yw_cnty_undifferenced.csv` depression and anxiety scores for 2019 and 2020 measured from Twitter data. This data does not include any correction for other years. The data format is shared from `lbmha_yw_cnty.csv`.
