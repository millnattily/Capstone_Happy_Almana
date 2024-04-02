### WORLD HAPPINESS with Happy ALMANA !
(Aliya S., Marita S., Natalie M.)

In this data project, we examine the latest world happiness or subjective well-being data that serves as the basis for the  [World Happiness Report Data Dashboard](https://worldhappiness.report/data/); namely, the Jan 20, 2023 release of the Gallup World Poll (GWP), covering years  2005 to 2022.  

**The World Happiness Report** (WHR) is a partnership of Gallup (a global analytics and advisory firm, experts in conducting survey research on public opinion), the Oxford Wellbeing Research Centre, the UN Sustainable Development Solutions Network, and the WHR’s Editorial Board. The report is produced under the editorial control of the WHR Editorial Board.

The World Happiness Report reflects a worldwide demand for more attention to happiness and well-being as criteria for government policy. It reviews the state of happiness in the world today and shows how the science of happiness explains personal and national variations in happiness. <span style="font-size:0.75em;"> *https://worldhappiness.report/about/* </span> 

[**MAIN DATASET**](https://happiness-report.s3.amazonaws.com/2023/WHR+23_Statistical_Appendix.pdf)


- **Ladder of Life**-  the target  

    - *represents national average of the answer to the following question: “Please imagine a ladder, with steps numbered from 0 at the bottom to 10 at the top. The top of the ladder represents the best possible life for you and the bottom of the ladder represents the worst possible life for you. On which step of the ladder would you say you personally feel you stand at this time?”*

- **Year**


- **Country**

- **Log GDP per Capita** 
    - taken  from a number sources; primarily from World Development Indicators.  GDP for Taiwan, Syria, Palestine, Venezuela, Djibouti and Yemen are from the Penn World Table 10.01.- GDP per capita in 2022 were not yet available as of January 2023.   Penn World Table,  OECD Economic Outlook, World Bank's Global Economic Prospects.  The WHR extended the GDP-per-capita times series from 2021 to 2022 data for 2022 using country-specific forecasts of real GDP growth in 2022 frm the OECD Economic Outlook No. 112 (November 2022) and if missing, then  forecasts rom World Bank’s Global Economic Prospects (Last Updated: 01/10/2023). The GDP growth forecasts are adjusted for population growth with the subtraction of 2020-21 population growth as the projected 2021-22 growth. A few countries/territories have their GDP figures from the Penn World Table that ends in 2019. We derive their 2020-2022 GDP values based on the 2019 values and the projected growth rates if they are available.

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

- **Institutional trust**:   [_source: Statistical Appendix 1 for Chapter 2 of World Happiness Report 2021 (pp 3)_ ](https://happiness-report.s3.amazonaws.com/2021/Appendix1WHR2021C2.pdf)
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

### More Features from Other Sources:

* **Population Density** based on [Kaggle data](https://worldpopulationreview.com/country-rankings/hdi-by-country)

* **Quality of Life Rankings** [from Numbeo](https://www.numbeo.com/quality-of-life/rankings_by_country.jsp)

### Features from United Nations
 _source:_ [UN Human Development Reports](https://hdr.undp.org/sites/default/files/2021-22_HDR/hdr2021-22_technical_notes.pdf) and the data table titled [_"All composite indices and components time series (1990-2022)"_](https://hdr.undp.org/data-center/documentation-and-downloads) 

* [**Human Development Index (HDI)**](https://hdr.undp.org/data-center/human-development-index#/indicies/HDI)  

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
        
        

##### **USEFUL DEFINITIONS**:
**GDP**
Gross domestic product measures the value of goods and services produced within a country; the measurement includes national output, expenditures, and income.

**Gross National Income (GNI)** is a measurement of a country's income. It includes all the income earned by a country's residents, businesses, and earnings from foreign sources. Income is defined as all employee compensation plus investment profits.

**GNI** also includes any product taxes not already counted, minus subsidies. It only counts income earned from residents who work abroad and does not count income earned by foreigners located in the country. Like GDP, it also does not include the shadow or black economy.

**GNI equals** GDP plus wages, salaries, and property income of the country's residents earned abroad and at home. It also includes net taxes and subsidies receivable from abroad, according to the Organization for Economic Cooperation and Development.

**GNI per capita** is a measurement of income to the number of people in the country. It compares the GNI of countries with different population sizes and standards of living. However, GNI does not account for costs of living or subsistence levels—which means that while providing good information about the income levels of the people in a country, it should be used in context with other measurements to grasp a full picture of the income and purchasing power a country's citizens have.

**GNI as a Comparison Tool**
    
The World Bank provides GNI data for all countries. To compare incomes among nations, it removes the effects of currency exchange rates by converting everything to the U.S. dollar using **purchasing power parity (PPP)**.
The World Bank. "Why Use GNI Per Capita to Classify Economies Into Income Groupings?"


The **problem with the PPP method**, though, is that it converts all goods and services in a country to what it would cost in the United States. The method works well for products like McDonald's hamburgers that are sold across the world—but does a poor job of estimating the value of goods not sold in America.