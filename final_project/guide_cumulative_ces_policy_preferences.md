# Guide to the Cumulative CES Policy Preferences 

Angelo Dagonel*

Guide last updated: 2023-01-18

Dagonel, Angelo, 2023, "Cumulative CES Policy Preferences", doi:10. 7910/DVN/OSXDQO, Harvard Dataverse, V3.

Each year, the Cooperative Election Study (CES) ${ }^{1}$ asks respondents about their preferences on issues like abortion, immigration, the environment and more. However, variable names for question items often change from year to year.

The Cumulative CES Policy Preferences data set compiles various policy preference question items from CES respondents over time. This represents an effort to track, rename, recode, and append together 557,456 responses across 54 policy preference question items from 16 individual CES survey data sets, ranging from 2006 to 2021.

The resulting time series is available as a downloadable data set from the Harvard Dataverse. This data set can be combined with the geographic, demographic, and political characteristics of each respondent from the Cumulative CES Common Content by merging on the case_id and year variables.

Question items are categorized into nine issue area categories. Variable names include the issue category, and a suffix related to the specific question. Variable labels contain a condensed, one sentence description of the policy that respondents are being asked if they support or oppose. For each question item, this guide provides details on the years where the item appears, frequency tables for response values, and it's original, year-specific variable name and question wording.

[^0]
## 1 Question availability by year

| Common variable name | 2006 | 2007 | 2008 | 2009 | 2010 | 2011 | 2012 | 2013 | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| case_id | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| Abortion |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| abortion_scale | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  |  |  |  |  |  |  |
| abortion_always |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| abortion_conditional |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| abortion_20weeks |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| abortion_coverage |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ |  |
| abortion_expenditures |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |
| abortion_prohibition |  |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| Environment |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| enviro_scale | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  |  |  |  |  |  |  |  |
| enviro_carbon |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| enviro_mpg_raise |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ |
| enviro_renewable |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| enviro_airwateracts |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| enviro_vs_jobs | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ |  | $\checkmark$ | $\checkmark$ |  |  |  |  |  |  |  |  |
| Guns - |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| guns_scale |  |  |  |  | $\checkmark$ |  | $\checkmark$ |  |  |  |  |  |  |  |  |  |
| guns_bgchecks |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ |
| guns_names |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  | $\checkmark$ |  |
| guns_assaultban |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| guns_permits |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| Health Care |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| healthcare_aca |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| healthcare_acamandate |  |  |  |  |  |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| healthcare_medicare |  |  |  |  |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| healthcare_medicareage |  |  |  |  |  |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ |  |
| Immigration |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| immig_legalize |  | $\checkmark$ |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| immig_border |  | $\checkmark$ |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| immig_police |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  | $\checkmark$ |  |  |  |  |
| immig_employer |  | $\checkmark$ |  |  | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  |  |  |
| immig_services |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ |  |  |  |  |  |  |  |  |
| immig_deport |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  |  |  |
| immig_report |  |  |  |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| immig_reduce |  |  |  |  |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |
| immig_wall |  |  |  |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ |
| Military |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| military_oil | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  |  | $\checkmark$ |  |
| military_terroristcamp | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  |  | $\checkmark$ |  |
| military_genocide | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  |  | $\checkmark$ |  |
| military_democracy | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  |  | $\checkmark$ |  |
| military_protectallies | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  |  | $\checkmark$ |  |
| military_helpun | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  |  | $\checkmark$ |  |
| Spending |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| spending_welfare |  |  |  |  |  |  |  |  | $\checkmark$ |  | $\checkmark$ |  | $\checkmark$ |  | $\checkmark$ |  |
| spending_healthcare |  |  |  |  |  |  |  |  | $\checkmark$ |  | $\checkmark$ |  | $\checkmark$ |  | $\checkmark$ |  |
| spending_education |  |  |  |  |  |  |  |  | $\checkmark$ |  | $\checkmark$ |  | $\checkmark$ |  | $\checkmark$ |  |
| spending_police |  |  |  |  |  |  |  |  | $\checkmark$ |  | $\checkmark$ |  | $\checkmark$ |  | $\checkmark$ |  |
| spending_infrastructure |  |  |  |  |  |  |  |  | $\checkmark$ |  | $\checkmark$ |  | $\checkmark$ |  | $\checkmark$ |  |
| spending_vs_tax | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  | $\checkmark$ |  |
| spending_cuts_most | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ |  |  |  |  |
| spending_cuts_least | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ |  |  |  |  |
| Trade |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| trade_china |  |  |  |  |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| trade_canmex_except |  |  |  |  |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |
| trade_canmex_include |  |  |  |  |  |  |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |
| Other |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| gaymarriage_scale | $\checkmark$ | $\checkmark$ |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| gaymarriage_ban |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  |  |  |  |  |  |  |  |  |
| gaymarriage_legalize |  |  |  |  |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  |  |  |  |
| affirmativeaction_scale | $\checkmark$ | $\checkmark$ |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| affirmativeaction |  |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  |  |  |  |  |  |
| incometax_vs_salestax | $\checkmark$ | $\checkmark$ | $\checkmark$ |  | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ | $\checkmark$ |  |  | $\checkmark$ |  |

## 2 Usage warnings

$R$ users are advised to download and use the .dta version of the data set, as the .tab version replaces informative value labels with numbers. To use .dta files in R, install and load the package "haven" via the following lines of code: install.packages("haven"); library(haven).

Some question wording varies slightly across time, with more extreme changes warranting a note at the end of each question item's section. Further, some item response values are shortened and/or slightly re-worded from their original values out of convenience. When shortening and re-wording occurs, the original value wording is listed inside the item's respective question wording table.

Users of the Cumulative CES Policy Preferences dataset are encouraged to reference this guide to examine details on any interested question item before use. Users of previous versions of the guide should familiarize themselves with any relevant updates described in the section "Version updates".

## 3 Version updates

Updates and changes from the previous (V1) to current version of the data:

- Policy items from the 2020 Common Content were added, when applicable.
- Four policy items on immigration were added: immig_deport, immig_report, immig_reduce and immig_wall.
- Three policy items on trade policy were added.
- Three policy items on health care were added, and the item previously named repealaca was renamed to healthcare_aca.
- One correction was made with respect to immig_services in 2014. Previously, responses from immig_border were recorded as responses for immig_services in 2014. This error is corrected in the current version.
- One correction was made with respect to healthcare_aca, previously repealaca, in 2014. Previously, responses from repealaca in 2014 were re-coded and switched-i.e. responses of support coded as oppose, and vice versa-to match question wording in other years that asked about support for repealing the ACA. However, question wording in 2014 already asked about repealing the ACA. Thus, this update does not recode any responses for this question item, now named healthcare_aca.
- Previously, responses from gaymarriage were re-coded and switched from 2006 through 2011 to match question wording from 2012 onwards that asked about support for legalizing gay marriage, rather than the 2016 through 2011 question wording asking about support for banning gay marriage. Instead, this update separates responses from 2006 through 2011 into gaymarriage_ban, and responses from 2012 onwards into gaymarriage_legalize.
- Previously, responses from enviro_mpg were re-coded and switched in 2018 to match question wording from all previous years that asked about support for raising fuel efficiency standards, rather than the 2018 and 2020 wording asking about support for lowering gay marriage. Instead, this update separates responses from 2018 and 2020 into enviro_mpg_lower, and responses from earlier years into enviro_mpg_raise.


## 4 Merging instructions

Users who have separately downloaded the Cumulative Common Content and Policy Preferences data sets can merge them using the year and case_id that are common between both. For users who have not downloaded the two data sets, the code chunk below can be run in R to produce a ready-to-use dataframe.

```
#Install and load necessary packages
install.packages(c("tidyverse", "haven", "dataverse"))
library(tidyverse, haven, dataverse)
#Load Cumulative Common content
common <- get_dataframe_by_name(
    filename = "cumulative_2006-2021.dta",
    dataset = "10.7910/DVN/II2DB6",
    server = "dataverse.harvard.edu",
    original = TRUE,
    .f = haven::read_dta)
#Load Cumulative Policy Preferences
preferences <- get_dataframe_by_name(
    filename = "cumulative_cces_policy_preferences.tab",
    dataset = "10.7910/DVN/OSXDQO",
    server = "dataverse.harvard.edu",
    original = TRUE,
    .f = haven::read_dta)
```

\#Merge common content to policy preferences ces <- inner_join(common, preferences)

## Contents

1 Question availability by year ..... 2
2 Usage warnings ..... 3
3 Version updates ..... 3
4 Merging instructions ..... 4
5 Question items ..... 7
5.1 Abortion ..... 7
5.1.1 abortion_scale ..... 7
5.1.2 abortion_always ..... 9
5.1.3 abortion_conditional ..... 9
5.1.4 abortion_20weeks ..... 10
5.1.5 abortion_coverage ..... 11
5.1.6 abortion_expenditures ..... 12
5.1.7 abortion_prohibition ..... 13
5.2 Environment ..... 15
5.2.1 enviro_scale ..... 15
5.2.2 enviro carbon ..... 16
5.2.3 enviro_mpg_raise ..... 17
5.2.4 enviro_renewable ..... 18
5.2.5 enviro_airwateracts ..... 20
5.2.6 enviro_vs_jobs ..... 21
5.3 Guns ..... 23
5.3.1 guns_scale ..... 23
5.3.2 guns_bgchecks ..... 23
5.3.3 guns_names ..... 24
5.3.4 guns_assaultban ..... 25
5.3.5 guns_permits ..... 26
5.4 Health care ..... 28
5.4.1 healthcare_aca ..... 28
5.4.2 healthcare_acamandate ..... 29
5.4.3 healthcare_medicare ..... 30
5.4.4 healthcare_medicareage ..... 31
5.5 Immigration ..... 32
5.5.1 immig_legalize ..... 32
5.5.2 immig_border ..... 33
5.5.3 immig_police ..... 35
5.5.4 immig_employer ..... 36
5.5.5 immig_services ..... 37
5.5.6 immig_deport ..... 38
5.5.7 immig_report ..... 38
5.5.8 immig_reduce ..... 39
5.5.9 immig_wall ..... 40
5.6 Military ..... 42
5.6.1 military_oil ..... 42
5.6.2 military_terroristcamp ..... 43
5.6.3 military_genocide ..... 44
5.6.4 military_democracy ..... 46
5.6.5 military_protectallies ..... 47
5.6.6 military_helpun ..... 48
5.7 Spending ..... 51
5.7.1 spending_welfare ..... 51
5.7.2 spending_healthcare ..... 51
5.7.3 spending_education ..... 52
5.7.4 spending_police ..... 53
5.7.5 spending_infrastructure ..... 54
5.7.6 spending_vs_tax ..... 55
5.7.7 spending_cuts_most ..... 58
5.7.8 spending_cuts_least ..... 60
5.8 Trade ..... 63
5.8.1 trade_china ..... 63
5.8.2 trade_canmex_except ..... 63
5.8.3 trade_canmex_include ..... 64
5.9 Other ..... 65
5.9.1 gaymarriage_scale ..... 65
5.9.2 gaymarriage_ban ..... 65
5.9.3 gaymarriage_legalize ..... 66
5.9.4 affirmativeaction_scale ..... 66
5.9.5 affirmativeaction ..... 67
5.9.6 incometax_vs_salestax ..... 68

## 5 Question items

### 5.1 Abortion

### 5.1.1 abortion_scale

Support scale for access to abortion (1 = Never permit, 4 = Always allow)
Years in data: 2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013
Table 1: abortion_scale: Frequency table

| Response | 2006 | 2007 | 2008 | 2009 | 2010 | 2011 | 2012 | 2013 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Never permit | 3,485 | 862 | 4,796 | 1,793 | 6,623 | 2,448 | 5,684 | 1,873 |
| Permit in rape, incest cases | 9,128 | 2,260 | 9,533 | 4,402 | 15,641 | 5,399 | 14,146 | 4,169 |
| Permit in other cases | 5,474 | 1,461 | 4,710 | 1,866 | 8,135 | 2,887 | 7,174 | 2,272 |
| Always allow | 15,899 | 4,678 | 13,595 | 5,657 | 24,639 | 9,416 | 27,111 | 7,963 |

Year-specific variable names and wording
Table 2: abortion_scale: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2006 v3019 | There has been some discussion about abortion during <br> recent years. Which one of the opinions on this page best <br> agrees with your view on this issue? [1 By law, abortion <br> should never be permitted, 2 The law should permit <br> abortion only in case of rape, incest or when the woman's <br> life is in danger, 3 The law should permit abortion for <br> reasons other than rape, incest, or danger to the woman's <br> life, but only after the need for the abortion has been <br> clearly established, 4 By law, a woman should always be <br> able to obtain an abortion as a matter of personal choice] |  |
| 2007 CC06_V3019 | There has been some discussion about abortion during <br> recent years. Which one of the opinions on this page best <br> agrees with your view on this issue? [1 By law, abortion <br> should never be permitted, 2 The law should permit <br> abortion only in case of rape, incest, 3 The law should <br> permit abortion for reasons other than rape, 4 By law, a <br> woman should always be able to obtain an abortion] |  |

Table 2: abortion_scale: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2008 | cc310 | Which one of the opinions on this page best agrees with your view on abortion? [1 By law, abortion should never be permitted, 2 The law should permit abortion only in case of rape, incest or when the womans life is in danger, 3 The law should permit abortion for reasons other than rape, incest, or danger to the womans life, but only after the need for the abortion has been clearly established, 4 By law, a woman should always be able to obtain an abortion as a matter of personal choice] |
| 2009 | cc09_53 | Abortion |
| 2010 | cc324 | Which one of the opinions on this page best agrees with your view on abortion? [1 By law, abortion should never be permitted, 2 The law should permit abortion only in case of rape, incest or when the womans life is in danger, 3 The law should permit abortion for reasons other than rape, incest, or danger to the womans life, but only after the need for the abortion has been clearly established, 4 By law, a woman should always be able to obtain an abortion as a matter of personal choice] |
| 2011 | CC352 | Abortion |
| 2012 | CC324 | Which one of the opinions on this page best agrees with your view on abortion? [1 By law, abortion should never be permitted, 2 The law should permit abortion only in case of rape, incest or when the womans life is in danger, 3 The law should permit abortion for reasons other than rape, incest, or danger to the womans life, but only after the need for the abortion has been clearly established, 4 By law, a woman should always be able to obtain an abortion as a matter of personal choice] |
| 2013 | CC327 | Which one of the opinions on this page best agrees with your view on abortion? [1 By law, abortion should never bepermitted, 2 The law should permit abortion only incase of rape, incest or when thewoman's life is in danger, 3 The law should permit abortion forreasons other than rape, incest, ordanger to the woman's life, but onlyafter the need for the abortion has beenclearly established, 4 By law, a woman should always be ableto obtain an abortion as a matter ofpersonal choice] |

### 5.1.2 abortion_always

Always allow abortion
Years in data: 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021
Table 3: abortion_always: Frequency table

| Response | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 33,283 | 7,907 | 39,808 | 10,741 | 35,751 | 10,067 | 37,266 | 16,206 |
| Oppose | 22,395 | 6,200 | 24,730 | 7,444 | 24,150 | 7,841 | 23,716 | 9,494 |

Year-specific variable names and wording
Table 4: abortion_always: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2014 | CC14_323_1 | Do you support or oppose each of the following <br> proposals? . . Always allow a woman to obtain an <br> abortion as a matter of choice |
| 2015 CC15_322a | Do you support or oppose each of the following <br> proposals? Always allow a woman to obtain an abortion <br> as a matter of choice |  |
| 2016 CC16_332a | Do you support or oppose each of the following <br> proposals? Always allow a woman to obtain an abortion <br> as a matter of choice |  |
| 2017 CC17_332a | Do you support or oppose each of the following <br> proposals? Always allow a woman to obtain an abortion <br> as a matter of choice |  |
| 2018 CC18_321a | Do you support or oppose each of the following <br> proposals? Always allow a woman to obtain an abortion <br> as a matter of choice |  |
| 2019 CC19_321a | Always allow a woman to obtain an abortion as a matter of <br> choice |  |
| 2021 CC20_332a | Always allow a woman to obtain an abortion as a matter of <br> choice |  |

### 5.1.3 abortion_conditional

Allow abortion only under certain cases

Years in data: 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021
Table 5: abortion_conditional: Frequency table

| Response | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 26,198 | 6,247 | 29,616 | 7,729 | 24,315 | 7,572 | 25,899 | 10,697 |
| Oppose | 29,166 | 7,822 | 34,892 | 10,452 | 35,583 | 10,395 | 35,080 | 15,003 |

Year-specific variable names and wording
Table 6: abortion_conditional: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2014 CC14_323_2 | Do you support or oppose each of the following <br> proposals? . . Permit abortion only in cases of rape, <br> incest, or when the womans life is in danger |  |
| 2015 CC15_322b | Do you support or oppose each of the following <br> proposals? Permit abortion ONLY in case of rape, incest <br> or when the woman's life is in danger |  |
| 2016 CC16_332b | Do you support or oppose each of the following <br> proposals? Permit abortion only in case of rape, incest or <br> when the woman's life is in danger |  |
| 2017 CC17_332b | Do you support or oppose each of the following <br> proposals? Permit abortion only in case of rape, incest or <br> when the woman's life is in danger |  |
| 2018 CC18_321b | Do you support or oppose each of the following <br> proposals? Permit abortion ONLY in case of rape, incest <br> or when the woman's life is in danger |  |
| 2020 CC19_321b | Permit abortion ONLY in case of rape, incest or when the <br> woman's life is in danger |  |
| 2021 CC21_323b | Cermit abortion only in case of rape, incest or when the <br> Cermit abortion only in case of rape, incest or when the <br> woman's life is in dange |  |

### 5.1.4 abortion_20weeks

Ban abortion after 20 weeks
Years in data: 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021

Table 7: abortion_20weeks: Frequency table

| Response | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 37,103 | 9,676 | 39,057 | 11,675 | 38,280 | 10,910 | 33,943 | 13,668 |
| Oppose | 18,318 | 4,391 | 25,461 | 6,506 | 21,634 | 7,079 | 27,033 | 12,032 |

Year-specific variable names and wording
Table 8: abortion_20weeks: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2014 | CC14_323_3 | Do you support or oppose each of the following proposals? <br> - . . Prohibit abortions after the 20th week of pregnancy |
| 2015 CC15_322c | Do you support or oppose each of the following proposals? <br> Ban abortions after the 20th week of pregnancy |  |
| 2016 CC16_332c | Do you support or oppose each of the following proposals? <br> Prohibit all abortions after the 20th week of pregnancy |  |
| 2017 CC17_332c | Do you support or oppose each of the following proposals? <br> Ban abortions after the 20th week of pregnancy |  |
| 2018 CC18_321c | Do you support or oppose each of the following proposals? <br> Ban abortions after the 20th week of pregnancy |  |
| 2019 | CC19_321c | Ban abortions after the 20th week of pregnancy |
| 2020 CC20_332c | Prohibit all abortions after the 20th week of pregnancy |  |
| 2021 CC21_323d | Prohibit all abortions after the 20th week of pregnancy |  |

### 5.1.5 abortion_coverage

Employer coverage of abortion
Years in data: 2014, 2015, 2016, 2017, 2018, 2020
Table 9: abortion_coverage: Frequency table

| Response | 2014 | 2015 | 2016 | 2017 | 2018 | 2020 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 25,366 | 6,856 | 28,138 | 8,225 | 25,999 | 24,197 |
| Oppose | 30,273 | 7,246 | 36,400 | 9,960 | 33,938 | 36,783 |

Year-specific variable names and wording

Table 10: abortion_coverage: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2014 | CC14_323_4 | Do you support or oppose each of the following <br> proposals? . . Allow employers to decline coverage of <br> abortions in insurance plans |
| 2015 CC15_322d | Do you support or oppose each of the following <br> proposals? Allow employers to decline coverage of <br> abortions in insurance plans |  |
| 2016 CC16_332d | Do you support or oppose each of the following <br> proposals? Allow employers to decline coverage of <br> abortions in insurance plans |  |
| 2017 CC17_332d | Do you support or oppose each of the following <br> proposals? Allow employers to decline coverage of <br> abortions in insurance plans |  |
| 2018 | CC18_321d | Do you support or oppose each of the following <br> proposals? Allow employers to decline coverage of <br> abortions in insurance plans |

### 5.1.6 abortion_expenditures

Prohibit expenditures for abortion
Years in data: 2014, 2015, 2016, 2017, 2018, 2019, 2020
Table 11: abortion_expenditures: Frequency table

| Response | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 26,497 | 7,032 | 29,217 | 8,253 | 26,280 | 9,127 | 25,265 |
| Oppose | 28,968 | 7,027 | 35,321 | 9,929 | 33,651 | 8,863 | 35,717 |

Year-specific variable names and wording
Table 12: abortion_expenditures: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2014 | CC14_323_5 | Do you support or oppose each of the following <br> proposals? . . . Prohibit the expenditure of funds <br> authorized or appropriated by federal law for any abortion |

Table 12: abortion_expenditures: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2015 CC15_322e | Do you support or oppose each of the following <br> proposals? Prohibit the expenditure of funds authorized or <br> appropriated by federal law for any abortion. |  |
| 2016 CC16_332e | Do you support or oppose each of the following <br> proposals? Prohibit the expenditure of funds authorized or <br> appropriated by federal law for any abortion |  |
| 2017 CC17_332e | Do you support or oppose each of the following <br> proposals? Prohibit the expenditure of funds authorized or <br> appropriated by federal law for any abortion. |  |
| 2018 CC18_321e | Do you support or oppose each of the following <br> proposals? Prohibit the expenditure of funds authorized or <br> appropriated by federal law for any abortion. |  |
| 2020 | CC20_332e | Prohibit the expenditure of funds authorized or <br> appropriated by federal law for any abortion except to <br> save the life of the woman, or if the pregnancy arises from <br> incest or rape |

### 5.1.7 abortion_prohibition

Total prohibition of abortion
Years in data: 2015, 2016, 2017, 2018, 2019, 2020, 2021
Table 13: abortion_prohibition: Frequency table

| Response | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 2,597 | 10,144 | 3,128 | 9,224 | 3,350 | 9,743 | 4,536 |
| Oppose | 11,439 | 54,369 | 15,056 | 50,685 | 14,629 | 51,229 | 21,164 |

Year-specific variable names and wording
Table 14: abortion_prohibition: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2015 | CC15_322f | Do you support or oppose each of the following <br> proposals? Make abortions illegal in all circumstances. |

Table 14: abortion_prohibition: Year-specific wording (continued)

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2016 | CC16_332f | Do you support or oppose each of the following <br> proposals? Make abortions illegal in all circumstances |
| 2017 | CC17_332f | Do you support or oppose each of the following <br> proposals? Make abortion illegal in all circumstances. |
| 2018 | CC18_321f | Do you support or oppose each of the following <br> proposals? Make abortion illegal in all circumstances. |
| 2019 | CC19_321e | Make abortions illegal in all circumstances |
| 2020 | CC20_332f | Make abortions illegal in all circumstances |
| 2021 | CC21_323e | Make abortions illegal in all circumstances |

### 5.2 Environment

### 5.2.1 enviro_scale

Opposition scale to climate change ( $1=$ serious problem, $5=$ not occuring) Years in data: 2006, 2007, 2009, 2010, 2011, 2012

Table 15: enviro_scale: Frequency table

| Response | 2006 | 2007 | 2009 | 2010 | 2011 | 2012 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Immediate action | 5,694 | 2,210 | 3,073 | 15,409 | 5,785 | 14,764 |
| Some action | 4,291 | 1,486 | 4,205 | 13,853 | 5,779 | 16,378 |
| More research needed | 3,651 | 1,307 | 2,743 | 10,730 | 4,085 | 11,461 |
| No action necessary | 2,635 | 1,027 | 3,760 | 11,095 | 3,289 | 8,693 |
| Climate change not occurring | 0 | 0 | 0 | 4,201 | 1,212 | 3,075 |

Year-specific variable names and wording
Table 16: enviro_scale: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2006 | v2092 | From what you know about global climate change or <br> global warming, which one of the following statements <br> comes closest to your opinion? [1 Global climate change <br> has been established as a serious problem, and <br> immediate action is necessary. 2 There is enough <br> evidence that climate change is taking place and some <br> action should be taken. 3 We don't know enough about <br> global climate change, and more research is necessary <br> before we take any actions. 4 Concern about global <br> climate change is unwarranted.] |
| 2007 CC06_V2092From what you know about global climate change or <br> global warming, which one of the following statements <br> comes closest to your opinion? [1 Immediate action, 2 <br> Some action, 3 More research, 4 Concern unwarranted] <br> Global Warming |  |  |

Table 16: enviro_scale: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2010 | cc321 | From what you know about global climate change or global warming, which one of the following statements comes closest to your opinion? [1 Global climate change has been established as a serious problem, and immediate action is necessary. 2 here is enough evidence that climate change is taking place and some action should be taken. 3 We don't know enough about global climate change, and more research is necessary before taking any actions. 4 Concern about global climate change is exaggerated. No action is necessary. 5 Global climate change is not occurring; this is not a real issue.] |
| 2011 | CC350 | Climate |
| 2012 | CC321 | From what you know about global climate change or global warming, which one of the following statements comes closest to your opinion? [1 Global Climate change has been established as a serious problem, and immediate action is necessary. 2 There is enough evidence that climate change is taking place and some action should be taken. 3 We don't know enough about global climate change, and more research is necessary before we take any actions. 4 Concern about global climate chane is exaggerated. No action is necessary. 5 Global climate change is not occurring; this is not a real issue] |

Note: From 2010 onward, this question includes a fifth response option, 'Global climate change is not occurring'.

### 5.2.2 enviro_carbon

Allow EPA to regulate carbon dioxide emissions
Years in data: 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021
Table 17: enviro_carbon: Frequency table

| Response | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 38,653 | 8,982 | 43,932 | 12,309 | 33,678 | 12,135 | 42,643 | 16,866 |
| Oppose | 16,728 | 5,065 | 20,608 | 5,873 | 17,805 | 5,842 | 18,338 | 8,834 |

Year-specific variable names and wording

Table 18: enviro_carbon: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2014 CC14_326_1 | Do you support or oppose each of the following policies? <br> Environmental Protection Agency regulating carbon <br> emissions |  |
| 2015 CC15_323_1 | Do you support or oppose each of the following <br> proposals? Give Environmental Protection Agency power <br> to regulate Carbon Dioxide emissions |  |
| 2016 CC16_333a | Do you support or oppose each of the following <br> proposals? Give Environmental Protection Agency power <br> to regulate Carbon Dioxide emissions |  |
| 2017 CC17_333a | Do you support or oppose each of the following <br> proposals? Give Environmental Protection Agency power <br> to regulate Carbon Dioxide emissions. |  |
| 2018 CC18_415a | Do you support or oppose each of the following <br> proposals? Give the Environmental Protection Agency <br> power to regulate Carbon Dioxide emissions |  |
| 2020 CC19_340a | Give the Environmental Protection Agency power to <br> regulate Carbon Dioxide emissions |  |
| 2021 CC21_323a | Give the Environmental Protection Agency power to <br> regulate Carbon Dioxide emissions |  |

### 5.2.3 enviro_mpg_raise

Raise average fuel efficiency
Years in data: 2014, 2015, 2016, 2017, 2018, 2020, 2021
Table 19: enviro_mpg_raise: Frequency table

| Response | 2014 | 2015 | 2016 | 2017 | 2018 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 39,160 | 9,634 | 45,022 | 12,533 | 16,535 | 41,788 | 16,967 |
| Oppose | 16,279 | 4,430 | 19,522 | 5,654 | 34,966 | 19,187 | 8,733 |

Year-specific variable names and wording

Table 20: enviro_mpg_raise: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2014 CC14_326_2 | Raise required fuel efficiency for the average automobile <br> from 25 mpg to 35 mpg. |  |
| 2015 CC15_323_2 | Do you support or oppose each of the following <br> proposals? Raise required fuel efficiency for the average <br> automobile from 25 mpg to 35 mpg. |  |
| 2016 CC16_333b | Do you support or oppose each of the following <br> proposals? Raise required fuel efficiency for the average <br> automobile from 25 mpg to 35 mpg. |  |
| 2017 CC17_333b | Do you support or oppose each of the following <br> proposals? Raise required fuel efficiency for the average <br> automobile from 25 mpg to 35 mpg. |  |
| 2020 CC20_333d | Do you support or oppose each of the following <br> proposals? Lower the required fuel efficiency for the <br> average automobile from 35 mpg to 25 mpg. |  |
| Raise the average fuel efficiency for all cars and trucks in <br> the US from 40 miles per gallon to 54.5 miles per gallon by <br> 2025. |  |  |
| 2021 CC21_324d | Raise the average fuel efficiency for all cars and trucks in <br> the US from 40 miles per gallon to 54.5 miles per gallon by <br> 2025. |  |

Note: In 2018 alone, question wording includes 'lower the fuel efficiency’, instead of 'raise the fuel efficiency' like all the other years..

### 5.2.4 enviro_renewable

Require states use a minimum amount of renewable fuels
Years in data: 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021
Table 21: enviro_renewable: Frequency table

| Response | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 32,926 | 8,650 | 41,447 | 11,928 | 31,567 | 11,527 | 40,678 | 16,451 |
| Oppose | 22,577 | 5,427 | 23,087 | 6,262 | 19,957 | 6,454 | 20,308 | 9,249 |

Year-specific variable names and wording

Table 22: enviro_renewable: Year-specific wording

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2014 | CC14_326_3 | Do you support or oppose each of the following policies? Your state requiring the use of a minimum amount of renewable fuels (wind, solar, and hydroelectric) in the generation of electricity even if electricity prices increase a little? |
| 2015 | CC15_323_3 | Do you support or oppose each of the following proposals? Require that each state use a minimum amount of renewable fuels (wind, solar, and hydroelectric) in the generation of electricity even if electricity prices increase a little |
| 2016 | CC16_333c | Do you support or oppose each of the following proposals? Require that each state use a minimum amount of renewable fuels (wind, solar, and hydroelectric) in the generation of electricity even if electricity prices increase somewhat |
| 2017 | CC17_333c | Do you support or oppose each of the following proposals? Require that each state use a minimum amount of renewable fuels (wind, solar, and hydroelectric) in the generation of electricity even if the electricity prices increase a little. |
| 2018 | CC18_415c | Do you support or oppose each of the following proposals? Require that each state use a minimum amount of renewable fuels (wind, solar, and hydroelectric) in the generation of electricity even if electricity prices increase |
| 2019 | CC19_340b | Require that each state use a minimum amount of renewable fuels (wind, solar, and hydroelectric) in the generation of electricity even if electricity prices increase a little |
| 2020 | CC20_333b | Require that each state use a minimum amount of renewable fuels (wind, solar, and hydroelectric) in the generation of electricity even if electricity prices increase a little |
| 2021 | CC21_324b | Require that each state use a minimum amount of renewable fuels (wind, solar, and hydroelectric) in the generation of electricity even if electricity prices increase a little |

### 5.2.5 enviro_airwateracts

## Strengthen EPA enforcement of Clean Air and Water acts

Years in data: 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021
Table 23: enviro_airwateracts: Frequency table

| Response | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 27,064 | 7,588 | 37,672 | 11,412 | 30,106 | 11,097 | 38,946 | 16,094 |
| Oppose | 28,342 | 6,459 | 26,875 | 6,772 | 21,438 | 6,888 | 22,040 | 9,606 |

Year-specific variable names and wording
Table 24: enviro_airwateracts: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2014 | CC14_326_4 | Environmental Protection Agency strengthening <br> enforcement of the Clean Air Act even if it costs US jobs |
| 2015 CC15_323_4 | Do you support or oppose each of the following <br> proposals? Strengthen the Environmental Protection <br> Agency enforcement of the Clean Air Act and Clean Water <br> Act even if costs US jobs |  |
| 2016 CC16_333d | Do you support or oppose each of the following <br> proposals? Strengthen enforcement of the Clean Air Act <br> and Clean Water Act even if costs US jobs |  |
| 2017 CC17_333d | Do you support or oppose each of the following <br> proposals? Strengthen the Environmental Protection <br> Agency enforcement of the Clean Air Act and Clean Water <br> Act even if it costs U.S. jobs. |  |
| 2018 CC18_415d | Do you support or oppose each of the following <br> proposals? Strengthen the Environmental Protection <br> Agency enforcement of the Clean Air Act and Clean Water <br> Act even if it costs US jobs |  |
| 2020 CC20_333c | Ctrengthen the Environmental Protection Agency <br> enforcement of the Clean Air Act and Clean Water Act <br> even if it costs U.S. jobs <br> Strengthen the Environmental Protection Agency <br> enforcement of the Clean Air Act and Clean Water Act <br> even if it costs U.S. jobs |  |
| 2021 CC21_324c | Strengthen the Environmental Protection Agency <br> enforcement of the Clean Air Act and Clean Water Act <br> even if it costs U.S. jobs |  |

### 5.2.6 enviro_vs_jobs

Preference scale between environmental protection and job availability (1=Environmental protection, 5=Job protection)
Years in data: 2006, 2007, 2008, 2010, 2012, 2013
Table 25: enviro_vs_jobs: Frequency table

| Response | 2006 | 2007 | 2008 | 2010 | 2012 | 2013 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Environment much more important | 8,569 | 2,598 | 4,573 | 7,643 | 6,558 | 2,172 |
| Environment somewhat more important | 8,919 | 2,442 | 6,158 | 9,802 | 9,602 | 2,874 |
| Environment and jobs of same importance | 8,134 | 2,107 | 8,851 | 15,358 | 17,209 | 5,844 |
| Jobs somewhat more important | 6,247 | 1,705 | 7,973 | 13,453 | 13,340 | 3,422 |
| Jobs much more important | 3,005 | 832 | 5,136 | 8,964 | 7,591 | 2,038 |
| Haven't thought much about this | 1,292 | 261 | 0 | 0 | 0 | 0 |

Year-specific variable names and wording
Table 26: enviro_vs_jobs: Year-specific wording

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2006 | v3022 | Some people think it is important to protect the environment even if it costs some jobs or otherwise reduces our standard of living. Other people think that protecting the environment is not as important as maintaining jobs and our standard of living. Which is closer to the way you feel, or haven't you thought much about this? |
| 2007 | CC06_V3022 | Some people think it is important to protect the environment even if it costs some jobs or otherwise reduces our standard of living. Other people think that protecting the environment is not as important as maintaining jobs and our standard of living. Which is closer to the way you feel, or haven't you thought much about this? |
| 2008 | cc311 | Some people think it is important to protect the environment even if it costs some jobs or otherwise reduces our standard of living. Other people think that protecting the environment is not as important as maintaining jobs and our standard of living. Which is closer to the way you feel, or haven't you thought much about this? |

Table 26: enviro_vs_jobs: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2010 | cc325 | Some people think it is important to protect the environment even if it costs some jobs or otherwise reduces our standard of living. Other people think that protecting the environment is not as important as maintaining jobs and our standard of living. Which is closer to the way you feel, or haven't you thought much about this? |
| 2012 | CC325 | Some people think it is important to protect the environment even if it costs some jobs or otherwise reduces our standard of living. Other people think that protecting the environment is not as important as maintaining jobs and our standard of living. Which is closer to the way you feel, or haven't you thought much about this? |
| 2013 | CC328 | Some people think it is important to protect the environment even if it costs some jobs or otherwise reduces our standard of living. Other people think that protecting the environment is not as important as maintaining jobs and our standard of living. Which is closer to the way you feel, or haven't you thought much about this? |

Note: In 2006 and 2007, this question includes a sixth response option, 'Haven't thought much about this'.

### 5.3 Guns

### 5.3.1 guns_scale

Restriction scale on gun sales (1 = More strict, 2 = Less strict, $3=$ Same)
Years in data: 2010, 2012
Table 27: guns_scale: Frequency table

| Response | 2010 | 2012 |
| :--- | :---: | :---: |
| More strict | 23,044 | 25,616 |
| Less strict | 10,491 | 7,664 |
| Kept as they are | 21,807 | 21,171 |

Year-specific variable names and wording
Table 28: guns_scale: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2010 | cc320 | In general, do you feel that the laws covering the sale of <br> firearms should be made more strict, less strict, or kept as <br> they are? |
| 2012 | CC320In general, do you feel that the laws covering the sale of <br> firearms should be... [1 More Strict, 2 Less Strict, 3 Kept <br> As They Are] |  |

### 5.3.2 guns_bgchecks

Background checks for guns for all sales
Years in data: 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2021
Table 29: guns_bgchecks: Frequency table

| Response | 2013 | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2021 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 14,136 | 48,950 | 12,333 | 58,138 | 16,481 | 53,989 | 15,475 | 22,989 |
| Oppose | 2,184 | 7,015 | 1,841 | 6,247 | 1,707 | 5,728 | 2,518 | 2,711 |

Year-specific variable names and wording

Table 30: guns_bgchecks: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2013 | CC13_320a | On the issue of gun regulation, are you for or against each <br> of the following proposals? Background checks for all <br> sales, including at gun shows and over the Internet |
| 2014 | CC14_320a | On the issue of gun regulation, are you for or against each <br> of the following ... Background Checks <br> On the issue of gun regulation, are you for or against each <br> of the following proposals? Background checks for all <br> sales, including at gun shows and over the Internet <br> On the issue of gun regulation, do you support or oppose |
| 2015 CC15_320a | CC16_330a | Onch of the following proposals? Background checks for <br> eall sales, including at gun shows and over the Internet |
| 2018 | CC17_330a | On the issue of gun regulation, are you for or against each <br> of the following proposals? Background checks for all <br> sales, including at gun shows and over the Internet <br> On the issue of gun regulation, are you for or against each <br> of the following proposals? Background checks for all <br> sales, including at gun shows and over the Internet |
| 2019 | CC19_320a | Background checks for all gun sales, including at gun <br> shows and over the Internet |
| 2021 | CC21_321f | Require criminal background checks on all gun sales |

### 5.3.3 guns_names

Prohibit state and local publishing gun owner names
Years in data: 2013, 2014, 2015, 2016, 2017, 2020
Table 31: guns_names: Frequency table

| Response | 2013 | 2014 | 2015 | 2016 | 2017 | 2020 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 9,832 | 32,054 | 8,411 | 37,944 | 9,930 | 32,847 |
| Oppose | 6,437 | 23,812 | 5,743 | 26,273 | 8,256 | 28,138 |

Year-specific variable names and wording

Table 32: guns_names: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2013 | CC13_320b | On the issue of gun regulation, are you for or against each <br> of the following proposals? Prohibit state and local <br> governments from publishing the names and addresses of <br> all gun owners |
| 2014 CC14_320b | On the issue of gun regulation, are you for or against each <br> of the following ... Prohibit state and local governments <br> from publishing the names and addresses of all gun <br> owners |  |
| 2015 CC15_320b | On the issue of gun regulation, are you for or against each <br> of the following proposals? Prohibit state and local <br> governments from publishing the names and addresses of <br> all gun owners |  |
| 2016 CC16_330b | On the issue of gun regulation, do you support or oppose <br> each of the following proposals? Prohibit state and local <br> governments from publishing the names and addresses of <br> all gun owners |  |
| 2020 CC20_330a | On the issue of gun regulation, are you for or against each <br> of the following proposals? Prohibit state and local <br> governments from publishing the names and addresses of <br> all gun owners |  |

### 5.3.4 guns_assaultban

## Ban assault rifles

Years in data: 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021
Table 33: guns_assaultban: Frequency table

| Response | 2013 | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 10,276 | 35,933 | 8,945 | 42,603 | 12,732 | 39,057 | 11,175 | 39,236 | 16,001 |
| Oppose | 5,924 | 19,799 | 5,210 | 21,548 | 5,453 | 20,507 | 6,803 | 21,750 | 9,699 |

Year-specific variable names and wording

Table 34: guns_assaultban: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2013 CC13_320d | On the issue of gun regulation, are you for or against each <br> of the following proposals? Ban assault rifles |  |
| 2014 | CC14_320d | On the issue of gun regulation, are you for or against each <br> of the following ... Ban assault rifles |
| 2015 CC15_320c | On the issue of gun regulation, are you for or against each <br> of the following proposals? Ban assault rifles |  |
| 2016 CC16_330d | On the issue of gun regulation, do you support or oppose <br> each of the following proposals? Ban assault rifles |  |
| 2017 CC17_330c | On the issue of gun regulation, are you for or against each <br> of the following proposals? Ban assault rifles |  |
| 2018 CC18_320c | On the issue of gun regulation, are you for or against each <br> of the following proposals? Ban assault rifles |  |
| 2019 | CC19_320c | Ban assault rifles |
| 2020 CC20_330b | Ban assault rifles |  |
| 2021 CC21_321a | Ban assault rifles |  |

### 5.3.5 guns_permits

Ease ability to obtain concealed-carry permits
Years in data: 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021
Table 35: guns_permits: Frequency table

| Response | 2013 | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 6,293 | 21,611 | 5,798 | 24,241 | 6,824 | 20,554 | 7,013 | 21,838 | 9,044 |
| Oppose | 9,961 | 34,245 | 8,358 | 39,982 | 11,364 | 39,036 | 10,979 | 39,146 | 16,656 |

Year-specific variable names and wording
Table 36: guns_permits: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2013 | CC13_320e | On the issue of gun regulation, are you for or against each <br> of the following proposals? Make it easier for people to <br> obtain concealed-carry permit |

Table 36: guns_permits: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2014 | CC14_320e | On the issue of gun regulation, are you for or against each of the following . . . Make it easier for people to obtain concealed weapons permits |
| 2015 | CC15_320d | On the issue of gun regulation, are you for or against each of the following proposals? Make it easier for people to obtain concealed-carry permit |
| 2016 | CC16_330e | On the issue of gun regulation, do you support or oppose each of the following proposals? Make it easier for people to obtain concealed-carry permit |
| 2017 | CC17_330d | On the issue of gun regulation, are you for or against each of the following proposals? Make it easier for people to obtain concealed-carry permit |
| 2018 | CC18_320d | On the issue of gun regulation, are you for or against each of the following proposals? Make it easier for people to obtain concealed-carry permit |
| 2019 | CC19_320d | Make it easier for people to obtain concealed-carry permit |
| 2020 | CC20_330c | Make it easier for people to obtain concealed-carry permit |
| 2021 | CC21_321b | Make it easier for people to obtain concealed-carry permit |

### 5.4 Health care

### 5.4.1 healthcare_aca

Repeal the Affordable Care Act
Years in data: 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021
Table 37: healthcare_aca: Frequency table

| Year | Support | Oppose |
| :---: | :---: | :---: |
| 2012 | 23,288 | 28,884 |
| 2013 | 8,506 | 7,321 |
| 2014 | 26,879 | 28,950 |
| 2015 | 7,881 | 6,166 |
| 2016 | 34,693 | 29,816 |
| 2017 | 8,026 | 10,020 |
| 2018 | 24,887 | 35,039 |
| 2019 | 8,349 | 9,501 |
| 2020 | 24,898 | 35,958 |
| 2021 | 10,704 | 14,996 |

Year-specific variable names and wording
Table 38: healthcare_aca: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2012 | CC332G | Congress Considered many important bills over the past <br> two years. For each of the following tell us whether you <br> support or oppose the legislation in principle. Repeal <br> Affordable Care Act. Would repeal the Affordable Care <br> Act. |
| 2013 CC332C | Congress considered many important bills over the past <br> few years. For each of the following tell us whether you <br> support or oppose the legislation in principle. Repeal <br> Affordable Care Act. Would repeal the Affordable Care |  |
| Act. |  |  |

Table 38: healthcare_aca: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2014 | CC14_324_1 | The Affordable Health Care Act was passed into law in 2010. It does the following: Requires Americans to obtain health insurance. Prevents insurance companies from denying coverage for pre-existing conditions. Allows people to keep current health insurance and care provider. Sets up national health insurance option for those without coverage, but allows states the option to implement their own insurance system. Would you vote to repeal the Affordable Care Act if you were in Congress in today? |
| 2015 | CC15_327A | Congress considered many important bills over the past few years. For each of the following tell us whether you support or oppose the legislation in principle. Repeal Affordable Care Act. Would repeal the Affordable Care Act. |
| 2016 | CC16_351I | Congress considers many issues. If you were in Congress would you vote FOR or AGAINST each of the following? Repeal Affordable Care Act. Would repeal the Affordable Care Act of 2009 (also known as Obamacare). |
| 2017 | CC17_340A | Congress considered many important bills over the past few years. For each of the following tell us whether you support or oppose the legislation in principle. Repeal Affordable Care Act. Would repeal the Affordable Care Act. |
| 2018 | CC18_327c | Thinking now about health care policy, would you support or oppose each of the following proposals? Health Care Repeal the entire Affordable Care Act. |
| 2019 | CC19_327d | Thinking now about health care policy, would you support or oppose each of the following proposals? Repeal the entire Affordable Care Act. |
| 2020 | CC20_327d | Repeal the entire Affordable Care Act. |
| 2021 | CC21_320b | Repeal the entire Affordable Care Act. |

### 5.4.2 healthcare_acamandate

Restore ACA mandate requiring everyone to be insured
Years in data: 2019, 2020, 2021

Table 39: healthcare_acamandate: Frequency table

| Response | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: |
| Support | 6,754 | 25,412 | 10,227 |
| Oppose | 11,091 | 35,476 | 15,473 |

Year-specific variable names and wording
Table 40: healthcare_acamandate: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2019 | CC19_327e | Thinking now about health care policy, would you support <br> or oppose each of the following proposals? Restore the <br> Affordable Care Act's mandate that all individuals be <br> required to purchase health insurance. |
| 2020 CC20_327e | Restore the Affordable Care Act's mandate that all <br> individuals be required to purchase health insurance. |  |
| 2021 CC21_320c | Restore the Affordable Care Act's mandate that all <br> individuals be required to purchase health insurance. |  |

### 5.4.3 healthcare_medicare

Provide Medicare for all Americans
Years in data: 2018, 2019, 2020, 2021
Table 41: healthcare_medicare: Frequency table

| Response | 2018 | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: |
| Support | 41,280 | 9,713 | 39,183 | 16,563 |
| Oppose | 18,637 | 8,129 | 21,718 | 9,137 |

Year-specific variable names and wording
Table 42: healthcare_medicare: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2018 | CC18_327a | Thinking now about health care policy, would you support <br> or oppose each of the following proposals? Provide <br> Medicare for all Americans. |

Table 42: healthcare_medicare: Year-specific wording (continued)
$\left.\begin{array}{cll}\hline \text { Year } & \text { Variable } & \text { Question wording } \\ \hline 2019 & \text { CC19_327a } & \begin{array}{l}\text { Thinking now about health care policy, would you support } \\ \text { or oppose each of the following proposals? Expand } \\ \text { Medicare to a single comprehensive public health care } \\ \text { coverage program that would cover all Americans. }\end{array} \\ 2020 & \text { CC20_327a } & \begin{array}{l}\text { Expand Medicare to a single comprehensive public health } \\ \text { care coverage program that would cover all Americans. } \\ 2021\end{array} \text { CC21_320a }\end{array} \begin{array}{l}\text { Expand Medicare to a single comprehensive public health } \\ \text { care program that would cover all Americans. }\end{array}\right]$

### 5.4.4 healthcare_medicareage

Lower the eligibility age for Medicare from 65 to 50
Years in data: 2019, 2020
Table 43: healthcare_medicareage: Frequency table

| Response | 2019 | 2020 |
| :--- | :---: | :---: |
| Support | 10,102 | 37,204 |
| Oppose | 7,759 | 23,677 |

Year-specific variable names and wording
Table 44: healthcare_medicareage: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2019 | CC19_327c | Thinking now about health care policy, would you support <br> or oppose each of the following proposals? Lower the <br> eligibility age for Medicare from 65 to 50. |
| 2020 | CC20_327c | Lower the eligibility age for Medicare from 65 to 50. |

### 5.5 Immigration

### 5.5.1 immig_legalize

Grant conditional legal status to undocumented
Years in data: 2007, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2019, 2020, 2021

Table 45: immig_legalize: Frequency table

| Year | Support | Oppose |
| :---: | :---: | :---: |
| 2007 | 3,430 | 6,570 |
| 2010 | 22,162 | 33,238 |
| 2011 | 8,898 | 11,252 |
| 2012 | 25,316 | 29,219 |
| 2013 | 7,672 | 8,728 |
| 2014 | 26,970 | 29,230 |
| 2015 | 7,147 | 7,103 |
| 2016 | 36,182 | 28,418 |
| 2017 | 10,195 | 8,005 |
| 2019 | 11,644 | 6,264 |
| 2020 | 43,277 | 17,667 |
| 2021 | 17,357 | 8,343 |

Year-specific variable names and wording
Table 46: immig_legalize: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2007 | CC12x_2 | What do you think Congress and the President should do <br> about immigration? Select all that apply. Grant legal status <br> to all illegal immigrants who have held jobs and paid taxes <br> for at least 3 years, and not been convicted of any felony <br> crimes. |
| 2010 cc322_2 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Grant legal status to all <br> illegal immigrants who have held jobs and paid taxes for at <br> least 3 years, and not been convicted of any felony crimes. |  |
| 2011 | CC351_1 | Immigration - Amnesty for long term residents |
| 2012 CC322_1 | Grant legal status to all illegal immigrants who have held <br> jobs and paid taxes for at least 3 years, and not been <br> convicted of any felony crimes. |  |

Table 46: immig_legalize: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2013 | CC326_1 | What do you think the U.S. government should do about immigration? Select all that apply. Grant legal status to all illegal immigrants who have held jobs and paid taxes for at least 3 years, and not been convicted of any felony crimes. |
| 2014 | CC14_322_1 | What do you think the government should do about immigration? Select all that apply . . . Grant legal status to all illegal immigrants who have held jobs and paid taxes for at least 3 years, and not been convicted of any felony crimes |
| 2015 | CC15_321_1 | What do you think the U.S. government should do about immigration? Select all that apply. Grant legal status to all illegal immigrants who have held jobs and paid taxes for at least 3 years, and not been convicted of any felony crimes. |
| 2016 | CC16_331_1 | What do you think the U.S. government should do about immigration? Select all that apply. Immigration - Grant legal status to all illegal immigrants who have held jobs and paid taxes for at least 3 years, and not been convicted of any felony crimes |
| 2017 | CC17_331_1 | What do you think the U.S. government should do about immigration? Select all that apply. Grant legal status to all illegal immigrants who have held jobs and paid taxes for at least 3 years, and not been convicted of any felony crimes. |
| 2019 | CC19_322d | Grant legal status to all illegal immigrants who have held jobs and paid taxes for at least 3 years, and not been convicted of any felony crimes. |
| 2020 | CC20_331a | Grant legal status to all illegal immigrants who have held jobs and paid taxes for at least 3 years, and not been convicted of any felony crimes. |
| 2021 | CC21_322a | Grant legal status to all illegal immigrants who have held jobs and paid taxes for at least 3 years, and not been convicted of any felony crimes. |

### 5.5.2 immig_border

Increase border security between US-Mexico
Years in data: 2007, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2019, 2020, 2021

Table 47: immig_border: Frequency table

| Year | Support | Oppose |
| :---: | :---: | :---: |
| 2007 | 5,452 | 4,548 |
| 2010 | 33,861 | 21,539 |
| 2011 | 11,100 | 9,050 |
| 2012 | 30,801 | 23,734 |
| 2013 | 8,769 | 7,631 |
| 2014 | 31,682 | 24,518 |
| 2015 | 7,601 | 6,649 |
| 2016 | 31,858 | 32,742 |
| 2017 | 7,760 | 10,440 |
| 2019 | 12,003 | 5,868 |
| 2020 | 35,297 | 25,655 |
| 2021 | 16,816 | 8,884 |

Year-specific variable names and wording
Table 48: immig_border: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2007 CC12x_4 | What do you think Congress and the President should do <br> about immigration? Select all that apply. Increase the <br> number of border patrol on the US-Mexican border. |  |
| 2010 cc322_4 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Increase the number of <br> border patrols on the US-Mexican border. |  |
| 2011 CC351_2 | Immigration - Increase border presence <br> Increase the number of border patrols on the US-Mexican <br> border. |  |
| 2012 CC322_2 | CC326_2 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Increase the number of <br> border patrols on the U.S.-Mexican border. |
| 2013 CC14_322_2 | What do you think the government should do about <br> immigration? Select all that apply... Increase Border <br> Patrols along the US-Mexico border |  |
| 2015 CC15_321_2 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Increase the number of <br> border patrols on the US-Mexican border. |  |
| CC16_331_2 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Immigration - Increase <br> the number of border patrols on the U.S.-Mexican border |  |

Table 48: immig_border: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2017 CC17_331_2 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Increase the number of <br> border patrols on the U.S.-Mexican border. |  |
| 2019 CC19_322e | Increase the number of border patrols on the <br> U.S.-Mexican border. |  |
| 2020 CC20_331b | Increase the number of border patrols on the US-Mexican <br> border. |  |
| 2021 CC21_322b | Increase the number of border patrols on the US-Mexican <br> border |  |

Note: In 2018 alone, question wording includes 'building a wall between the U.S. and Mexico', and has been categorized here as under the question item 'immig_wall'.

### 5.5.3 immig_police

Allow police questioning of suspected undocumented
Years in data: 2010, 2011, 2012, 2013, 2014, 2015, 2017
Table 49: immig_police: Frequency table

| Response | 2010 | 2011 | 2012 | 2013 | 2014 | 2015 | 2017 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 25,999 | 8,613 | 21,795 | 6,006 | 19,729 | 5,041 | 5,084 |
| Oppose | 29,401 | 11,537 | 32,740 | 10,394 | 36,471 | 9,209 | 13,116 |

Year-specific variable names and wording
Table 50: immig_police: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2010 | cc322_5 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Allow police to question <br> anyone they think may be in the country illegally. |
| 2011 CC351_3 | Immigration - Police question those reasonably suspected <br> of being illegal |  |
| 2012 CC322_3 | Allow police to question anyone they think may be in the <br> country illegally. |  |

Table 50: immig_police: Year-specific wording (continued)

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2013 CC326_3 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Allow police to question <br> anyone they think may be in the country illegally. |  |
| 2014 CC14_322_3 | What do you think the government should do about <br> immigration? Select all that apply. . Allow police to <br> question anyone they think may be in the country illegally. |  |
| 2015 CC15_321_3What do you think the U.S. government should do about <br> immigration? Select all that apply. Allow police to question <br> anyone they think may be in the country illegally. |  |  |
| 2017 CC17_331_3What do you think the U.S. government should do about <br> immigration? Select all that apply. Allow police to question <br> anyone they think may be in the country illegally. |  |  |

### 5.5.4 immig_employer

Sanction employers hiring undocumented
Years in data: 2007, 2010, 2012, 2013, 2014, 2015, 2016, 2017
Table 51: immig_employer: Frequency table

| Response | 2007 | 2010 | 2012 | 2013 | 2014 | 2015 | 2016 | 2017 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Support | 6,898 | 1,684 | 34,354 | 10,310 | 34,013 | 8,387 | 8,578 | 9,207 |
| Oppose | 3,102 | 579 | 20,181 | 6,090 | 22,187 | 5,863 | 4,691 | 8,993 |

Year-specific variable names and wording
Table 52: immig_employer: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2007 | CC12x_1 | What do you think Congress and the President should do <br> about immigration? Select all that apply. Fine US <br> businesses that hire illegal immigrants. |
| 2010 | cc322_1 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Fine Businesses |
| 2012 CC322_4 | Fine US businesses that hire illegal immigrants. |  |

Table 52: immig_employer: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2013 CC326_4 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Fine U.S. businesses <br> that hire illegal immigrants. |  |
| 2014 CC14_322_4 | What do you think the government should do about <br> immigration? Select all that apply . . Fine US businesses <br> that hire illegal immigrants |  |
| 2015 CC15_321_4What do you think the U.S. government should do about <br> immigration? Select all that apply. Fine US businesses <br> that hire illegal immigrants. |  |  |
| 2016 CC16_331_4What do you think the U.S. government should do about <br> immigration? Select all that apply. Immigration - Fine U.S. <br> businesses that hire illegal immigrants |  |  |
| 2017 CC17_331_4What do you think the U.S. government should do about <br> immigration? Select all that apply. Fine U.S. businesses <br> that hire illegal immigrants. |  |  |

### 5.5.5 immig_services

Prohibit services to immigrants
Years in data: 2012, 2013
Table 53: immig_services: Frequency table

| Response | 2012 | 2013 |
| :--- | :---: | :---: |
| Support | 17,415 | 5,078 |
| Oppose | 37,120 | 11,322 |

Year-specific variable names and wording
Table 54: immig_services: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2012 | CC322_5 | Prohibit illegal immigrants from using emergency hospital <br> care and public schools. |

Table 54: immig_services: Year-specific wording (continued)

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2013 CC326_5 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Prohibit illegal <br> immigrants from using emergency hospital care and public <br> schools. |  |

### 5.5.6 immig_deport

Identify and deport illegal immigrants
Years in data: 2014, 2015, 2016, 2017
Table 55: immig_deport: Frequency table

| Response | 2014 | 2015 | 2016 | 2017 |
| :--- | :---: | :---: | :---: | :---: |
| Support | 30,574 | 7,165 | 26,249 | 6,762 |
| Oppose | 25,626 | 7,085 | 38,351 | 11,438 |

Year-specific variable names and wording
Table 56: immig_deport: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2014 | CC14_322_5 | What do you think the government should do about <br> immigration? Select all that apply . . Identify and deport <br> illegal immigrants |
| 2015 CC15_321_5 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Identify and deport <br> illegal immigrants. |  |
| 2016 CC16_331_7What do you think the U.S. government should do about <br> immigration? Select all that apply. Immigration - Idenfity <br> and deport illegal immigrants |  |  |
| 2017 CC17_331_5What do you think the U.S. government should do about <br> immigration? Select all that apply. Identify and deport <br> illegal immigrants. |  |  |

### 5.5.7 immig_report

Withhold funding from police failing to report illegal immigrants

Years in data: 2017, 2018, 2019, 2020, 2021
Table 57: immig_report: Frequency table

| Response | 2017 | 2018 | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Support | 6,988 | 27,821 | 8,214 | 25,881 | 11,567 |
| Oppose | 11,212 | 32,124 | 9,686 | 35,072 | 14,133 |

Year-specific variable names and wording
Table 58: immig_report: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2017 CC17_331_8 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Require local police <br> departments to report to the federal government anyone <br> they identify as an illegal immigrant. |  |
| 2018 CC18_322c | What do you think the U.S. government should do about <br> immigration? Do you support or oppose each of the <br> following? Withhold federal funds from any local police <br> department that does not report to the federal government <br> anyone they identify as an illegal immigrant |  |
| 2019 | CC19_322b | Withhold federal funds from any local police department <br> that does not report to the federal government anyone <br> they identify as an illegal immigrant. |
| 2020 CC20_331c | Withhold federal funds from any local police department <br> that does not report to the federal government anyone <br> they identify as an illegal immigrant. |  |

### 5.5.8 immig_reduce

Reduce legal immigration by 50 percent
Years in data: 2018, 2019, 2020
Table 59: immig_reduce: Frequency table

| Response | 2018 | 2019 | 2020 |
| :--- | :---: | :---: | :---: |
| Support | 24,732 | 6,967 | 22,755 |

Table 59: immig_reduce: Frequency table (continued)

| Response | 2018 | 2019 | 2020 |
| :--- | :---: | :---: | :---: |
| Oppose | 33,934 | 10,882 | 38,169 |

Year-specific variable names and wording
Table 60: immig_reduce: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2018 | CC18_322c_new | Reduce legal immigration by eliminating the visa lottery <br> and ending family-based migration |
| 2019 | CC19_322c | Reduce legal immigration by 50 percent. |
| 2020 CC20_331d | Reduce legal immigration by 50 percent over the next 10 <br> years by eliminating the visa lottery and ending <br> family-based migration. |  |

### 5.5.9 immig_wall

Increase spending on border security, including building a wall
Years in data: 2017, 2018, 2020, 2021
Table 61: immig_wall: Frequency table

| Response | 2017 | 2018 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: |
| Support | 5,076 | 24,362 | 23,893 | 10,914 |
| Oppose | 13,124 | 35,323 | 37,053 | 14,786 |

Year-specific variable names and wording
Table 62: immig_wall: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2017 | CC17_331_7 | What do you think the U.S. government should do about <br> immigration? Select all that apply. Build a wall between <br>  |
|  |  |  |

Table 62: immig_wall: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2018 | CC18_322a | What do you think the U.S. government should do about <br> immigration? Do you support or oppose each of the <br> following? Increase spending on border security by 25 <br> billion, including building a wall between the U.S. and <br> Mexico. |
| 2020 CC20_331e | Increase spending on border security by 25 billion dollars, <br> including building a wall between the U.S. and Mexico. |  |
| $2021 \quad$ CC21_322d | Build a wall between the U.S. and Mexico. |  |

### 5.6 Military

### 5.6.1 military_oil

Approve of military ensuring oil supply
Years in data: 2006, 2007, 2008, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2020
Table 63: military_oil: Frequency table

| Year | Support | Oppose |
| :---: | :---: | :---: |
| 2006 | 7,457 | 28,900 |
| 2007 | 2,056 | 7,932 |
| 2008 | 6,841 | 20,180 |
| 2010 | 12,206 | 34,478 |
| 2011 | 4,791 | 15,359 |
| 2012 | 11,483 | 33,535 |
| 2013 | 3,815 | 12,585 |
| 2014 | 9,853 | 39,035 |
| 2015 | 3,027 | 11,223 |
| 2016 | 9,521 | 43,378 |
| 2020 | 9,623 | 41,928 |

Year-specific variable names and wording
Table 64: military_oil: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2006 v3029 | For each of the following reasons, would you approve of <br> the use of U.S. military troops? Please check all that <br> apply: Military use to ensure the supply of oil |  |
| 2007 CC06_V3029 | For each of the following reasons, would you approve of <br> the use of U.S. military troops? Please check all that <br> apply: To nsure the supply of oil |  |
| 2008 cc418_1 | Would you approve of the use of U.S. military troops in <br> order to...? Ensure the supply of oil |  |
| 2010 cc414_1 | Would you approve of the use of U.S. military troops in <br> order to...? Ensure the supply of oil |  |
| 2011 CC356_1 | Ensure the supply of oil <br> Would you approve of the use of U.S. military troops in |  |
| 2013 CC414_1 | Wrder to...? Ensure the supply of oil |  |
| CC322_1 | Would you approve of the use of U.S. military troops in <br> order to...? Ensure the supply of oil |  |

Table 64: military_oil: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2014 CC414_1 | Would you approve of the use of U.S. military troops in <br> order to...? Ensure the supply of oil |  |
| 2015 CC15_324_1 | Would you approve of the use of U.S. military troops in <br> order to...? Ensure the supply of oil |  |
| 2016 CC16_414_1 | Would you approve of the use of U.S. military troops in <br> order to...? Ensure the supply of oil |  |
| 2020 CC20_420_1 | Ensure the supply of oil |  |

### 5.6.2 military_terroristcamp

Approve of military to destroy terrorist camp
Years in data: 2006, 2007, 2008, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2020
Table 65: military_terroristcamp: Frequency table

| Year | Support | Oppose |
| :---: | :---: | :---: |
| 2006 | 25,760 | 10,597 |
| 2007 | 7,222 | 2,766 |
| 2008 | 19,336 | 7,685 |
| 2010 | 33,030 | 13,654 |
| 2011 | 13,616 | 6,534 |
| 2012 | 28,745 | 16,273 |
| 2013 | 9,615 | 6,785 |
| 2014 | 29,828 | 19,060 |
| 2015 | 9,845 | 4,405 |
| 2016 | 34,290 | 18,609 |
| 2020 | 31,977 | 19,574 |

Year-specific variable names and wording
Table 66: military_terroristcamp: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2006 | v3030 | For each of the following reasons, would you approve of <br> the use of U.S. military troops? Please check all that <br> apply: Military use to destroy a Terrorist camp |

Table 66: military_terroristcamp: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2007 | CC06_V3030 | For each of the following reasons, would you approve of the use of U.S. military troops? Please check all that apply: Destroy a terrorist camp |
| 2008 | cc418_2 | Would you approve of the use of U.S. military troops in order to...? Destroy a terrorist camp |
| 2010 | cc414_2 | Would you approve of the use of U.S. military troops in order to...? Destroy a terrorist camp |
| 2011 | CC356_2 | Destroy a terrorist camp |
| 2012 | CC414_2 | Would you approve of the use of U.S. military troops in order to...? Destroy a terrorist camp |
| 2013 | CC322_2 | Would you approve of the use of U.S. military troops in order to...? Destroy a terrorist camp |
| 2014 | CC414_2 | Would you approve of the use of U.S. military troops in order to...? Destroy a terrorist camp |
| 2015 | CC15_324_2 | Would you approve of the use of U.S. military troops in order to...? Destroy a terrorist camp |
| 2016 | CC16_414_2 | Would you approve of the use of U.S. military troops in order to...? Destroy a terrorist camp |
| 2020 | CC20_420_2 | Destroy a terrorist camp |

### 5.6.3 military_genocide

Approve of military to intervene in genocide or civil war
Years in data: 2006, 2007, 2008, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2020
Table 67: military_genocide: Frequency table

| Year | Support | Oppose |
| :---: | :---: | :---: |
| 2006 | 19,111 | 17,246 |
| 2007 | 5,392 | 4,596 |
| 2008 | 13,787 | 13,234 |
| 2010 | 19,179 | 27,505 |
| 2011 | 7,923 | 12,227 |
| 2012 | 16,341 | 28,677 |
| 2013 | 4,680 | 11,720 |
| 2014 | 17,994 | 30,894 |
| 2015 | 6,161 | 8,089 |

Table 67: military_genocide: Frequency table (continued)

| Year | Support | Oppose |
| :---: | :---: | :---: |
| 2016 | 20,546 | 32,353 |
| 2020 | 24,731 | 26,820 |

Year-specific variable names and wording
Table 68: military_genocide: Year-specific wording

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2006 | v3031 | For each of the following reasons, would you approve of the use of U.S. military troops? Please check all that apply: Military use to intervene in Genocide or Civil War |
| 2007 | CC06_V3031 | For each of the following reasons, would you approve of the use of U.S. military troops? Please check all that apply: Intervene in a region where there is genocide or a civil war |
| 2008 | cc418_3 | Would you approve of the use of U.S. military troops in order to...? Intervene in a region where there is genocide or a civil war |
| 2010 | cc414_3 | Would you approve of the use of U.S. military troops in order to...? Intervene in a region where there is genocide or a civil war |
| 2011 | CC356_3 | Intervene in a region where there is genocide or a civil war |
| 2012 | CC414_3 | Would you approve of the use of U.S. military troops in order to...? Intervene in a region where there is genocide or a civil war |
| 2013 | CC322_3 | Would you approve of the use of U.S. military troops in order to...? Intervene in a region where there is genocide or a civil war |
| 2014 | CC414_3 | Would you approve of the use of U.S. military troops in order to...? Intervene in a region where there is genocide or a civil war |
| 2015 | CC15_324_3 | Would you approve of the use of U.S. military troops in order to...? Intervene in a region where there is genocide or a civil war |
| 2016 | CC16_414_3 | Would you approve of the use of U.S. military troops in order to...? Intervene in a region where there is genocide or a civil war |
| 2020 | CC20_420_3 | Intervene in a region where there is genocide or a civil war |

### 5.6.4 military_democracy

Approve of military to assist in spread democracy
Years in data: 2006, 2007, 2008, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2020
Table 69: military_democracy: Frequency table

| Year | Support | Oppose |
| :---: | :---: | :---: |
| 2006 | 8,300 | 28,057 |
| 2007 | 2,147 | 7,841 |
| 2008 | 6,637 | 20,384 |
| 2010 | 8,885 | 37,799 |
| 2011 | 3,160 | 16,990 |
| 2012 | 7,651 | 37,367 |
| 2013 | 2,323 | 14,077 |
| 2014 | 7,354 | 41,534 |
| 2015 | 2,216 | 12,034 |
| 2016 | 7,896 | 45,003 |
| 2020 | 10,336 | 41,215 |

Year-specific variable names and wording
Table 70: military_democracy: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2006 | v3032 | For each of the following reasons, would you approve of <br> the use of U.S. military troops? Please check all that <br> apply: Military use to Spread democracy |
| 2007 | CC06_V3032 | For each of the following reasons, would you approve of <br> the use of U.S. military troops? Please check all that <br> apply: Spread of democracy |
| 2008 cc418_4 | Would you approve of the use of U.S. military troops in <br> order to...? Assist the spread of democracy |  |
| 2010 | cc414_4 | Would you approve of the use of U.S. military troops in <br> order to...? Assist the spread of democracy |
| 2011 CC356_4 | Assist the spread of democracy |  |
| 2012 | CC414_4 | Would you approve of the use of U.S. military troops in <br> order to...? Assist the spread of democracy <br> Would you approve of the use of U.S. military troops in <br> order to...? Assist the spread of democracy |
| 2013 CC322_4 CC414_4 | Would you approve of the use of U.S. military troops in <br> order to...? Assist the spread of democracy |  |

Table 70: military_democracy: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2015 | CC15_324_4 | Would you approve of the use of U.S. military troops in <br> order to...? Assist the spread of democracy |
| 2016 | CC16_414_4 | Would you approve of the use of U.S. military troops in <br> order to...? Assist the spread of democracy |
| 2020 | CC20_420_4 | Assist the spread of democracy |

### 5.6.5 military_protectallies

Approve of military to protect US allies under attack
Years in data: 2006, 2007, 2008, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2020
Table 71: military_protectallies: Frequency table

| Year | Support | Oppose |
| :---: | :---: | :---: |
| 2006 | 29,214 | 7,143 |
| 2007 | 8,206 | 1,782 |
| 2008 | 21,013 | 6,008 |
| 2010 | 34,750 | 11,934 |
| 2011 | 14,501 | 5,649 |
| 2012 | 32,800 | 12,218 |
| 2013 | 11,517 | 4,883 |
| 2014 | 32,943 | 15,945 |
| 2015 | 10,337 | 3,913 |
| 2016 | 37,979 | 14,920 |
| 2020 | 39,627 | 11,924 |

Year-specific variable names and wording
Table 72: military_protectallies: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2006 | v3033 | For each of the following reasons, would you approve of <br> the use of U.S. military troops? Please check all that <br> apply: Military use to Protect American Allies |
| 2007 | CC06_V3033 | For each of the following reasons, would you approve of <br> the use of U.S. military troops? Please check all that <br> apply: Protect American allies |

Table 72: military_protectallies: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2008 cc418_5 | Would you approve of the use of U.S. military troops in <br> order to...? Protect American allies under attack by foreign <br> nations |  |
| 2010 cc414_5 | Would you approve of the use of U.S. military troops in <br> order to...? Protect American allies under attack by foreign <br> nations |  |
| 2011 CC356_5 | Protect American allies under attack by foreign nations <br> 2012 <br> CC414_5 | Would you approve of the use of U.S. military troops in <br> order to...? Protect American allies under attack by foreign <br> nations |
| 2013 CC322_5 | Would you approve of the use of U.S. military troops in <br> order to...? Protect American allies under attack by foreign <br> nations |  |
| 2015 CC415_524_5 | Would you approve of the use of U.S. military troops in <br> order to...? Protect American allies under attack by foreign <br> nations |  |
| Would you approve of the use of U.S. military troops in <br> order to...? Protect American allies under attack by foreign <br> nations |  |  |
| 2016 CC16_414_5Would you approve of the use of U.S. military troops in <br> order to...? Protect American allies under attack by foreign <br> nations |  |  |

### 5.6.6 military_helpun

Approve of military to help the United Nations uphold international law Years in data: 2006, 2007, 2008, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2020

Table 73: military_helpun: Frequency table

| Year | Support | Oppose |
| :---: | :---: | :---: |
| 2006 | 19,987 | 16,370 |
| 2007 | 5,577 | 4,411 |
| 2008 | 13,402 | 13,619 |
| 2010 | 18,727 | 27,957 |
| 2011 | 8,690 | 11,460 |
| 2012 | 18,244 | 26,774 |

Table 73: military_helpun: Frequency table (continued)

| Year | Support | Oppose |
| :---: | :---: | :---: |
| 2013 | 7,395 | 9,005 |
| 2014 | 20,069 | 28,819 |
| 2015 | 6,715 | 7,535 |
| 2016 | 24,159 | 28,740 |
| 2020 | 25,563 | 25,988 |

Year-specific variable names and wording
Table 74: military_helpun: Year-specific wording

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2006 | v3034 | For each of the following reasons, would you approve of the use of U.S. military troops? Please check all that apply: Military use to Help the United Nations |
| 2007 | CC06_V3034 | For each of the following reasons, would you approve of the use of U.S. military troops? Please check all that apply: To help the United Nations uphold international law |
| 2008 | cc418_6 | Would you approve of the use of U.S. military troops in order to...? Help the United Nations uphold international law |
| 2010 | cc414_6 | Would you approve of the use of U.S. military troops in order to...? Help the United Nations uphold international law |
| 2011 | CC356_6 | Help the United Nations uphold international law |
| 2012 | CC414_6 | Would you approve of the use of U.S. military troops in order to...? Help the United Nations uphold international law |
| 2013 | CC322_6 | Would you approve of the use of U.S. military troops in order to...? Help the United Nations uphold international law |
| 2014 | CC414_6 | Would you approve of the use of U.S. military troops in order to...? Help the United Nations uphold international law |
| 2015 | CC15_324_6 | Would you approve of the use of U.S. military troops in order to...? Help the United Nations uphold international law |
| 2016 | CC16_414_6 | Would you approve of the use of U.S. military troops in order to...? Help the United Nations uphold international law |

Table 74: military_helpun: Year-specific wording (continued)

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2020 | CC2O_420_6 | Help the United Nations uphold international law |

### 5.7 Spending

### 5.7.1 spending_welfare

Spending preferences on welfare (1 = Increase, 3 = Maintain, 5 = Decrease) Years in data: 2014, 2016, 2018, 2020

Table 75: spending_welfare: Frequency table

| Response | 2014 | 2016 | 2018 | 2020 |
| :--- | :---: | :---: | :---: | :---: |
| Greatly increase | 4,051 | 4,995 | 6,419 | 9,265 |
| Slightly increase | 7,013 | 7,657 | 9,989 | 10,877 |
| Maintain | 18,848 | 19,534 | 18,863 | 19,113 |
| Slightly decrease | 9,527 | 10,176 | 8,393 | 6,579 |
| Greatly decrease | 9,209 | 10,398 | 8,025 | 5,713 |

Year-specific variable names and wording
Table 76: spending_welfare: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2014 | CC426_1 | Legislative spending - Welfare |
| 2016 CC16_426_1 | State legislatures must make choices when making <br> spending decisions on important state programs. Would <br> you like your legislature to increase or decrease spending <br> on the five areas below? Welfare |  |
| 2018 CC18_426_1 | State legislatures must make choices when making <br> spending decisions on important state programs. Would <br> you like your legislature to increase or decrease spending <br> on the five areas below? Welfare |  |
| 2020 | CC20_443_1 | State legislature spending - Welfare |

### 5.7.2 spending_healthcare

Spending preferences on health care (1 = Increase, $3=$ Maintain, $5=$ Decrease) Years in data: 2014, 2016, 2018, 2020

Table 77: spending_healthcare: Frequency table

| Response | 2014 | 2016 | 2018 | 2020 |
| :--- | :---: | :---: | :---: | :---: |
| Greatly increase | 10,785 | 13,550 | 19,862 | 21,355 |

Table 77: spending_healthcare: Frequency table (continued)

| Response | 2014 | 2016 | 2018 | 2020 |
| :--- | :---: | :---: | :---: | :---: |
| Slightly increase | 12,941 | 14,765 | 14,109 | 12,773 |
| Maintain | 17,637 | 16,781 | 12,689 | 13,480 |
| Slightly decrease | 4,309 | 4,562 | 2,852 | 2,240 |
| Greatly decrease | 2,954 | 3,096 | 2,158 | 1,699 |

Year-specific variable names and wording
Table 78: spending_healthcare: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2014 | CC426_2 | Legislative spending - Health Care |
| 2016 CC16_426_2 | State legislatures must make choices when making <br> spending decisions on important state programs. Would <br> you like your legislature to increase or decrease spending <br> on the five areas below? Health Care |  |
| 2018 CC18_426_2 | State legislatures must make choices when making <br> spending decisions on important state programs. Would <br> you like your legislature to increase or decrease spending <br> on the five areas below? Health Care |  |
| 2020 CC20_443_2 | State legislature spending - Health Care |  |

### 5.7.3 spending_education

Spending preferences on education (1 = Increase, $3=$ Maintain, $5=$ Decrease)
Years in data: 2014, 2016, 2018, 2020
Table 79: spending_education: Frequency table

| Response | 2014 | 2016 | 2018 | 2020 |
| :--- | :---: | :---: | :---: | :---: |
| Greatly increase | 15,912 | 18,166 | 21,875 | 20,732 |
| Slightly increase | 13,917 | 15,144 | 14,467 | 13,399 |
| Maintain | 14,340 | 14,460 | 11,805 | 13,338 |
| Slightly decrease | 2,677 | 2,993 | 2,000 | 2,365 |
| Greatly decrease | 1,755 | 1,969 | 1,500 | 1,712 |

Year-specific variable names and wording

Table 80: spending_education: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2014 | CC426_3 | Legislative spending - Education |
| 2016 CC16_426_3 | State legislatures must make choices when making <br> spending decisions on important state programs. Would <br> you like your legislature to increase or decrease spending <br> on the five areas below? Education |  |
| 2018 CC18_426_3 | State legislatures must make choices when making <br> spending decisions on important state programs. Would <br> you like your legislature to increase or decrease spending <br> on the five areas below? Education |  |
| 2020 | CC20_443_3 | State legislature spending - Education |

### 5.7.4 spending_police

Spending preferences on law enforcement (1 = Increase, $3=$ Maintain, $5=$ Decrease) Years in data: 2014, 2016, 2018, 2020

Table 81: spending_police: Frequency table

| Response | 2014 | 2016 | 2018 | 2020 |
| :--- | :---: | :---: | :---: | :---: |
| Greatly increase | 7,205 | 11,346 | 11,764 | 10,257 |
| Slightly increase | 14,571 | 17,417 | 17,309 | 12,170 |
| Maintain | 21,774 | 19,428 | 18,443 | 16,993 |
| Slightly decrease | 3,532 | 3,052 | 2,699 | 7,079 |
| Greatly decrease | 1,470 | 1,449 | 1,405 | 5,048 |

Year-specific variable names and wording
Table 82: spending_police: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2014 | CC426_4 | Legislative spending - Law Enforcement |
| 2016 | CC16_426_4 | State legislatures must make choices when making <br> spending decisions on important state programs. Would <br> you like your legislature to increase or decrease spending <br> on the five areas below? Law Enforcement |

Table 82: spending_police: Year-specific wording (continued)

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2018 | CC18_426_4 | State legislatures must make choices when making <br> spending decisions on important state programs. Would <br> you like your legislature to increase or decrease spending <br> on the five areas below? Law Enforcement |
| 2020 | CC2O_443_4 | State legislature spending - Law Enforcement |

### 5.7.5 spending_infrastructure

Spending preferences on transportation/infrastructure (1 = Increase, 3 = Maintain, 5 = Decrease)
Years in data: 2014, 2016, 2018, 2020
Table 83: spending_infrastructure: Frequency table

| Response | 2014 | 2016 | 2018 | 2020 |
| :--- | :---: | :---: | :---: | :---: |
| Greatly increase | 9,996 | 13,764 | 16,899 | 15,246 |
| Slightly increase | 14,926 | 17,798 | 19,015 | 17,468 |
| Maintain | 19,993 | 17,793 | 13,851 | 16,357 |
| Slightly decrease | 2,726 | 2,451 | 1,289 | 1,746 |
| Greatly decrease | 904 | 921 | 582 | 720 |

Year-specific variable names and wording
Table 84: spending_infrastructure: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2014 | CC426_5 | Legislative spending - Transportation/Infrastructure |
| 2016 CC16_426_5 | State legislatures must make choices when making <br> spending decisions on important state programs. Would <br> you like your legislature to increase or decrease spending <br> on the five areas below? Transportation/Infrastructure |  |
| 2018 CC18_426_5State legislatures must make choices when making <br> spending decisions on important state programs. Would <br> you like your legislature to increase or decrease spending <br> on the five areas below? Transportation/Infrastructure <br> State legislature spending - Transportation and |  |  |
| 2020 | CC20_443_5 |  |

### 5.7.6 spending_vs_tax

Preference scale from 0 (increasing taxes) to 100 (spending cuts on education, health care, welfare and construction)
Years in data: 2006, 2007, 2008, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2020

Density plots for spending_vs_tax
![](https://cdn.mathpix.com/cropped/2024_12_11_8fae408dd24911bc1c7ag-57.jpg?height=633&width=1503&top_left_y=730&top_left_x=319)

Figure 1: Density plots for question item
Year-specific variable names and wording
Table 85: spending_vs_tax: Year-specific wording

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2006 | v4040 | If your state were to have a budget deficit this year it would have to raise taxes on income or sales or cut spending, such as on education, health care, welfare, and road construction. What would you prefer more raising taxes or cutting spending? Choose a point along the scale from 100 percent tax increases (and no spending cuts) to 100 percent spending cuts (and 0 percent no tax increases). The point in the middle means that any the budget should be balanced with equal amounts of spending cuts and tax increases. If you are not sure, or don't know, please check here: [dk] |

Table 85: spending_vs_tax: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2007 | CC06_V4040 | If your state were to have a budget deficit this year it would have to raise taxes on income or sales or cut spending, such as on education, health care, welfare, and road construction. What would you prefer more raising taxes or cutting spending? Choose a point along the scale from 100 percent tax increases (and no spending cuts) to 100 percent spending cuts (and 0 percent no tax increases). The point in the middle means that any the budget should be balanced with equal amounts of spending cuts and tax increases. |
| 2008 | cc420 | If your state were to have a budget deficit this year it would have to raise taxes on income or sales or cut spending, such as on education, health care, welfare, and road construction. What would you prefer more, raising taxes or cutting spending? Choose a point along the scale from 100 percent tax increases (and no spending cuts) to 100 percent spending cuts (and no tax increases). The point in the middle means that the budget should be balanced with equal amounts of spending cuts and tax increases. If you are not sure, or don't know, please check the box below... Values in range 0 to 100 |
| 2010 | cc415r | If your state were to have a budget deficit this year it would have to raise taxes on income or sales or cut spending, such as on education, health care, welfare, and road construction. What would you prefer more, raising taxes or cutting spending? Choose a point along the scale from 100 percent tax increases (and no spending cuts) to 100 percent spending cuts (and no tax increases). The point in the middle means that the budget should be balanced with equal amounts of spending cuts and tax increases. If you are not sure, or don't know, please check the box below Values in range 0 to 100 |
| 2011 | CC357 | Raise Taxes or Cut Spending Rule |

Table 85: spending_vs_tax: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2012 | CC415r | If your state were to have a budget deficit this year it would have to raise taxes on income and sales or cut spending, such as on education, health care, welfare, and road construction. What would you prefer more raising taxes or cutting spending? Choose a point along the scale from 100 percent tax increases (and no spending cuts) to 100 percent spending cuts (and no tax increases). The point in the middle means that the budget should be balanced with equal amounts of spending cuts and tax increases. If you are Not sure, or don't know, please check the 'not sure' box. |
| 2013 | CC13_323 | If your state were to have a budget deficit this year it would have to raise taxes on income and sales or cut spending, such as on education, health care, welfare, and road construction. What would you prefer more raising taxes or cutting spending? Choose a point along the scale from 100 percent tax increases (and no spending cuts) to 100 percent spending cuts (and no tax increases). The point in the middle means that the budget should be balanced with equal amounts of spending cuts and tax increases. If you are Not sure, or don't know, please check the 'not sure' box. |
| 2014 | CC415r | If your state were to have a budget deficit this year it would have to raise taxes on income and sales or cut spending, such as on education, health care, welfare, and road construction. What would you prefer more raising taxes or cutting spending? Choose a point along the scale from 100 percent tax increases (and no spending cuts) to 100 percent spending cuts (and no tax increases). The point in the middle means that the budget should be balanced with equal amounts of spending cuts and tax increases. If you are Not sure, or don't know, please check the 'not sure' box. |

Table 85: spending_vs_tax: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2015 | CC15_331 | If your state were to have a budget deficit this year it would have to raise taxes on income and sales or cut spending, such as on education, health care, welfare, and road construction. What would you prefer more raising taxes or cutting spending? Choose a point along the scale from 100 percent tax increases (and no spending cuts) to 100 percent spending cuts (and no tax increases). The point in the middle means that the budget should be balanced with equal amounts of spending cuts and tax increases. If you are Not sure, or don't know, please check the 'Not sure' box. |
| 2016 | CC16_415r | If your state were to have a budget deficit this year it would have to raise taxes on income and sales or cut spending, such as on education, health care, welfare, and road construction. What would you prefer more, raising taxes or cutting spending? Choose a point along the scale from 100 |
| 2017 | CC17_343 | If your state were to have a budget deficit this year it would have to raise taxes on income and sales or cut spending, such as on education, health care, welfare, and road construction. What would you prefer more raising taxes or cutting spending? Choose a point along the scale from 100 percent tax increases (and no spending cuts) to 100 percent spending cuts (and no tax increases). The point in the middle means that the budget should be balanced with equal amounts of spending cuts and tax increases. If you are Not sure, or don't know, please check the 'Not sure' box. |
| 2020 | CC20_421r | Tax increases vs. Spending cuts |

### 5.7.7 spending_cuts_most

Most preferred spending cut option (1=Defense, 2=Domestic, 3=Raise taxes)
Years in data: 2006, 2007, 2008, 2010, 2011, 2012, 2013, 2014, 2015, 2017
Table 86: spending_cuts_most: Frequency table

| Year | Cut defense spending | Cut domestic spending | Raise taxes | Borrow |
| :---: | :---: | :---: | :---: | :---: |
| 2006 | 9,310 | 14,579 | 4,813 | 1,396 |
| 2007 | 3,270 | 4,647 | 1,659 | 365 |

Table 86: spending_cuts_most: Frequency table (continued)

| Year | Cut defense spending | Cut domestic spending | Raise taxes | Borrow |
| :---: | :---: | :---: | :---: | :---: |
| 2008 | 11,927 | 17,793 | 2,916 | 0 |
| 2010 | 22,061 | 24,549 | 8,211 | 0 |
| 2011 | 7,227 | 7,538 | 5,385 | 0 |
| 2012 | 21,793 | 20,865 | 11,081 | 0 |
| 2013 | 7,182 | 5,794 | 3,219 | 0 |
| 2014 | 23,581 | 20,764 | 11,218 | 0 |
| 2015 | 5,525 | 5,552 | 2,940 | 0 |
| 2017 | 7,846 | 6,366 | 3,787 | 0 |

Year-specific variable names and wording
Table 87: spending_cuts_most: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2006 | v4044 | What would you most prefer that Congress do - cut <br> domestic spending, cut military spending, raise taxes, or <br> borrow funds? |
| 2007 CC06_V4044 | What would you most prefer that Congress do - cut <br> domestic spending, cut military spending, raise taxes, or <br> borrow funds? |  |
| 2008 cc309 | What would you most prefer that Congress do - cut <br> domestic spending, cut military spending, or raise taxes? |  |
| 2010 cc328 | The federal budget is approximately 600 billion this year. If <br> the Congress were to balance the budget it would have to <br> consider cutting defense spending, cutting domestic <br> spending (such as Medicare or Social Security), or raising <br> taxes to cover the deficit. What would you most prefer that <br> Congress do - cut domestic spending, cut defense |  |
| spending, or raise taxes? |  |  |

Table 87: spending_cuts_most: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2013 | CC13_331a | If your state were to have a budget deficit this year it would have to raise taxes on income and sales or cut spending, such as on education, health care, welfare, and road construction. What would you prefer more raising taxes or cutting spending? Choose a point along the scale from 100 percent tax increases (and no spending cuts) to 100 percent spending cuts (and no tax increases). The point in the middle means that the budget should be balanced with equal amounts of spending cuts and tax increases. If you are Not sure, or don't know, please check the 'not sure' box. |
| 2014 | CC14_329a | The federal budget deficit is approximately 500 billion this year. If the Congress were to balance the budget it would have to consider cutting defense spending, cutting domestic spending (such as Medicare and Social Security), or raising taxes to cover the deficit. What would you most prefer that Congress do - cut domestic spending, cut defense spending, or raise taxes? |
| 2015 | CC15_333a | The federal budget deficit is approximately 1 trillion this year. If the Congress were to balance the budget it would have to consider cutting defense spending, cutting domestic spending (such as Medicare and Social Security), or raising taxes to cover the deficit. What would you most prefer that Congress do - cut domestic spending, cut defense spending, or raise taxes? |
| 2017 | CC17_345a | The federal budget deficit is approximately 700 billion this year. If the Congress were to balance the budget it would have to consider cutting defense spending, cutting domestic spending (such as Medicare and Social Security), or raising taxes to cover the deficit. What would you most prefer that Congress do - cut domestic spending, cut defense spending, or raise taxes? |

Note: In 2006 and 2007, this question includes a fourth response option, 'Borrow'.

### 5.7.8 spending_cuts_least

Least preferred spending cut option (1=Defense, 2=Domestic, 3=Raise taxes)
Years in data: 2006, 2007, 2008, 2010, 2011, 2012, 2013, 2014, 2015, 2017

Table 88: spending_cuts_least: Frequency table

| Year | Cut defense spending | Cut domestic spending | Raise taxes | Borrow |
| :---: | :---: | :---: | :---: | :---: |
| 2006 | 6,891 | 3,257 | 7,942 | 11,064 |
| 2007 | 2,051 | 1,208 | 2,629 | 3,822 |
| 2008 | 6,129 | 7,150 | 19,422 | 0 |
| 2010 | 8,062 | 17,016 | 29,550 | 0 |
| 2011 | 4,721 | 7,445 | 7,801 | 0 |
| 2012 | 10,493 | 19,130 | 23,876 | 0 |
| 2013 | 2,665 | 6,131 | 7,343 | 0 |
| 2014 | 11,694 | 18,583 | 25,098 | 0 |
| 2015 | 3,232 | 4,939 | 5,917 | 0 |
| 2017 | 4,035 | 6,943 | 7,010 | 0 |

Year-specific variable names and wording
Table 89: spending_cuts_least: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2006 | v4046 | What do you least want Congress to do? |
| 2007 | CC06_V4046 | Should Congress cut spending, raise taxes, or borrow... <br> What do you least want Congress to do? |
| 2008 | cc310a | What do you least want Congress to do? |
| 2010 cc329 | The federal budget is approximately 600 billion this year. If <br> the Congress were to balance the budget it would have to <br> consider cutting defense spending, cutting domestic <br> spending (such as Medicare or Social Security), or raising <br> taxes to cover the deficit. What do you least want |  |
| 2012 | CC329 | Congress to do? |
|  | Budget Balance 2 |  |
| The federal budget deficit is approximately 1 trillion this <br> year. If the Congress were to balance the budget it would <br> have to consider cutting defense spending, cutting <br> domestic spending (such as Medicare and Social <br> Security), or raising taxes to cover the deficit. What would <br> you LEAST prefer that Congress do - cut domestic <br> spending, cut defense spending, or raise taxes |  |  |

Table 89: spending_cuts_least: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2013 | CC13_331b | If the state had to raise taxes, what share of the tax increase should come from increased income taxes and what share from increased sales taxes? Choose a point along the scale from 100 percent from sales (and none from income) to 100 percent from income (and none from sales). The point in the middle means that any increase in taxes should come equally from sales and income taxes. If you are Not sure, or don't know, please check the 'not sure' box. |
| 2014 | CC14_329b | The federal budget deficit is approximately 500 billion this year. If the Congress were to balance the budget it would have to consider cutting defense spending, cutting domestic spending (such as Medicare and Social Security), or raising taxes to cover the deficit. What do you least want Congress to do? |
| 2015 | CC15_333b | The federal budget deficit is approximately 1 trillion this year. If the Congress were to balance the budget it would have to consider cutting defense spending, cutting domestic spending (such as Medicare and Social Security), or raising taxes to cover the deficit. What do you least want Congress to do? |
| 2017 | CC17_345b | The federal budget deficit is approximately 700 billion this year. If the Congress were to balance the budget it would have to consider cutting defense spending, cutting domestic spending (such as Medicare and Social Security), or raising taxes to cover the deficit. What do you least want Congress to do? |

Note: In 2006 and 2007, this question includes a fourth response option, 'Borrow'.

### 5.8 Trade

### 5.8.1 trade_china

Tariffs on goods imported from China
Years in data: 2018, 2019, 2020, 2021
Table 90: trade_china: Frequency table

| Response | 2018 | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: |
| Support | 29,290 | 9,128 | 35,793 | 16,081 |
| Oppose | 30,591 | 8,573 | 24,633 | 9,601 |

Year-specific variable names and wording
Table 91: trade_china: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2018 | CC18_331a | Tariffs on 200 billion dollars worth of goods imported from <br> China |
| 2019 | CC19_331a | 20 percent tariffs on goods imported from China |
| 2020 | CC20_338a | Tariffs on 200 billion dollars worth of goods imported from <br> China |
| 2021 | CC21_325a | 20 percent tariffs on goods imported from China |

### 5.8.2 trade_canmex_except

Tariffs on steel and aluminum EXCEPT from Canada and Mexico Years in data: 2018, 2019, 2020

Table 92: trade_canmex_except: Frequency table

| Response | 2018 | 2019 | 2020 |
| :--- | :---: | :---: | :---: |
| Support | 28,817 | 8,870 | 33,614 |
| Oppose | 31,036 | 8,799 | 26,784 |

Year-specific variable names and wording

Table 93: trade_canmex_except: Year-specific wording

| Year | Variable | Question wording |
| :---: | :--- | :--- |
| 2018 | CC18_331b | 25 percent tariffs on imported steel and 10percent on <br> imported aluminum, EXCEPT from Canada and Mexico. |
| 2019 | CC19_331b | 25 percent tariffs on imported steel and 10percent on <br> imported aluminum, EXCEPT from Canada and Mexico. |
| 2020 | CC20_338b | 25 percent tariffs on imported steel and 10percent on <br> imported aluminum, EXCEPT from Canada and Mexico. |

### 5.8.3 trade_canmex_include

Tariffs on steel and aluminum INCLUDING from Canada and Mexico Years in data: 2018, 2019, 2020, 2021

Table 94: trade_canmex_include: Frequency table

| Response | 2018 | 2019 | 2020 | 2021 |
| :--- | :---: | :---: | :---: | :---: |
| Support | 21,137 | 5,929 | 20,920 | 14,582 |
| Oppose | 38,738 | 11,706 | 39,349 | 11,099 |

Year-specific variable names and wording
Table 95: trade_canmex_include: Year-specific wording
$\left.\begin{array}{cll}\hline \text { Year } & \text { Variable } & \text { Question wording } \\ \hline 2018 & \text { CC18_331c } & \begin{array}{l}\text { 25 percent tariffs on all imported steel and 10percent on } \\ \text { imported aluminum, INCLUDING from Canada and }\end{array} \\ \text { 2019 } & \text { CC19_331c } & \begin{array}{l}\text { Mexico. }\end{array} \\ \text { 25 percent tariffs on imported steel and 10 percent on } \\ \text { imported aluminum. }\end{array}\right]$

### 5.9 Other

### 5.9.1 gaymarriage_scale

Opposition scale to gay marriage (1=Strongly support, 4=Strongly oppose) Years in data: 2006, 2007

Table 96: gaymarriage_scale: Frequency table

| Response | 2006 | 2007 |
| :--- | :---: | :---: |
| Strongly support | 5,848 | 1,958 |
| Somewhat support | 1,571 | 529 |
| Somewhat oppose | 1,462 | 506 |
| Stongly oppose | 6,937 | 2,893 |
| Don't know | 418 | 144 |

Year-specific variable names and wording
Table 97: gaymarriage_scale: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2006 | v2103 | President Bush recently spoke out in favor of a <br> Constitutional Amendment defining marriage as strictly <br> between a man and a woman. Do you support or oppose <br> a Constitutional amendment banning gay marriage? |
| 2007 CC06_V2103 | President Bush recently spoke out in favor of a <br> Constitutional Amendment defining marriage as strictly <br> between a man and a woman. Do you support or oppose <br> a Constitutional amendment banning gay marriage? |  |

### 5.9.2 gaymarriage_ban

Amendment banning gay marriage
Years in data: 2008, 2009, 2010, 2011
Table 98: gaymarriage_ban: Frequency table

| Response | 2008 | 2009 | 2010 | 2011 |
| :--- | :---: | :---: | :---: | :---: |
| Support | 13,946 | 6,067 | 23,328 | 7,942 |
| Oppose | 15,333 | 7,674 | 31,830 | 12,208 |

Year-specific variable names and wording

Table 99: gaymarriage_ban: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2008 | cc316f | Constitutional Amendment banning Gay Marriage |
| 2009 | cc09_54 | Gay Marriage |
| 2010 | $\operatorname{cc326}$ | Do you support a Constitutional Amendment banning Gay <br> Marriage? |
| 2011 | CC353 | Gay Marriage |

### 5.9.3 gaymarriage_legalize

Support for legalizing gay marriage
Years in data: 2012, 2013, 2014, 2015, 2016
Table 100: gaymarriage_legalize: Frequency table

| Response | 2012 | 2013 | 2014 | 2015 | 2016 |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Support | 28,085 | 9,308 | 32,810 | 8,248 | 41,718 |
| Oppose | 25,857 | 6,867 | 22,860 | 5,841 | 22,407 |

Year-specific variable names and wording
Table 101: gaymarriage_legalize: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2012 CC326 | Do you favor or oppose allowing gays and lesbians to <br> marry legally? |  |
| 2013 CC329 | Do you favor or oppose allowing gays and lesbians to <br> marry legally? |  |
| 2014 CC14_327 | Do you favor or oppose allowing gays and lesbians to <br> marry legally? |  |
| 2015 CC15_325 | Do you favor or oppose allowing gays and lesbians to <br> marry legally? |  |
| 2016 CC16_335 | Do you favor or oppose allowing gays and lesbians to <br> marry legally? |  |

### 5.9.4 affirmativeaction_scale

Opposition scale to affirmative action (1 = Strongly support, 7 = Strongly oppose)

Years in data: 2006, 2007
Table 102: affirmativeaction_scale: Frequency table

| Response | 2006 | 2007 |
| :--- | :---: | :---: |
| Strongly support | 4,503 | 1,030 |
| Support | 3,571 | 1,069 |
| Somewhat support | 3,839 | 1,185 |
| Neither support nor oppose | 6,630 | 1,726 |
| Somewhat oppose | 3,152 | 839 |
| Oppose | 3,909 | 1,125 |
| Strongly oppose | 10,662 | 2,999 |

Year-specific variable names and wording
Table 103: affirmativeaction_scale: Year-specific wording

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2006 v3027 | Some people think that if a company has a history of <br> discriminating against blacks when making hiring <br> decisions, then they should be required to have an <br> affirmative action program that gives blacks preference in <br> hiring. What do you think? Should companies that have <br> discriminated against blacks have to have an affirmative <br> action program? |  |
| 2007 CC06_V3027Some people think that if a company has a history of <br> discriminating against blacks when making hiring <br> decisions, then they should be required to have an <br> affirmative action program that gives blacks preference in <br> hiring. What do you think? Should companies that have <br> discriminated against blacks have to have an affirmative <br> action program? |  |  |

Note: In 2006 and 2007, this question includes a fourth response option, 'Not sure', which has been re-coded as 'NA' in this data set.

### 5.9.5 affirmativeaction

Opposition to affirmative action (1 = Support, $4=$ Oppose)
Years in data: 2008, 2009, 2010, 2011, 2012, 2013, 2014

Table 104: affirmativeaction: Frequency table

| Response | 2008 | 2009 | 2010 | 2011 | 2012 | 2013 | 2014 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Strongly support | 3,791 | 1,581 | 6,638 | 2,251 | 7,448 | 1,993 | 8,116 |
| Somewhat support | 8,883 | 3,236 | 12,985 | 4,886 | 13,797 | 4,176 | 14,161 |
| Somewhat oppose | 8,123 | 3,392 | 13,326 | 5,407 | 14,183 | 4,219 | 14,135 |
| Strongly oppose | 11,820 | 5,541 | 22,324 | 7,579 | 18,869 | 5,930 | 19,591 |

Year-specific variable names and wording
Table 105: affirmativeaction: Year-specific wording

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2008 | cc313 | Affirmative action programs give preference to racial minorities and to women in employment and college admissions in order to correct for discrimination. Do you support or oppose affirmative action? |
| 2009 | cc09_55 | Affirmative Action |
| 2010 | cc327 | Affirmative action programs give preference to racial minorities in employment and college admissions in order to correct for past discrimination. Do you support or oppose affirmative action? |
| 2011 | CC354 | Affirmative Action |
| 2012 | CC327 | Affirmative action programs give preference to racial minorities in employment and college admissions in order to correct for past discrimination. Do you support or oppose affirmative action? |
| 2013 | CC330 | Affirmative action programs give preference to racial minorities in employment and college admissions in order to correct for past discrimination. Do you support or oppose affirmative action? |
| 2014 | CC14_328 | Affirmative action programs give preference to racial minorities in employment and college admissions in order to correct for past discrimination. Do you support or oppose affirmative action? |

### 5.9.6 incometax_vs_salestax

Preference scale from 0 (increase income tax) to 100 (increase sales tax)
Years in data: 2006, 2007, 2008, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2020
![](https://cdn.mathpix.com/cropped/2024_12_11_8fae408dd24911bc1c7ag-71.jpg?height=698&width=1508&top_left_y=299&top_left_x=314)

Figure 2: Density plots for question item

Year-specific variable names and wording
Table 106: incometax_vs_salestax: Year-specific wording

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2006 | v4042 | If the state had to raise taxes, which taxes should it increase? Suppose that your state government has to raise some combination of sales taxes and individual income taxes in the coming year. What share of the tax increase should come from increased income taxes and what share from increased sales taxes? Choose a point along the scale from 100 percent from sales (and none from income) to 100 percent from income (and none from sales). The point in the middle means that any increase in taxes should come equally from sales and income taxes. If you are not sure, or don't know, please check here: [dk] |

Table 106: incometax_vs_salestax: Year-specific wording (continued)

| Year | Variable | Question wording |
| :---: | :---: | :---: |
| 2007 | CC06_V4042 | If the state had to raise taxes, which taxes should it increase? Suppose that your state government has to raise some combination of sales taxes and individual income taxes in the coming year. What share of the tax increase should come from increased income taxes and what share from increased sales taxes? Choose a point along the scale from 100 percent from sales (and none from income) to 100 percent from income (and none from sales). The point in the middle means that any increase in taxes should come equally from sales and income taxes. |
| 2008 | cc421 | If the state had to raise taxes, what share of the tax increase should come from increased income taxes and what share from increased sales taxes? Choose a point along the scale from 100 percent from sales (and none from income) to 100 percent from income (and none from sales). The point in the middle means that any increase in taxes should come equally from sales and income taxes. If you are not sure, or don't know, please check the box below... Values in range 0 to 100 |
| 2010 | cc416r | If the state had to raise taxes, what share of the tax increase should come from increased income taxes and what share from increased sales taxes? Choose a point along the scale from 100 percent from sales (and none from income) to 100 percent from income (and none from sales). The point in the middle means that any increase in taxes should come equally from sales and income taxes. If you are not sure, or don't know, please check the box below Values in range 0 to 100 |
| 2011 | CC358 | Income vs Sales Tax Rule |
| 2012 | CC416r | If the state had to raise taxes, what share of the tax increase should come from increased income taxes and what share from increased sales taxes? Choose a point along the scale from 100 percent from sales (and none from income) to 100 percent from income (and none from sales). The point in the middle means that any increase in taxes should come equally from sales and income taxes. If you are Not sure, or don't know, please check the 'not sure' box. |

Table 106: incometax_vs_salestax: Year-specific wording (continued)

| Year | Variable | Question wording |
| :--- | :--- | :--- |
| 2013 CC13_324 | If the state had to raise taxes, what share of the tax <br> increase should come from increased income taxes and <br> what share from increased sales taxes? Choose a point <br> along the scale from 100 percent from sales (and none <br> from income) to 100 percent from income (and none from <br> sales). The point in the middle means that any increase in <br> taxes should come equally from sales and income taxes. If <br> you are Not sure, or don't know, please check the 'not <br> sure' box. |  |
| If the state had to raise taxes, what share of the tax |  |  |
| increase should come from increased income taxes and |  |  |
| what share from increased sales taxes? Choose a point |  |  |
| along the scale from 100 percent from sales (and none |  |  |
| from income) to 100 percent from income (and none from |  |  |
| sales). The point in the middle means that any increase in |  |  |
| taxes should come equally from sales and income taxes. If |  |  |
| you are Not sure, or don't know, please check the 'not |  |  |
| sure' box. |  |  |


[^0]:    *PhD candidate, Department of Government, Harvard University. Thanks to Shiro Kuriwaki, Stephen Ansolabehere and Brian Schaffner for their suggestions and guidance. Please send bug reports to dagonel@g.harvard.edu, or the Github repository for the guide.
    ${ }^{1}$ Formerly the Cooperative Congressional Election Study (CCES).

