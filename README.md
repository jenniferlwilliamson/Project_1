<div style="background-color:dodgerblue;color:white;padding:20px;font-size:16px;font-family:'Arial'">
  <h1>Reducing the Rate of Standardized Testing in the US</h1>
</div>

---
# File Structure

---

### Files:
* README.md - describes file
* presentation.pdf - includes a pdf file of the presentation

### Folders:
* code - folder includes files for running the analysis
   * starter-code - describes the detailed analysis

* data - folder includes data used for the analysis
   * original:
     * see list in data sources below
   
   * output:
     * sat_and_act_2018_participation
     * college_info_summary.csv
     * gen_and_admit_info_summary.csv
     * private_4yr_schools_allnums.csv
     * public_4yr_schools_allnums.csv
 
* visuals:
   * screenshots used for README file
 
---
# Background

---
I focused on an audience that would want to reduce the prevalence of standardized testing throughout the US.

Several states require students to take either the SAT’s or ACT’s as part of graduation requirements per 2020 blog.
* https://blog.prepscholar.com/which-states-require-the-sat
* https://blog.prepscholar.com/which-states-require-the-act-full-list-and-advice

This has especially increased since 2016 change of SAT’s 
* https://www.washingtonpost.com/education/2018/10/23/sat-reclaims-title-most-widely-used-college-admission-test/

However, while there's comparison between tests, I was curious if some states had higher rates of testing that correlated to whether the large public schools in their states required tests. Based on research, in-state schools generally have at least 40% of their enrollment from in-state residents and usually even more attendance from in-state residents, so it makes sense that they would affect testing norms in the state:
* https://www.usatoday.com/in-depth/news/investigations/2019/08/19/college-recruiting-enrollment-tuition-in-state/1628566001/

* https://www.usatoday.com/story/news/investigations/2019/08/19/despite-trends-some-public-colleges-fight-to-keep-state-students/1828246001/

* https://www.usatoday.com/pages/interactives/colleges-out-of-state-enrollment-database/

In addition, from my anecdotal experience I know most people applied to at least one of the local public state schools when applying to college.

---
# Problem Statement

---

While mandatory statewide testing occurs in many states, several states have high participation rates that are not in this group.  Public colleges and universities generally have a high percentage of students from in-state, so they could be drivers of testing requirements.

### Do testing requirements of private or public 4-year post-secondary schools affect the testing requirements, so that we could target them instead of state education boards?

---
# Data Sources

---

### Given by GA
 * sat_2018.csv - sat data for 2018
 * act_2018.csv - act data for 2018

### Imported three data sets related to higher education:

* Source for datasets accessed online: https://nces.ed.gov/ipeds/datacenter/DataFiles.aspx?goToReportId=7
    
* Help information is here: https://nces.ed.gov/Ipeds/Help/View/101

**2018 data on Institutional Characteristics** 

![](https://git.generalassemb.ly/jenni5/project_1/blob/master/Visuals/ScreenShotHD.png)

* hd2018.csv - dataset for institutional characteristics
* hd2018.xlsx - data dictionary for institutional characteristics

**2018 data on Admissions and Test Scores**

![](https://git.generalassemb.ly/jenni5/project_1/blob/master/Visuals/ScreenShotADM.png)

* folder ADM2018
   * adm2018_rv.csv - dataset for admissions and test scores
   * adm2018.xlsx - data dictionary for admissions and test scores

**2018 data on makeup of first-year students in the fall**

![](https://git.generalassemb.ly/jenni5/project_1/blob/master/Visuals/ScreenShotEF.png)

* ef2018c.csv - dataset that includes state of residence for first year students
* ef2018c.xlsx - data dictionary that includes state of residence for first year students

---
# Data Dictionary

---

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|sat_and_act_2018_participation|Abbreviation of States| 
|act_participation|float|act_2018|Percentage of Students who took the act exam in a given state| 
|sat_participation|float|sat_2018|Percentage of Students who took the act exam in a given state| 
|unit_id|int|hd_2018|id code associated with a given university or school| 
|years_and_puborpriv|int|hd_2018|Whether the institution is 4-yr, 2-yr, or less, and whether it is public or private| 
|test_scores_required|int|adm_2018|How the institution address tests| 
|state_of_residence_when_admitted|int|ef2018c|Gives the state of residence for first year students when admitted for a given institution| 
|number_studnets_in_state|int|ef2018c|Gives the number of students in a state for first year students when admitted for a given institution| 

---
# Analysis

---

### School Requirements for Testing
* Most public schools require tests.
* Wide range of variability in testing requirements for private schools.
![](https://git.generalassemb.ly/jenni5/project_1/blob/master/Visuals/BoxPlot.png)

### School Requirements for Testing vs Students Taking Test
* Minimal correlation between private school requirements and whether students take tests.
* Some correlation between public school requirements and whether students take tests.
![](https://git.generalassemb.ly/jenni5/project_1/blob/master/Visuals/CorrelationPlot.png)

![](https://git.generalassemb.ly/jenni5/project_1/blob/master/Visuals/ScatterPlot.png)

### Limitation of Data
* Did not find source that combines SAT and ACT data for student test takers, so I had to make assumptions to calculate the total number of test takers.
* There's a negative correlation between the two and many states have a dominant test that most students take.  So I assumed the higher value of test taking percent as the total test takers for a given state (so where states have more of a mix in test this undercounts the total percent of test takers).
![](https://git.generalassemb.ly/jenni5/project_1/blob/master/Visuals/ScatterPlot_SAT_vs_ACT.png)

![](https://git.generalassemb.ly/jenni5/project_1/blob/master/Visuals/SATvsACT_barchart.png)

---
# Conclusions/Recommendations

---

### Conclusion
* Based on the limited correlation between public school testing requirements and whether students take tests - public schools could be contributing to students taking tests.

### Recommendations
* Consider targeting public universities/colleges to remove their testing requirements in states without mandatory testing requirements.
*  Research alternative relationships between testing and states.

![](https://git.generalassemb.ly/jenni5/project_1/blob/master/Visuals/Map_of_US_Percent_take_test_public_school.png)

