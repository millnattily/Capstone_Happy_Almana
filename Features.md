# WORLD HAPPINESS with Happy ALMANA !
(Aliya S., Marita S., Natalie M.)
### FEATURES AND BACKGROUND INFO


In this data project, we examine the latest world happiness (or subjective well-being data) that serves as the basis for the  [World Happiness Report Data Dashboard](https://worldhappiness.report/data/); namely, the Jan 20, 2023 release of the Gallup World Poll (GWP) that covers the years  2005 to 2022.  

**The World Happiness Report** (WHR) is a partnership of Gallup (a global analytics and advisory firm, experts in conducting survey research on public opinion), the Oxford Wellbeing Research Centre, the UN Sustainable Development Solutions Network, and the WHR’s Editorial Board. The report is produced under the editorial control of the WHR Editorial Board.

The World Happiness Report reflects a worldwide demand for more attention to happiness and well-being as criteria for government policy. It reviews the state of happiness in the world today and shows how the science of happiness explains personal and national variations in happiness. <span style="font-size:0.75em;"> *https://worldhappiness.report/about/* </span> 

[**MAIN DATASET**](https://happiness-report.s3.amazonaws.com/2023/WHR+23_Statistical_Appendix.pdf)


- **Ladder of Life**-  the target  

    - *represents national average of the answer to the following question: “Please imagine a ladder, with steps numbered from 0 at the bottom to 10 at the top. The top of the ladder represents the best possible life for you and the bottom of the ladder represents the worst possible life for you. On which step of the ladder would you say you personally feel you stand at this time?”*

- **Year**


- **Country**

- **Log GDP per Capita** 
    - taken  from a number sources; primarily from World Development Indicators.  GDP for Taiwan, Syria, Palestine, Venezuela, Djibouti and Yemen are from the Penn World Table 10.01.- GDP per capita in 2022 were not yet available as of January 2023.   Penn World Table,  OECD Economic Outlook, World Bank's Global Economic Prospects.  The WHR extended the GDP-per-capita times series from 2021 to 2022 data for 2022 using country-specific forecasts of real GDP growth in 2022 frm the OECD Economic Outlook No. 112 (November 2022) and if missing, then  forecasts rom World Bank’s Global Economic Prospects (Last Updated: 01/10/2023). The GDP growth forecasts are adjusted for population growth with the subtraction of 2020-21 population growth as the projected 2021-22 growth. A few countries/territories have their GDP figures from the Penn World Table that ends in 2019. We derive their 2020-2022 GDP values based on the 2019 values and the projected growth rates if they are available.
- ** Healthy Life Expectancy** Average number of years that a person can expect to live in "full health" by taking into account years lived in less than full health due to disease and/or injury.Healthy Life Expectancy (HLE). Healthy life expectancies at birth are based on the data extracted from the World Health Organization’s (WHO) Global 1 Health Observatory data repository (Last updated: 2020-12-04). The data at the source are available for the years 2000, 2010, 2015 and 2019. To match this report’s sample period (2005-2021), interpolation and extrapolation are used.
- **Social Support** 
    - or *"having someone to count on in times of trouble."* is the national average of the binary responses (either 0 or 1)  to the Gallup World Poll (GWP) question 
    
            If you were in trouble, do you have 
            relatives or friends you can count on 
            to help you whenever you need them, 
            or not?


-  **Freedom to Make Life Choices** 
    - is the national average of the binary responses (either 0 or 1)  to the  question 
    
            Are you satisfied or dissatisfied 
            with your freedom to choose what 
            you do with your life?
    
- **Generosity**
    -  is the residual of regressing national average of response on GDP per capita to the GWP question 
    
            Have you donated money to a charity 
            in the past month? 
            
- **Positive Affect**  Positive affect is defined as **the average of three positive affect measures** in GWP: laugh, enjoyment and doing interesting things in the Gallup World Poll waves 3-7. These measures are the responses to the following three questions, respectively: **“Did you smile or laugh a lot yesterday?”, and “Did you experience the following feelings during A LOT OF THE DAY yesterday? How about Enjoyment?”, “Did you learn or do something interesting yesterday?”**

- **Negative affect**  Negative affect is defined as the **average of three negative affect measures** in GWP. They are worry, sadness and anger, respectively the responses to “Did you experience the following feelings during A LOT OF THE DAY yesterday? How about Worry?”, “Did you experience the following feelings during A LOT OF THE DAY yesterday? How about Sadness?”, and “Did you experience the following feelings during A LOT OF THE DAY yesterday? How about Anger?”

- **Corruption Perception** 
    -  overall perception is measure (the average of the two 0-or-1 response) of national average for the survey responses to two questions
     
            -Is corruption widespread throughout 
            the government or not?  

            -Is corruption widespread within 
            businesses or not? 
     
     
- **Gini of Household Income Reported in Gallup, by wp5-year**
    
    - Gini of household income reported in the Gallup World Poll *(Data for Table 2.1, World Happiness Report 2020)*(variable name
    giniIncGallup). 
    - The income variable is described in Gallup’s [Worldwide Research: Methodology and Codebook, October 2021,(*pp 17-18*)](https://news.gallup.com/poll/165404/world-poll-methodology.aspx) 
    as “Household Income International Dollars [...] To calculate income, respondents
    are asked to report their household income in local currency. Those respondents
    who have difficulty answering the question are presented a set of ranges in local
    currency and are asked which group they fall into. Income variables are created by converting local currency to International Dollars (ID) using purchasing
    power parity (PPP) ratios.” 
    The gini measure is generated using STATA command ineqdec0 by WP5-year ( Stata module to calculate inequality indices with decomposition by subgroup) with sample weights. Observations whose recorded
    income value is 0 or 1 are dropped before the gini calculation. A Gini coefficient(index) of 0 reflects perfect equality, where all income or wealth values are the same, while a Gini coefficient of 1 (or 100%) reflects maximal inequality among values, a situation where a single individual has all the income while all others have none.

- **GINI index from the World Bank** (variable name giniIncWB and giniIncWBavg) from the World Development Indicators. The variable labeled at the
source as “GINI index (World Bank estimate)”, series code “SI.POV.GINI”.

    - The Gini index measures the extent to which the distribution of income or consumption among individuals or households within an economy deviates from a perfectly equal distribution. 
    - A Gini index of 0 represents perfect equality, while an index of 100 implies perfect inequality. [*(Metadata Glossary, The World Bank)*](https://databank.worldbank.org/metadataglossary/world-development-indicators/series/SI.POV.GINI#:~:text=The%20Gini%20index%20measures%20the,of%20100%20implies%20perfect%20inequality.)
According to the source, the data source is “World Bank, Development Research Group. Data are based on primary household survey data obtained from
government statistical agencies and World Bank country departments.” The
variable giniIncWB is an unbalanced panel of yearly index. The data availability is patchy at the yearly frequency. The variable giniIncWBavg is the
average of giniIncWB starting from year 2000. The average does not imply
that a country has the gini index in all years since then. In fact, most do not.

- **Institutional trust**:   [<span style="font-size:0.75em;">source, Statistical Appendix 1 for Chapter 2 of World Happiness Report 2021 (pp 3)</span>](https://happiness-report.s3.amazonaws.com/2021/Appendix1WHR2021C2.pdf)
    - Represents the first principal component of the following five measures:
        - confidence in the national government
        - confidence in the judicial system and
            courts, 
        - confidence in the honesty of          elections, 
        - confidence in the local police force,
and 
        - perceived corruption in business. 
    - This principal component is then used to
create a binary measure of high institutional trust using the 75th percentile in
the global distribution as the cutoff point; this way a country whose population
tends to have a low level of institutional trust in the global distribution will
have a low average institutional trust at the national level. This measure is
not available for all countries since not all surveys in all countries ask all of the
questions that are used to derive the principal component.

### Additional Features from Other Sources:

* **Population Density** based on [Kaggle data](https://worldpopulationreview.com/country-rankings/hdi-by-country)

* **Quality of Life Indices** [from Numbeo](https://www.numbeo.com/quality-of-life/rankings_by_country.jsp)

    - **Quality of Life Index** (higher is better, *WHICH WE DIDN'T USE* due to its overlap with other features) is an estimation of the overall quality of life by using an empirical formula that takes into account the following factors:

    - [**Purchasing Power Index**](https://www.numbeo.com/cost-of-living/cpi_explained.jsp) (higher is better) This index indicates the relative purchasing power in a given city based on the average net salary. A domestic purchasing power of 40 means that residents with an average salary can afford, on average, 60% less goods and services compared to residents of New York City with an average salary.
    - [**Pollution Index**](https://www.numbeo.com/pollution/indices_explained.jsp)(lower is better) The data in this section is derived from surveys conducted by visitors to our website. Questions in these surveys are designed to be similar to many scientific and government surveys.

        Each entry in the survey is assigned a number within the range of -2 to +2, where -2 represents a strongly negative perception and +2 represents a strongly positive perception.

        To ensure data accuracy, we have implemented filtering measures to identify and exclude potential spam from our calculations. Our algorithms identify users who exhibit spam-like behavior and their inputs are not considered in the calculations. This helps maintain the integrity of the data and provide reliable results.

        To make survey results easier to interpret for our users, we present them on a scale ranging from 0 to 100. This scale allows for a clear and straightforward understanding of the data, enhancing user experience and facilitating meaningful comparisons.

        Our current index, which is continuously updated, is generated using data up to 36 months old. We carefully select cities for inclusion in the index based on a minimum number of contributors to ensure statistical significance. Additionally, our semiannual index is calculated twice a year by incorporating the latest data into the historical view.

        Most of our data are based on perceptions (opinions) from visitors of this website. For the pollution section, we include relevant data from World Health Organization and other institutions if we find it helpful. Please consult our Terms of use for details.

        Pollution Index provides an estimation of overall pollution levels in cities worldwide. It considers factors such as air and water pollution, garbage disposal, cleanliness, noise and light pollution, green spaces, and comfort in relation to pollution. Numbeo assigns the highest weight to air pollution, followed by water pollution and accessibility, which are considered the two primary pollution factors. Other types of pollution receive a smaller weight in the index.

        Pollution Exp Scale uses an exponential function to show very high numbers for very polluted cities and very low numbers for unpolluted cities.

        Actual formulas to calculate indices are subject to change. At this moment, quite complex empirical formulas are used. Those formulas, as written in the Java programming language, are as follows:
    - **House Price to Income Ratio** (lower is better)
    - [**Cost of Living Index**](https://www.numbeo.com/cost-of-living/cpi_explained.jsp) (lower is better) the cost of living indices provided on this website are relative to New York City (NYC), with a baseline index of 100% for NYC. Here's a breakdown of each index and its meaning:

        Cost of Living Index (Excl. Rent): This index indicates the relative prices of consumer goods like groceries, restaurants, transportation, and utilities. It excludes accommodation expenses such as rent or mortgage. For instance, a city with a Cost of Living Index of 120 is estimated to be 20% more 
        expensive than New York City (excluding rent).

        Cost of Living Index is calculated based on our estimated average expenses for a four-person family in a specific city. Please note that the weights used in our calculation may change over time. Currently, the weights used are as follows: [link](https://www.numbeo.com/common/motivation_and_methodology.jsp)

    - [**Crime Index**](https://www.numbeo.com/crime/indices_explained.jsp) (lower is better) or its converse **Safety Index** 
        
        About Crime Indices At This Website
        The data in this section is derived from surveys conducted by visitors to our website. Questions in these surveys are designed to be similar to many scientific and government surveys.

        Each entry in the survey is assigned a number within the range of -2 to +2, where -2 represents a strongly negative perception and +2 represents a strongly positive perception.

        To ensure data accuracy, we have implemented filtering measures to identify and exclude potential spam from our calculations. Our algorithms identify users who exhibit spam-like behavior and their inputs are not considered in the calculations. This helps maintain the integrity of the data and provide reliable results.

        To make survey results easier to interpret for our users, we present them on a scale ranging from 0 to 100. This scale allows for a clear and straightforward understanding of the data, enhancing user experience and facilitating meaningful comparisons.

        Our current index, which is continuously updated, is generated using data up to 36 months old. We carefully select cities for inclusion in the index based on a minimum number of contributors to ensure statistical significance. Additionally, our semiannual index is calculated twice a year by incorporating the latest data into the historical view.

        Crime Index is an estimation of the overall level of crime in a given city or country. We consider crime levels lower than 20 as very low, crime levels between 20 and 40 as low, crime levels between 40 and 60 as moderate, crime levels between 60 and 80 as high, and crime levels higher than 80 as very high.

        Safety index is, on the other way, quite the opposite of the crime index. If the city has a high safety index, it is considered very safe.

        The Crime Index takes into account survey responses about:

        General perception of crime levels
        Perceived safety: Survey responses from residents and visitors regarding their feelings of safety while walking during daylight and at night.
        Concerns about specific crimes: Survey questions about worries regarding mugging, robbery, car theft, physical attacks by strangers, harassment in public places, and discrimination based on factors like skin color, ethnicity, gender, or religion.
        Property crimes: Assessment of the extent of property-related crimes, such as burglary, theft, vandalism, etc.
        Violent crimes: Evaluation of the perception of violent crimes, including assault, homicide, sexual offenses, etc.
        It's important to note that the Crime Index provided by Numbeo is based on user-contributed data and perceptions, which may differ from official government statistics. The index serves as a comparative tool to assess the relative safety of different cities or countries, helping individuals make informed decisions and understand the crime landscape in specific locations.

        Is this much less accurate than governmental statistics?

        In some countries, governments have detailed statistics based on the number of reported crimes per capita. While these surveys are usually particularly good for comparing crime between two cities within the same country, they may not be as suitable for cross-country comparisons due to the following reasons:

        People in some countries are more likely to report a crime than in other countries.
        Data could be forged by governmental institutions.
        Data might not available in many parts of the world.
        Actual formulas to calculate indices are subject to change. At this moment, quite complex empirical formulas are used. Those formulas, as written in the Java programming language, are as follows:



    - [**Health Care Index**](https://www.numbeo.com/health-care/indices_explained.jsp) (higher is better) Health Care Index is an estimation that evaluates the overall quality of the healthcare system, including factors such as healthcare professionals, equipment, staff, doctors, and costs. It provides an assessment of the healthcare infrastructure, services, and resources available in a specific location.

        Health Care Exp Index is designed to reflect the quality of a healthcare system by emphasizing the positive aspects more significantly through an exponential increase while also emphasizing the native aspects more significantly.

        The data in this section is derived from surveys conducted by visitors to our website. Questions in these surveys are designed to be similar to many scientific and government surveys.

        Each entry in the survey is assigned a number within the range of -2 to +2, where -2 represents a strongly negative perception and +2 represents a strongly positive perception.

        To ensure data accuracy, we have implemented filtering measures to identify and exclude potential spam from our calculations. Our algorithms identify users who exhibit spam-like behavior and their inputs are not considered in the calculations. This helps maintain the integrity of the data and provide reliable results.

        To make survey results easier to interpret for our users, we present them on a scale ranging from 0 to 100. This scale allows for a clear and straightforward understanding of the data, enhancing user experience and facilitating meaningful comparisons.

        Our current index, which is continuously updated, is generated using data up to 36 months old. We carefully select cities for inclusion in the index based on a minimum number of contributors to ensure statistical significance. Additionally, our semiannual index is calculated twice a year by incorporating the latest data into the historical view.
    - **Traffic Commute Time Index** (lower is better)
    - **Climate Index** (higher is better)

### Features from United Nations Human Development Reports
 <span style="font-size:0.75em;">source:[UN Human Development Reports](https://hdr.undp.org/sites/default/files/2023-24_HDR/hdr2023-24_technical_notes.pdf) and the data table from link titled [_"All composite indices and components time series (1990-2022)"_](https://hdr.undp.org/data-center/documentation-and-downloads) </span>

 * **Mean Years of Schooling** Mean years of schooling: Average number of years of education received by people ages 25 and older, converted from education attainment levels using official durations of each level. [*("Table 1: Human Development Index and components": HDR23-24_Statistical_Annex_HDI_Table)*](https://hdr.undp.org/data-center/documentation-and-downloads)

* [**Human Development Index (HDI)**: *("All composite indices and components time series (1990-2022) Metadata")*](https://hdr.undp.org/data-center/human-development-index#/indicies/HDI) 

    summary measure of average achievement in 3 key dimensions of human development: 

    - long and healthy life, 
    - being knowledgeable and 
    - having a decent standard of living. 

    <u>Scores for the three HDI dimension indices</u> are then aggregated into a composite index using geometric mean. 

    Calculation of geometric mean =
            $$ ^n\sqrt{x_1 * x_2 *... x_n} $$   or $$ (x_1 * x_2 * x_3)^{1/3} $$  in the HDI case.


    * Health dimension = life expectancy at birth, 
    * Education dimension = mean of years of schooling for adults  25 years or older and expected years of schooling for children of school entering age. 
    * Standard of living dimension is measured by gross national income per capita.  HDI uses the logarithm of income, to reflect the diminishing importance of income with increasing GNI. 
        
        

### **ABOUT GDP, GNI & PPP** 
<span style="font-size:0.75em;"> source, https://www.thebalancemoney.com/gross-national-income-4020738</span>


**GDP**
Gross domestic product measures the value of goods and services produced within a country; the measurement includes national output, expenditures, and income.

**Gross National Income (GNI)** is a measurement of a country's income. It includes all the income earned by a country's residents, businesses, and earnings from foreign sources. Income is defined as all employee compensation plus investment profits.

**GNI** also includes any product taxes not already counted, minus subsidies. It only counts income earned from residents who work abroad and does not count income earned by foreigners located in the country. Like GDP, it also does not include the shadow or black economy.

**GNI =** GDP plus wages, salaries, and property income of the country's residents earned abroad and at home. It also includes net taxes and subsidies receivable from abroad, according to the Organization for Economic Cooperation and Development.

**GNI per capita** is a measurement of income to the number of people in the country. It compares the GNI of countries with different population sizes and standards of living. However, GNI does not account for costs of living or subsistence levels—which means that while providing good information about the income levels of the people in a country, it should be used in context with other measurements to grasp a full picture of the income and purchasing power a country's citizens have.

**GNI as a Comparison Tool**
    
The World Bank provides GNI data for all countries. To compare incomes among nations, it removes the effects of currency exchange rates by converting everything to the U.S. dollar using **purchasing power parity (PPP)**.
The World Bank. "Why Use GNI Per Capita to Classify Economies Into Income Groupings?"


The **problem with the PPP method**, though, is that it converts all goods and services in a country to what it would cost in the United States. The method works well for products like McDonald's hamburgers that are sold across the world—but does a poor job of estimating the value of goods not sold in America.

