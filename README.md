# Visitors to Ug National Parks Analysis

### Project Overview

This project aims to provide insights into the performance of Uganda national parks by analyzing "Number of visitors to National Parks" data
between 2015 to 2019. We want to look at trend and the contribution of each national park.

[View Final dashboard here](https://app.powerbi.com/view?r=eyJrIjoiOTQ3OTk4YWEtMzA2MC00YTNkLWJiMDMtZDk5MGJkN2U3NDYxIiwidCI6ImY0OTU4NDAzLTgyZGEtNDYxNC1hNjk2LTI3M2VkMWI4ZTU5OSJ9)


### Data Source

The dataset used is Visitors_to_National_Parks_(Citizens_and_Foreigners),_2015_–_2019, downloaded from the Uganda Bureau of Statisitcs (UBOS) website.
[Download here](https://www.ubos.org/wp-content/uploads/statistics/Visitors_to_National_Parks_(Citizens_and_Foreigners),_2015_%E2%80%93_2019.xlsx)


### Tools used

#### PowerBi

- Power query - Extracting & Transforming data.
- DAX formulas - Calculations & Analysis.

### Data Preparation / Cleaning Process

The following tasks were performed:

1. Loaded data into power query
2. Removed Top Rows (1)
3. Promoted headers.
4. Filtered "National Parks" column to removed nulls
5. Unpivoted other columns
6. Renamed columns and assigned the right data types.

### Exploratory Data Analysis

This involved exploring the data to find answers questions to the questions:-
- What was the overall trend of number of visitors to parks for the period 2015 to 2019
- What was the Annual average no. of visitors.
- Was there growth between 2015 to 2019.
- Which parks had the highest number of visitors.

### The Data Analysis Process
Used dax calculations to create aggregatation measesures such as:

- **No. of National parks**
```Parks = COUNT('National Parks'[National Parks])```

-  **No. of visitors**
```No. of Visitors = SUM(FactTable[Total Visitors])```

- **Annual Avg No. of visitors**
```Avg.No. of Visitors per Year = DIVIDE([No. of Visitors],5)```

- **YoY% Growth**
```YoY% Change = 
VAR Previous_Year=
    CALCULATE([No. of Visitors],DATEADD('Calendar'[Date],-1,YEAR))
RETURN
    DIVIDE(([No. of Visitors]-Previous_Year),Previous_Year)
```

### Findings

The findings are summarised as below;

- The of visitors in general grew by 30% over from 20215 to 2019 averaging 280 visitors per year.
- Murchision Falls and Queen Elizabeth had the highest no. of visitors.
- There is slight fall in 2019 which could be attributed to the covid 19 movement restrictions.

[Visitors in Uganda National Parks Report.pdf](https://github.com/user-attachments/files/20188549/Visitors.in.Uganda.National.Parks.Report.pdf)

### Recommendations

- Invest in intentional advertising and marketing for stand out parks like the Rwenzoris and Mgahinga Gorilla.
- Invest in vlogs and blogs showcasing the uniqeness of each of these national parks.
- Invest in infrastructure to accomodate unforgettable experiences of visitors while at the parks.
- Research on the least performing parks like Semilik, the Rwenzori mountains, Elgon and Mgahinga Gorilla should be carried out to find out why they are not being preferred as tourist destinations.

### Limitations
The data set was not exhaustively detialed as it lacked attributes like categories of visitors, Nationality, Date (to track monthly performance).
