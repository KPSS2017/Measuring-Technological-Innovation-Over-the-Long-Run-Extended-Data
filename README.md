# Updates and Extension of Measuring Technological Innovation Over the Long Run. 2021. 

The main data file provides an updated series of KPST indicators for patent importance and an indicator of whether the patent constitutes a breakthrough patent. The extended data is constructed based on updating the methodology of [Kelly, B., Papanikolaou, D., Seru, A. and Taddy, M., 2021.](https://www.aeaweb.org/articles?id=10.1257/aeri.20190499). The other datasets provide the linkage file between the patent number and its CPC class, and patent-patent pairwise citations.




## Data

#### Data Version:

The version released on Sept 29, 2023 is the latest data that updates until the end of 2022.


#### Data Description:

We provide two updated data sets constructed from the paper here:

- **PatentSimilarityImportanceBreakthrough_forPost2022.csv**: Patent level panel data with patent forward (impact) and backward (novelty) similarities, importance, and breakthrough indicators from 1836 to the present 
- **PatentFullCPC_forPost2022.csv**: a dataset containing the assigned CPC technology class to all patents issued from 1836 to 2022
- **PatentPairwiseCitations_forPost2022.csv**: A dataset that contains updated citation pairs from the original paper augmented with data from the USPTO until the end of 2022


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
| CPC           | Full CPC class of a patent             |


For the patent citations data, the variable definitions are:

| Variable name | Definition                             |
| :------------ | :------------------------------------- |
| citing\_patent\_num | ID number of the citer patents |
| cited\_patent\_num  | ID number of the patents being cited  |





## Notes

1. Our patent indicators are affected by truncation lags (patents only appear in the dataset when they are issued). As a result, we compute patent importance, and breakthrough indicators until 2011 (for the 10-year forward measure) and until 2016 (for the 5-year forward measure).

2. The patent's importance measure and breakthrough indicators may not precisely match the original version of the data due to the following reasons:

    - **Changes in the raw patent text data**: The extended data is constructed using a new scrape of Google Patents database. The text of patents in Google Patent  does change for some patents, likely due to  improvements in OCR technology.
  
    - **Errors in Filing Years**: 294 patents, primarily from year 1882-1884, had the wrong filing year in the original data. These have been corrected.

    - **Improvements in Text Cleaning**: We have improved the text cleaning process by excluding a few more frequently occurring but irrelevant phrases, such as "United States Patent Office," "sheets-sheet," etc., in the raw text files. Those phrases predominantly appear in the patents from earlier years (before 1926).

3. The patent pairwise citation data is constructed from KPST pairwise citations by augmenting it with newer pairwise citation records from USPTO. Using this data, researchers can create analogous measures as our baseline indicators, by restricting the horizon over which forward citations are constructed.





## Contact:

Please contact Dimitris Papanikolaou (d-papanikolaou@kellogg.northwestern.edu) or Amit Seru (aseru@stanford.edu) for any questions regarding the data.

**Please see the paper for more information on the data. If you use these data sets, please cite [Kelly, B., Papanikolaou, D., Seru, A. and Taddy, M., 2021.](https://www.aeaweb.org/articles?id=10.1257/aeri.20190499) as the source based on which these data have been generated.**

