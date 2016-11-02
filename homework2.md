<h3>SUNIL MURTI </h3>
<h2>Data Bootcamp: Code Practice #3</h2>

<h5>1.  Enter and run this code in Spyder to produce the dataframe.

The numbers are GDP per person in thousands of US dollars, 2008 to 2014, variable PPPPC in the IMF’s World Economic Outlook database.</h5>

<h5>a. Explain the import statement.</h5>
The import statment is loading the open-source Panda library into Python and renaming it ''''pd'''' — as a way of shortening our commands.

<h5>b. What type of object is data?</h5>

Data is a dictionary made up of 4 keys with 7 values each.

<h5>c. Why does the last line have pd prior to the DataFrame function? </h5>

The last line has pd. prior to DataFrame function, as this function is part of the Pandas library. If we had not
changed the name in the first import line, the function would have been pandas.DataFrame.

<h5>d. What type of object is weo?</h5>

weo is a DataFrame— that was built from dictionary "data".

<h5>e. How many rows does it have? Columns? </h5>
WEO has 4 columns and 7 rows.

    In[3]:
    weo
    
    Out[3]: 
     BRA    JPN    USA  Year
     0  13.37  33.43  48.30  2008
     1  13.30  31.83  46.91  2009
     2  14.34  33.71  48.31  2010
     3  15.07  34.29  49.72  2011
     4  15.46  35.60  51.41  2012
     5  15.98  36.79  52.94  2013
     6  16.10  37.39  54.60  2014
     
<h5>What dtypes are the variables/columns? What does this mean?</h5>
