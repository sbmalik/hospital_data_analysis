install libraries (pandas numpy matplotlib jupyter notebooks).
dataset from http://data.bayanat.ae/en_GB/dataset/hospital-bed-by-hospital-speciality-and-medical-district.
download csv files from here.
dataset is from 2002-2008.
We have total 7 files for data analysis of hospital beds in UAE states.
The dataset contain 5713 Rows and 8 Columns.
The following columns are for the analysis of data:
    Year
    Region_EN
    Hospital_EN
    Speciality_EN
    Beds
because other cols are either unnecessary or in arabic language.

From here we start preprocessing:
1. remove additional columns and keep only cols of interest.
2. combine all dataframes.
3. change year column to date format values.
4. remove null values from data-frame.
5. convert beds to integers after removing commas from string.
6. remove all columns containing total word, so they are not able to cause problem in our analysis.
After preprocessing we have total of 4060 rows and 5 columns left.

Before forming questions, we check unique regions, hospitals and Specialities and found that we have:
 - 9 uniques regions
 - 34 specialities
 - 40 hospitals

Now coming towards data analysis we decided to answer the following questions with 3 chart types.

1. Which hospital has most beds & in which year?
ans.    we sort our dataset by beds to answer the this question & know that
        Abu-Dhabi Central Hospital has 165 beds in 2002 for the General Medicine's Speciality.

2. Show trends in number of beds for general medicine per year using line chart?
ans.    we use the filter/condition for general medicine and group by years to find values and plot a line chart.

3. What is the average number of beds per year and its spread?
ans.    we filter the total beds with per year and takes it's mean and standard deviation.

4. Show the distribution of beds among regions in 2005 using pie chart?
ans.	we first condition data for year=2005 then group it by Region, after that calculate the total beds, then use
	this data for plotting the pie chart.

5. Number of Specialities with respect to Regions of UAE using Bar plot?
ans.	first group data by regions, then extract specialities, find unique specialties, apply a lambda
	function to change the unique specialities array with its length, use this data to create a stylish
	bar plot for data visualization.
	
6. What is the highest change for Beds against Region in 2002-2008?
ans.	group data by years and regions, we have a multi-indexed data now, now extract the beds counts for every region
	create a function to join all the dataframes, change index to regions and transpose to make regions as column,
	calcuate the spread of data around mean for the value of change over the years.
	
7. What is the number of hospitals in each region?
ans.	group data by region, and get the unique values of hospitals from each region and display them.
