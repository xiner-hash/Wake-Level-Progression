## Description

Welcome to the Aqualab Level Progression Analysis, which examines the influence of prior job completions and other factors on the likelihood of completing future target jobs in the educational game Wake.

This user guide will walk you through the key functionalities of the program.

### Session I. Pre-process log data

This section converts the raw .tsv files downloaded from (https://opengamedata.fielddaylab.wisc.edu/gamedata.php?game=AQUALAB) for each month and processes them into a format suitable for subsequent analysis.


* Please skip this step if all .tsv files have already been converted to .csv format for chi-square tests/regression.
* Please ensure that all the .tsv files are located in the current working directory.


### Session II. Chi-square test

This section combines all the .csv files into one. Then, based on the specified target level (LevelB), it iterates through all previously played levels before the target level. It counts the number of players who have completed each previous level and those who have not. Next, it filters all the previous levels based on specified criteria (e.g., threshold_yes, threshold_no). It uses the remaining previous levels to conduct the chi-square test to investigate the relationship between players' decisions to switch off the target level and their completion status of any previous level they may have accepted before those target jobs.


* Please make sure that the .txt file containing all job difficulty parameters is in the current working directory.
* Level B (LevelB) is customizable.
* Criteria for selecting Level As is customizable (threshold_yes, threshold_no).
* At the end of the session, the program sorts all previous levels based on chi-square statistics from high to low. It retains only a customizable number, n, of previous jobs for Session III.


### Session III. Construct regression table


In this section, we conduct a regression analysis to understand how various factors (further details provided in the code), both individually and collectively, impact the likelihood of a player switching jobs. 

* This section only consider the n number (defined in Session II) of previous jobs prior to the target job with the highest chi-square coefficient to compile the regression table.



