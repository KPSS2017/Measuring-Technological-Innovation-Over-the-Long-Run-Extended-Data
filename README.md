# Updates and Extension (till 2022) from Measuring Technological Innovation Over the Long Run. 2021. 

The primary data provides an updated series of KPST measures for patent similarity, patent importance, breakthrough indicator, patent filing and issuance years, as well as forward citations, spanning 1836-2022 following [Kelly, B., Papanikolaou, D., Seru, A. and Taddy, M., 2021.](https://www.aeaweb.org/articles?id=10.1257/aeri.20190499). The other datasets provide the linkage file between the patent number and its CPC class, and patent-patent pairwise citations.



## Data

#### Data Version:

The version released on Sept 29, 2023 is the latest data that updates until the end of 2022.


#### Data Description:

We provide two updated data sets constructed from the paper here:

- **PatentSimilarityImportanceBreakthrough_forPost2022.csv**: Patent level panel data with patent similarities, importance, and breakthrough indicators from 1836 to 2022
- **PatentFullCPC_forPost2022.csv**: Patent-CPC class match data spanning from 1836 to 2022
- **PatentPairwiseCitations_forPost2022.csv**: Patent citation pairs up to 2022


For the patent-level panel data, the variable definitions are:

| Variable name   | Definition                                                |
| :-------------- | :-------------------------------------------------------- |
| patent\_num            | Patent ID number                                          |
| issue\_year      | Year when a patent is issued (yyyy)                       |
| filed\_year      | Year when a patent is filed (yyyy)                        |
| fsim01          | Forward 1-year aggregate patent similarity                |
| fsim25          | Forward 2-5 years aggregate patent similarity             |
| fsim610         | Forward 6-10 years aggregate patent similarity            |
| bsim5           | Backward 5-year aggregate patent similarity    |
| lqsim05         | 5-year importance (log ratio of fsim5/bsim5)              |
| lqsim010        | 10-year importance (log ratio of fsim10/bsim5)            |
| fcitALL         | Total Forward citations till 2022                        |
| bk\_p90\_alqsim05 | Breakthrough Indicator (based on 5-yr importance)         |
| bk\_p90\_alqsim010| Breakthrough Indicator (based on 10-yr importance)        |



For the patent-CPC class match data, the variable definitions are:

| Variable name | Definition                             |
| :------------ | :------------------------------------- |
| patent\_num          | Patent ID number                       |
| CPC           | Full CPC class of patent             |


For the patent citations data, the variable definitions are:

| Variable name | Definition                             |
| :------------ | :------------------------------------- |
| citing\_patent\_num | ID number of the citer patents |
| cited\_patent\_num  | ID number of the patents being cited  |





## Notes

1. The 2022 updated sample contains 11,474,838 patents, covering the period from 1836 to 2022. Out of these, 11,899 patents do not have CPC records in the patent-CPC linkage file. The original KPST(2021) sample consists of 9,072,704 patents from 1836 to 2015.

2. Given the specified forward and backward year ranges, our data covers patents‘ 10-year importance measures from 1840 to 2011 and 5-year importance measures from 1840 to 2016. 

3. The patent's importance measure and breakthrough indicators may not precisely match the original version of the data in the paper due to the following reasons:

  - **Text source**: We download the text from Google Patents again, and Google Patent texts change as improvements in OCR technology.
  
  - **Year mismatch**: We find that 294 patents have the wrong filing years (filed year > issued year) in the original patent-year linkage file [PatentChar.dta](https://github.com/KPSS2017/Measuring-Technological-Innovation-Over-the-Long-Run-Replication-Kit/blob/master/input_data/PatentChar.dta.zip). We modify this by assuming their filing years identical to their issued years, given those mismatched patents primarily from year 1882-1884. The updated information on the patent's filing and issued years are also included in ./data/**PatentSimilarityImportanceBreakthrough_forPost2022.csv**.
  
  - **Text cleaning**: We improve the text cleaning process by excluding a few more frequently occurring but irrelevant phrases, such as "United States Patent Office," "sheets-sheet," etc., in the raw text files. Those phrases predominantly appear in the patents from earlier years (before 1926).

4. The patent pairwise citation data is constructed from KPST pairwise citations by augmenting it with newer pairwise citation records from USPTO. The forward citation data can be further constructed by counting the forward citations given year horizons, based on the gap of filing years between the citing and cited patents, as referred to the original KPST forward citation file [PatentCitations.dta](https://github.com/KPSS2017/Measuring-Technological-Innovation-Over-the-Long-Run-Replication-Kit/blob/master/input_data/PatentCitations.dta.zip).





## Contact:

Please contact Dimitris Papanikolaou (d-papanikolaou@kellogg.northwestern.edu) or Amit Seru (aseru@stanford.edu) for any questions regarding the data.

**Please see the paper for more information on the data. If you use these data sets, please CITE this paper as the data source.**
