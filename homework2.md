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
     
<h5>f.What dtypes are the variables/columns? What does this mean?</h5>

The data that falls under the country code are floats. The data within the year column are integers. This means that python/pandas is classifying each of the variables within a dataframe based on their column and content.

    In[4]:
    weo.dtypes
    
    Out[4]: 
    BRA     float64
    JPN     float64
    USA     float64
    Year      int64
    dtype: object
    
<h5>g. Challenging. What are each of these expressions? What type?</h5>

     weo['Year'] ## Pulls the Year column as a Series
     weo[['Year']] ## Pulls the Year column as a DataFrame
     weo[[3]] ## Pulls the Year column as a Dataframe. The 3 refers to the column number it is, starting with 0.
     
<h5> Challenging. Find and apply a method to convert weo[’Year’] to type float. Hint: The method begins with the letter a.</h5>

    In [13]:
    weo['Year'] = weo['Year'].astype('float')

    In [14]:
    weo['Year']
    
    Out[14]: 
    0    2008.0
    1    2009.0
    2    2010.0
    3    2011.0
    4    2012.0
    5    2013.0
    6    2014.0
    Name: Year, dtype: float64

<h5> (i) Describe the result of the statement t = weo.tail(3). What kind of object is t? What does it look like? </h5>
