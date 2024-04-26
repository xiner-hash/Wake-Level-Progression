## Description

Welcome to the Aqualab Level Progression Analysis, which examines the influence of prior job completions and other factors on the likelihood of completing future target jobs in the educational game Wake.

This user guide will walk you through the key functionalities of the program.

### Session I. Pre-process log data

This section converts the raw .tsv files downloaded from (https://opengamedata.fielddaylab.wisc.edu/gamedata.php?game=AQUALAB) for each month and processes them into a format suitable for subsequent analysis.


* Please skip this step if all .tsv files have already been converted to .csv format for chi-square tests/regression.
* Please ensure that all the .tsv files are located in the current working directory.

### Session II. Pre-process log data

This section consolidates all the .csv files into one. We then select all jobs within the game for subsequent analysis, excluding only the introductory level where players cannot quit, as well as those rarely reached (less than 30 students who complted it or fewer than 30 students who quit it) for Sections III and IV.

* Please make sure that the processed data is in the current working directory.

### Session III. Chi-square test

For each target job identified in Section II, this section iterates through all previously played levels before reaching this target job. It calculates the number of players who have completed each previous level and those who have not. Then, it conducts the chi-square test to investigate the relationship between players' decisions to switch off this target level and their completion status of any previous levels they may have accepted before encountering these target jobs. At the end of the session, the program sorts all previous levels based on chi-square statistics from high to low for each target job. It retains only a customizable number, n, of previous jobs. 

* Please make sure that the .txt file containing all job difficulty parameters is in the current working directory.
* Level B (LevelB) is customizable.
* Criteria for selecting Level As is customizable (threshold_yes, threshold_no).


### Session IV. Construct regression table


For all target jobs and their corresponding n number of previous job identified in Section III, we conduct a regression analysis to understand how various factors (further details provided in the code), both individually and collectively, impact the likelihood of a player switching the target jobs.

* For each target job, this section only consider the n number (defined in Session II) of previous jobs prior to the target job with the highest chi-square coefficient to compile the regression table.



