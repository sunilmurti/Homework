<h3>SUNIL MURTI </h3>
<h2>Data Bootcamp: Code Practice #3</h2>

<h5>1.  Enter and run this code in Spyder to produce the dataframe.

The numbers are GDP per person in thousands of US dollars, 2008 to 2014, variable PPPPC in the IMF’s World Economic Outlook database.</h5>

<h5>a. Explain the import statement.</h5>
The import statment is loading the open-source Panda library into Python and renaming it pd — as a way of shortening our commands.

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
         BRA    JPN    USA   Year
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
     
<h5>h. Challenging. Find and apply a method to convert weo[’Year’] to type float. Hint: The method begins with the letter a.</h5>

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

<h5>i. Describe the result of the statement t = weo.tail(3). What kind of object is t? What does it look like? </h5>

The statement created a new DataFrame using the LAST 3 or 3 rows at the tail of the table. In this case, Rows 4, 5, 6. 
t is a data frame. It looks like a shortened version or a subsect of dataframe weo.

<h5>j. How would you create a new dataframe that consists of the first 4 rows of weo?</h5>

    In[18]:
    weo.head(4)
    
    Out[18]: 
        BRA    JPN    USA    Year
    0  13.37  33.43  48.30  2008.0
    1  13.30  31.83  46.91  2009.0
    2  14.34  33.71  48.31  2010.0
    3  15.07  34.29  49.72  2011.0

<h5>k. What type of object is weo[’BRA’]?</h5>

weo['BRA'] is a series.

    In[22]:
    type(weo['BRA'])
    
    Out[22]: pandas.core.series.Series
    
<h5>l. Create a new variable equal to the ratio of Brazil’s GDP per capita to Japan’s and add it to the DataFrame.</h5>

    In[23]: weo['GDP_BRA/JPN'] = weo['BRA']/weo['JPN']

    In[24]: weo
    
    Out[24]: 
        BRA    JPN    USA    Year     GDP_BRA/JPN
    0  13.37  33.43  48.30  2008.0     0.399940
    1  13.30  31.83  46.91  2009.0     0.417845
    2  14.34  33.71  48.31  2010.0     0.425393
    3  15.07  34.29  49.72  2011.0     0.439487
    4  15.46  35.60  51.41  2012.0     0.434270
    5  15.98  36.79  52.94  2013.0     0.434357
    6  16.10  37.39  54.60  2014.0     0.430596


<h5>m. Challenging. Use the drop() method to eliminate this (new) variable from the dataframe.</h5>

    In[29]:weo = weo.drop(['GDP_BRA/JPN'], axis=1)

    In[30]:weo
    
    Out[30]: 
        BRA    JPN    USA    Year
    0  13.37  33.43  48.30  2008.0
    1  13.30  31.83  46.91  2009.0
    2  14.34  33.71  48.31  2010.0
    3  15.07  34.29  49.72  2011.0
    4  15.46  35.60  51.41  2012.0
    5  15.98  36.79  52.94  2013.0
    6  16.10  37.39  54.60  2014.0

<h5>n. What are weo’s row and column labels?</h5>

Column Labels = BRA, JPN, USA, Year

Row Labels = 0, 1, 2, 3, 4, 5, 6

<h5> o. Set the index equal to the Year variable. </h5>

    In [38]: weo_year = weo.set_index('Year')

    In [38]: weo_year
    
    Out[38]: 
          BRA    JPN    USA
    Year                       
    2008.0  13.37  33.43  48.30
    2009.0  13.30  31.83  46.91
    2010.0  14.34  33.71  48.31
    2011.0  15.07  34.29  49.72
    2012.0  15.46  35.60  51.41
    2013.0  15.98  36.79  52.94
    2014.0  16.10  37.39  54.60
    
<h5>p. Change the names of the other variables to Brazil, Japan, and United States.</h5>


    In [39]:weo_year.columns = ['Brazil', 'Japan', 'United States']

    In [40]: weo_year
    
    Out[40]: 
            Brazil  Japan      United States
    Year                                
    2008.0   13.37  33.43          48.30
    2009.0   13.30  31.83          46.91
    2010.0   14.34  33.71          48.31
    2011.0   15.07  34.29          49.72
    2012.0   15.46  35.60          51.41
    2013.0   15.98  36.79          52.94
    2014.0   16.10  37.39          54.60

<h5>q. Export the dataframe to an Excel spreadsheet. </h5>
    
    weo_year.to_excel('weo.xls')
    

<h5>r. What method would you use to compute the mean for each country? What are the means?</h5>

    In[50]:weo_year.mean()

    Out[50]: 
    Brazil           14.802857
    Japan            34.720000
    United States    50.312857
    dtype: float64

<h5>s. Challenging. How would you compute means across countries for each year? </h5>
    
    In[59]:
    weo_year.mean(axis=1)
    
    Out[59]: 
    2008.0    31.700000
    2009.0    30.680000
    2010.0    32.120000
    2011.0    33.026667
    2012.0    34.156667
    2013.0    35.236667
    2014.0    36.030000
    dtype: float64
    
<h5>t. Plot the data by applying a plot method to weo.</h5>

    In[65]: weo_year.plot()
    Out[65]: <matplotlib.axes._subplots.AxesSubplot at 0x11c4399b0>
    
![alt text](https://cloud.githubusercontent.com/assets/4370818/19934604/99e9e9f8-a0ed-11e6-992c-6706d7f3089e.png "GDP Plot")

<h5>u. Challenging. Change the colors of the lines to green (Brazil), red (Japan), and blue (US).</h5>

    In[74]: weo_year.plot(color=["green", "red", "blue"])
    Out[74]: <matplotlib.axes._subplots.AxesSubplot at 0x11d0a5dd8>
![alt text](https://cloud.githubusercontent.com/assets/4370818/19936415/b0be5708-a0f3-11e6-9334-104e77fcc972.png "GDP Plot")

<h5>v. Challenging. Do the same plot with a log scale. Hint: Read the documentation for the plot method.</h5>

    In[77]: weo_year.plot(color=["green", "red", "blue"], logx=True)
    Out[77]: <matplotlib.axes._subplots.AxesSubplot at 0x11d40f438>
![alt text](https://cloud.githubusercontent.com/assets/4370818/19936676/b2b034c2-a0f4-11e6-9c3f-1ecb36f0b372.png "GDP Plot")


    In[83]: weo_year.plot(color=["green", "red", "blue"], logy=True)
    Out[83]: <matplotlib.axes._subplots.AxesSubplot at 0x11d5bb7f0>
![alt text](https://cloud.githubusercontent.com/assets/4370818/19936849/71990652-a0f5-11e6-8eaf-ac5f55e32e1a.png "GDP Plot")


<h5>w. Plot Brazil on its own.</h5>
    
    In[96]: weo_year.drop(['Japan', 'United States'], axis=1).plot()
    Out[96]: <matplotlib.axes._subplots.AxesSubplot at 0x11eb20898>

![alt text] (https://cloud.githubusercontent.com/assets/4370818/19937313/1ce7c3ee-a0f7-11e6-94a7-e6bf421bec97.png "GDP Plot")

    
<h5>2.Use read_csv() to read the responses of our class entry poll from</h5>
    https://raw.githubusercontent.com/NYUDataBootcamp/Materials/master/Data/entry_poll_fall16.csv
    
    
<h5>a.Read the file and assign it to the variable ep.</h5>

    url1  = 'https://raw.githubusercontent.com/NYUDataBootcamp/Materials/'
    url2 = 'master/Data/entry_poll_fall16.csv'
    url = url1 + url2

    ep = pd.read_csv(url)


<h5>b.Describe its contents. What are the variables? The responses?</h5>

The CSV includes the questions and responses to the Entry Poll we took before the first day of class.


The Variables - are the various questions posed in the Google Form.


The Responses - are the multiple choice and free type answers my classmates and I responded with.


<h5>c.What data types are the variables?</h5>
    
All the variables are objects.
    
    
    In[103]: ep.dtypes
    
    Out[103]: 
    TimeStamp   object
    Why have you enrolled in this course?  object
    What program are you enrolled in?      object
    How much programming experience have you had?  object
    How much experience with probability and statistics have you had?  object
    What is your expected major or concentration?        object
    What career path most interests you?  object
    Do you use social media for information purposes?  Check all that apply.    object
    What kinds of data most interest you?  List any that cross your mind.   object
    If we have time -- and we may not -- what special topics would interest you?  
    Check all that apply.  object
    dtype: object

<h5>d.Change the variable names to something shorter.</h5>

    ep.columns = ["Time", "Why This Class", "What Program", 
                  "Programming Exp.", "Prob. and Statistis Exp.", "Major/Concentration", 
                  "Career Path", "Social Media", "Interests", "Special Topics"]
    
    In[107]:
    ep.dtypes
    
    Out[107]: 
    Time                        object
    Why This Class              object
    What Program                object
    Programming Exp.            object
    Prob. and Statistis Exp.    object  
    Major/Concentration         object
    Career Path                 object
    Social Media                object
    Interests                   object
    Special Topics              object
    dtype: object

<h5>e.Challenging. Describe what this code does:</h5>

It starts with DataFrame ep. It lists all of the responses from column 1 (Why Take this Class?) of ep, and the corresponding count or number of times participants of the poll gave that response. For example, 60 students exactly responded that they took this course "To help with my career".

    ep[list(ep)[1]].value_counts()

    Out[108]: 
    To help with my career                               60
    I heard it was fun                                   14
    I lost my mind for a minute                           5
    I code/build websites in my spare time as a hobby     1
    Recommended by a professor.                           1
    I like a challenge                                    1
    i am living in Santiago de Chile                      1
    To finish my major                                    1
    Wanted to try something completely different          1
    Name: Why This Class, dtype: int64


<h5>3.Consider the 538 college majors data at url:</h5>
    
    url1 = 'https://raw.githubusercontent.com/fivethirtyeight/data/master/'
    url2 = 'college-majors/recent-grads.csv'
    url = url1 + url2
    
<h5>a.Create a dataframe df538 from the csv file at url using read_csv(). What are its dimensions? </h5>

There are [173 rows x 21 columns]

    url1 = 'https://raw.githubusercontent.com/fivethirtyeight/data/master/'
    url2 = 'college-majors/recent-grads.csv'
    url = url1 + url2

    df538 = pd.read_csv(url)
    
 <h5>b.What argument/parameter would you use to read only the first ten lines of the file?</h5>
 
     df538.head(10)
    
 <h5>c.Extract the variables numbered [2, 4, 15, 16, 17]. What are the names of these variables? What do they represent?</h5>
 
     In[125]: collist = [2, 4, 15, 16, 17]
     In[126]: df538 = df538[collist]
     In[126]: df538
     
     Major - What Major they are purusing/pursed
     Total - Total number of people with major
     Median - Median earnings of full-time, year-round workers
     P25th - 25th percentile of earnings
     P75th - 75th percentile of earnings
     
 
<h5>d. Set the index equal to Major..</h5>

    In[136]: df538 = df538.set_index('Major')

    In[137]: df538
    Out[137]: 
                                                    Total  Median  P25th   P75th
    Major                                                                       
    PETROLEUM ENGINEERING                            2339  110000  95000  125000
    MINING AND MINERAL ENGINEERING                    756   75000  55000   90000
    METALLURGICAL ENGINEERING                         856   73000  50000  105000
    NAVAL ARCHITECTURE AND MARINE ENGINEERING        1258   70000  43000   80000
    CHEMICAL ENGINEERING                            32260   65000  50000   75000
    NUCLEAR ENGINEERING                              2573   65000  50000  102000
    ACTUARIAL SCIENCE                                3777   62000  53000   72000
    ASTRONOMY AND ASTROPHYSICS                       1792   62000  31500  109000
    MECHANICAL ENGINEERING                          91227   60000  48000   70000
    ELECTRICAL ENGINEERING                          81527   60000  45000   72000
    COMPUTER ENGINEERING                            41542   60000  45000   75000
    AEROSPACE ENGINEERING                           15058   60000  42000   70000
                                                      ...     ...    ...     ...
[173 rows x 4 columns]

<h5>e.Use the sort_values() method to sort the data by Total.</h5>

    df538.sort(columns="Total")
    
<h5>f. What code would you use to extract the ten majors with the greatest number of people?</h5>

    In[142]: df538.sort(columns="Total").tail(10)

    Out[142]: 
                                             Total  Median  P25th  P75th
    Major                                                               
    POLITICAL SCIENCE AND GOVERNMENT        182621   38000  28000  50000
    ENGLISH LANGUAGE AND LITERATURE         194673   32000  23000  41000
    ACCOUNTING                              198633   45000  34000  56000
    MARKETING AND MARKETING RESEARCH        205211   38000  30000  50000
    NURSING                                 209394   48000  39000  58000
    COMMUNICATIONS                          213996   35000  27000  45000
    GENERAL BUSINESS                        234590   40000  30000  55000
    BIOLOGY                                 280709   33400  24000  45000
    BUSINESS MANAGEMENT AND ADMINISTRATION  329927   38000  29000  50000
    PSYCHOLOGY                              393735   31500  24000  41000
    
    
<h5>g. Challenging. Construct horizontal bar charts of the top ten majors sorted, first, by median salary and, second, by the salary of the 25th percentile. In each case plot just the variable you sorted on.</h5>
 
     mediangraph = df538.sort(columns="Median").tail(10)
     mediangraph.drop(['Total', 'P25th', 'P75th'], axis=1).plot.barh()
     
![alt text] (https://cloud.githubusercontent.com/assets/4370818/19941716/a8622b20-a107-11e6-92e5-d8a26ac77fe0.png "GDP Plot")
     
     p25graph = df538.sort(columns="P25th").tail(10)
     p25graph.drop(['Total', 'Median', 'P75th'], axis=1).plot.barh()

![alt text] (https://cloud.githubusercontent.com/assets/4370818/19941729/b4408680-a107-11e6-95f3-96b92e108ed9.png "GDP Plot")

<h5> 4. Approximately how long did this assignment take you?</h5>

1.25 Hours
