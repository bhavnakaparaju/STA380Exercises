Question 1: Visual Story Telling: Green Buildings
=================================================

Analysis of the Experts Decisions
---------------------------------

    ## Loading required package: dplyr

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

    ## Loading required package: lattice

    ## Loading required package: ggformula

    ## Loading required package: ggplot2

    ## Loading required package: ggstance

    ## 
    ## Attaching package: 'ggstance'

    ## The following objects are masked from 'package:ggplot2':
    ## 
    ##     geom_errorbarh, GeomErrorbarh

    ## 
    ## New to ggformula?  Try the tutorials: 
    ##  learnr::run_tutorial("introduction", package = "ggformula")
    ##  learnr::run_tutorial("refining", package = "ggformula")

    ## Loading required package: mosaicData

    ## Loading required package: Matrix

    ## Registered S3 method overwritten by 'mosaic':
    ##   method                           from   
    ##   fortify.SpatialPolygonsDataFrame ggplot2

    ## 
    ## The 'mosaic' package masks several functions from core packages in order to add 
    ## additional features.  The original behavior of these functions should not be affected by this.
    ## 
    ## Note: If you use the Matrix package, be sure to load it BEFORE loading mosaic.
    ## 
    ## Have you tried the ggformula package for your plots?

    ## 
    ## Attaching package: 'mosaic'

    ## The following object is masked from 'package:Matrix':
    ## 
    ##     mean

    ## The following object is masked from 'package:ggplot2':
    ## 
    ##     stat

    ## The following objects are masked from 'package:dplyr':
    ## 
    ##     count, do, tally

    ## The following objects are masked from 'package:stats':
    ## 
    ##     binom.test, cor, cor.test, cov, fivenum, IQR, median, prop.test,
    ##     quantile, sd, t.test, var

    ## The following objects are masked from 'package:base':
    ## 
    ##     max, mean, min, prod, range, sample, sum

    ## -- Attaching packages --------------------------------------- tidyverse 1.3.0 --

    ## v tibble  3.0.3     v purrr   0.3.4
    ## v tidyr   1.1.0     v stringr 1.4.0
    ## v readr   1.3.1     v forcats 0.5.0

    ## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
    ## x mosaic::count()            masks dplyr::count()
    ## x purrr::cross()             masks mosaic::cross()
    ## x mosaic::do()               masks dplyr::do()
    ## x tidyr::expand()            masks Matrix::expand()
    ## x dplyr::filter()            masks stats::filter()
    ## x ggstance::geom_errorbarh() masks ggplot2::geom_errorbarh()
    ## x dplyr::lag()               masks stats::lag()
    ## x tidyr::pack()              masks Matrix::pack()
    ## x mosaic::stat()             masks ggplot2::stat()
    ## x mosaic::tally()            masks dplyr::tally()
    ## x tidyr::unpack()            masks Matrix::unpack()

### Removing Bottom 10% of Leasing Rates

Below is the histogram displaying the distribution of leasing rate for
the non-green buildings.
![](STA-380-Exercises_files/figure-markdown_strict/1.2-1.png) Below is
the histogram displaying the distribution of leasing rate for the green
buildings. ![](STA-380-Exercises_files/figure-markdown_strict/1.3-1.png)

Based on the distributions shown above, we do not believe that we should
remove the buildings with leasing rates that are less than 10%. While
the non green building distribution shows a slight left skew with some
outliers, the green building distribution does not. By removing these
values, we believe we would be compromising the data set by not
including all information available.

### Using Median instead of Mean

Since we did not remove the outliers above, we believe it is important
to use median intead of the mean because the median is more robust to
outliers. We agree with the experts decision to do this.

Below is the median value for the green buildings rent:

    ## [1] 27.6

Below is the median value for the non-green buildings rent:

    ## [1] 25

Based on the results above, on average rent is more expensive in green
buildings over non\_green buildings. This leads us to believe that there
may be a advantage to building more green buildings but we will rely
further analysis to confirm.

Potential Other Causes of Rent Increases
----------------------------------------

The guru stated that since our building will be 250,000 square feet and
that there is an increase of 2.60 dollars for green buildings, that our
estimated revenue would be 650,000 dollars more. However, we are unsure
about this conclusion. We believe that other specifications about the
building could impact overall revenue.

### Age Vs Rent

Below, we display the relationship between age and rent. From this, we
can see that majority of the green buildings are newer, which makes
sense as this is a new development in construction. However, this graph
does not give us a clear picture if the age largely impacts the overall
rent. ![](STA-380-Exercises_files/figure-markdown_strict/1.6-1.png)

### Leasing Rate vs Rent

Below, the graph displays the relationship between leasing rate and
rent. It appears to have a slightly positive correlation. This makes
sense as more desirable will lease to capacity more often.

![](STA-380-Exercises_files/figure-markdown_strict/1.7-1.png)

### Rent vs Class

Based on the below boxplot, we have concluded that class could be
indicative of rent increases. So class is potentially a variable that
would affect rent and affect our conclusion of revenue increase.
![](STA-380-Exercises_files/figure-markdown_strict/1.8-1.png)

### Rent vs Renovated

The below graph shows that the mean values for renovated vs
non-renovated buildings are very similar. While, the renovated buildings
have a higher maximum rent value, it does not appear that all renovated
buildings cost more in rent. We believe that this is due to the fact
that new buildings do not require renovations so while an older building
that is renovated will cost more than an older building that is not
renovated, a newer builder that is not technically renovated will still
cost more than the older renovated building. Due to this, we do not
believe that the renovated variable is highly indicative of price.

![](STA-380-Exercises_files/figure-markdown_strict/1.9-1.png)

### Rent vs Amenities

Surprisingly enough, it also does not appear that buildings containing
amentities have higher rents. Due to this, we do not think that the
amenities variable is highly indicative of increased rent.

![](STA-380-Exercises_files/figure-markdown_strict/1.10-1.png)

Conclusion and Recommendation
-----------------------------

Based on our analysis from the above figures, it does appear that the
main variable that increases the cost of rent is whether or not the
building is a green building. It also appears that green buildings rent
at a higher leasing rate than non-green buildings.

Question 2: Visual Story Telling: Flights at ABIA
=================================================

Our goal for this assignment is to find some interesting story about
flights arriving and departing from Austin airport. To begin this
process, we started by simply looking at the dataset and we decided that
looking at the various Delay variables would be interesting. We decided
to focus on these variables because Delays have a very adverse affect on
flying and almost everyone has had a negative experience with airline
delays. We wanted to understand how the Austin airport is related with
Delays.

Visual Analaysis
----------------

### Departure Delays vs Arrival Delays

To start, we ran a simple scatter plot of Departure Delays and Arrival
Delays. There seems to be a positive correlation between Departure Delay
and Arrival Delay, which makes sense as often times when a plane leaves
late, it will arrive at the location late as well.

    ## Warning: Removed 1601 rows containing missing values (geom_point).

![](STA-380-Exercises_files/figure-markdown_strict/2.2-1.png)

### Departure Delays vs Month

Next, we wanted to understand if there was any relationship between
delays and time of year so we looked at a histogram of delays by month.
We decided to specifically look at Departure Delays because that is most
indicative of factors at the Austin airport. It appears as though the
low time for delays is September through November. We discussed how this
could be related to the Fall season since there is less harsh weather in
the fall. The spike in December could be related to high travel related
to the Christmas holiday.

    ## Warning: Removed 59007 rows containing missing values (position_stack).

![](STA-380-Exercises_files/figure-markdown_strict/2.3-1.png)

### Departure Delays vs Day of Week

We looked at a similar histogram as the one above but for day of week
with 1 being Sunday and 7 and being Saturday. The only interesting thing
to note about this graph is that there seems to be a very low level on
Fridays.

    ## Warning: Removed 59007 rows containing missing values (position_stack).

![](STA-380-Exercises_files/figure-markdown_strict/2.4-1.png)

### Monthly Arrival and Departure Delays

Next we looked at the average monthly delays both arrival and departure.
They seem to track with eachother for the most part, which makes sense
from our earlier scatter plot that shows there is a positive
relationship between arrival and departure delays. However, they
slightly deviate from eachother in the summer months with departure
delays being less than arrival delays.

    ## Warning: Ignoring unknown parameters: fun.y

    ## Warning: Ignoring unknown parameters: fun.y

    ## No summary function supplied, defaulting to `mean_se()`
    ## No summary function supplied, defaulting to `mean_se()`

![](STA-380-Exercises_files/figure-markdown_strict/2.5-1.png)

### Daily Arrival and Departure Delays

Similar to the graph above, we looked at daily arrival and departure
delays. They follow the same the trend; however, the departure delays
are always less than the arrival delays. This is interesting because
departure delays are usually more indicative of the local airport so
this displays that the Austin airport sends flights out late less often
than flights arrive to them late.

    ## Warning: Ignoring unknown parameters: fun.y

    ## Warning: Ignoring unknown parameters: fun.y

    ## No summary function supplied, defaulting to `mean_se()`
    ## No summary function supplied, defaulting to `mean_se()`

![](STA-380-Exercises_files/figure-markdown_strict/2.6-1.png)

### Types of Delays

Next, we looked at the types of delays over the different months. This
is interesting because the consistently highest type of delay is Late
Aircraft Delay. This makes sense because we saw above that the Austin
airport has a much higher rate of Arrival Delays than Departure Delays.

    ## Warning: Ignoring unknown parameters: fun.y

    ## Warning: Ignoring unknown parameters: fun.y

    ## Warning: Ignoring unknown parameters: fun.y

    ## Warning: Ignoring unknown parameters: fun.y

    ## Warning: Ignoring unknown parameters: fun.y

    ## No summary function supplied, defaulting to `mean_se()`
    ## No summary function supplied, defaulting to `mean_se()`
    ## No summary function supplied, defaulting to `mean_se()`
    ## No summary function supplied, defaulting to `mean_se()`
    ## No summary function supplied, defaulting to `mean_se()`

![](STA-380-Exercises_files/figure-markdown_strict/2.7-1.png)

### Delays by Carrier

Lastly, we looked at delays by carrier as shown below.

    ## Warning: `fun.y` is deprecated. Use `fun` instead.

    ## Warning: `fun.y` is deprecated. Use `fun` instead.

![](STA-380-Exercises_files/figure-markdown_strict/2.9-1.png)

Summary and Conclusion
----------------------

From our visual analysis, we concluded that the Austin airport does a
better job than average when it comes to delays. We conclude this
because Austin airport has consistently less departure delay times even
when their arrival delay times are high. This is surprising because
arrival and departure delays were highly correlated.

Question 3: Portfolio Modeling
==============================

Selecting and Loading our Stocks
--------------------------------

The ETF’s we decided to build our portfolio with were iShares Preferred
and Income Securities ETF(PFF), Invesco Preferred ETF(PGX), SPDR
Barclays Capital Convertible Bond ETF(CWB). We then adjusted for splits
and dividends, and plotted each indivuial ETF.

    ## Loading required package: xts

    ## Loading required package: zoo

    ## 
    ## Attaching package: 'zoo'

    ## The following objects are masked from 'package:base':
    ## 
    ##     as.Date, as.Date.numeric

    ## 
    ## Attaching package: 'xts'

    ## The following objects are masked from 'package:dplyr':
    ## 
    ##     first, last

    ## Loading required package: TTR

    ## Registered S3 method overwritten by 'quantmod':
    ##   method            from
    ##   as.zoo.data.frame zoo

    ## Version 0.4-0 included new data defaults. See ?getSymbols.

    ## 
    ## Attaching package: 'foreach'

    ## The following objects are masked from 'package:purrr':
    ## 
    ##     accumulate, when

    ## 'getSymbols' currently uses auto.assign=TRUE by default, but will
    ## use auto.assign=FALSE in 0.5-0. You will still be able to use
    ## 'loadSymbols' to automatically load data. getOption("getSymbols.env")
    ## and getOption("getSymbols.auto.assign") will still be checked for
    ## alternate defaults.
    ## 
    ## This message is shown once per session and may be disabled by setting 
    ## options("getSymbols.warning4.0"=FALSE). See ?getSymbols for details.

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query1.finance.yahoo.com/v7/finance/download/PFF?
    ## period1=-2208988800&period2=1597622400&interval=1d&events=split&crumb=Sdswv6FDbwh'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query2.finance.yahoo.com/v7/finance/download/PFF?
    ## period1=-2208988800&period2=1597622400&interval=1d&events=split&crumb=Sdswv6FDbwh'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query2.finance.yahoo.com/v7/finance/download/PGX?
    ## period1=-2208988800&period2=1597622400&interval=1d&events=split&crumb=Sdswv6FDbwh'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query2.finance.yahoo.com/v7/finance/download/PGX?
    ## period1=-2208988800&period2=1597622400&interval=1d&events=split&crumb=Sdswv6FDbwh'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query2.finance.yahoo.com/v7/finance/download/CWB?
    ## period1=-2208988800&period2=1597622400&interval=1d&events=split&crumb=Sdswv6FDbwh'

    ## Warning in read.table(file = file, header = header, sep = sep,
    ## quote = quote, : incomplete final line found by readTableHeader
    ## on 'https://query1.finance.yahoo.com/v7/finance/download/CWB?
    ## period1=-2208988800&period2=1597622400&interval=1d&events=split&crumb=Sdswv6FDbwh'

![](STA-380-Exercises_files/figure-markdown_strict/3.1-1.png)![](STA-380-Exercises_files/figure-markdown_strict/3.1-2.png)![](STA-380-Exercises_files/figure-markdown_strict/3.1-3.png)

Combine close to close changes in a single matrix, and remove first row
because value is NA. We didn’t have a “before” in our data. Outputting
all returns afterwards.

    ##                ClCl.PFFa     ClCl.PGXa    ClCl.CWBa
    ## 2015-01-05 -0.0037869729 -0.0020338983 -0.012364059
    ## 2015-01-06  0.0010137101  0.0006793478 -0.002374293
    ## 2015-01-07  0.0022784810  0.0027155465  0.008870619
    ## 2015-01-08  0.0012629199  0.0006770481  0.009650461
    ## 2015-01-09  0.0007567861  0.0000000000 -0.004248109
    ## 2015-01-12 -0.0007562138 -0.0006765900 -0.007252560

Plotting the correlation of all three ETF’s. Shows a strong correlation
up to around index 120
![](STA-380-Exercises_files/figure-markdown_strict/3.3-1.png)![](STA-380-Exercises_files/figure-markdown_strict/3.3-2.png)

Plotting the market returns over time
![](STA-380-Exercises_files/figure-markdown_strict/3.4-1.png)

Plotting all\_returns correlation between two days, and seems to be
similar in trend
![](STA-380-Exercises_files/figure-markdown_strict/3.5-1.png)

![](STA-380-Exercises_files/figure-markdown_strict/3.6-1.png)

First Possibility: Aggressive Model
-----------------------------------

We chose the following 3 stocks: PFF, PGX, CWB. From the ETFDB website,
we determined that the PFF stock has a YTD of 0.02%, the PGX stock as a
YTD of 1.86% and the CWB stock has YTD of 20.99%. Based on these values,
we decided to begin with an aggressive strategy by weighting the CWB
stock higher than our other stocks.

    ##            ClCl.PFFa ClCl.PGXa ClCl.CWBa
    ## 2020-01-08  10010.58  15019.85  75279.01

    ## [1] 100309.4

We decided to run the simulation over a 4 week period. We then plotted
the path our total wealth took in our portfolio over 20 days. Also using
bootstrap resampling to estimate the 4-week

    ## [1] 102499.7

![](STA-380-Exercises_files/figure-markdown_strict/3.9-1.png)

We then decided to simulate many different possible futures.

    ##               [,1]      [,2]      [,3]      [,4]      [,5]      [,6]      [,7]
    ## result.1 100022.77  99550.11  99434.81  99517.59  98954.98  99590.28  99792.12
    ## result.2  99984.20 100319.24 100619.30 100519.60 100439.38 100285.79 100630.10
    ## result.3 100132.12 100207.62  99695.77  99696.40 100258.95  99903.01  99949.68
    ## result.4  99870.87 100119.22 100043.76  99365.27  99449.52  99655.53  99375.99
    ## result.5 100158.06 100120.17 100292.88 101027.42 100175.00 100503.08 100801.25
    ## result.6  98060.51  97798.20  97446.55  97101.16  97385.04  97644.30  97713.41
    ##               [,8]      [,9]     [,10]     [,11]     [,12]     [,13]     [,14]
    ## result.1  99910.75  99574.17  99616.14  99561.76  98879.10  99161.67  99564.07
    ## result.2 100235.41 100502.53 100157.06  99917.79 105865.79 105893.07 105772.07
    ## result.3  99727.76 100069.46 100044.63 100198.09 100262.74 100385.47 100689.76
    ## result.4  99531.96  99314.99  99461.71  99107.93  98436.59  98016.85  97999.28
    ## result.5 100841.39 100861.05 100875.52 100547.49  99449.14  99671.37  99742.64
    ## result.6  98178.65  98025.40  97811.72  97871.82  98027.48  98077.02  97874.61
    ##              [,15]     [,16]     [,17]     [,18]     [,19]     [,20]
    ## result.1  99534.94  99297.20  99403.56  99346.85  99556.39  99331.74
    ## result.2 106289.92 109407.93 109373.46 109306.28 109198.63 109385.43
    ## result.3 100861.81 100036.18 100166.18 100340.87 100411.21 100344.00
    ## result.4  97079.77  97121.08  97295.38  97708.67  97388.88  97126.34
    ## result.5 100020.43 100199.17  98939.70  99064.83  99011.24  99266.66
    ## result.6  97855.02  97919.70  97970.65  98239.50  98373.75  98397.64

![](STA-380-Exercises_files/figure-markdown_strict/3.11-1.png)

Next, we decided to look at the profit and loss.

    ## [1] 100480

    ## [1] 479.9631

![](STA-380-Exercises_files/figure-markdown_strict/3.12-1.png)

5% value at risk displayed below:

    ##        5% 
    ## -5390.312

Second Possibility: Cautious Stategy
------------------------------------

For our cautious strategy, we decided to weight the less volatile stocks
higher, such as PFF and PGX. CWB was the most sporadic ETF, so we
decided to give it the least amount of weight.

    ##            ClCl.PFFa ClCl.PGXa ClCl.CWBa
    ## 2015-12-02  49770.93  29959.73  19819.32

Summing our total wealth for our portfolio

    ## [1] 99549.98

We decided to run the simulation over a 4 week period. We then plotted
the path our total wealth took in our portfolio over 20 days. Also using
bootstrap resampling to estimate the 4-week

    ## [1] 99757.47

![](STA-380-Exercises_files/figure-markdown_strict/3.16-1.png)

We then decided to simulate 5000 different possible futures. Then
displayed the first 10 dollar amounts of our total wealth

    ##               [,1]      [,2]      [,3]      [,4]      [,5]      [,6]      [,7]
    ## result.1 100350.53 100251.12 100241.51 100179.55  99997.26  99878.05  99923.59
    ## result.2 100207.21 100026.91 100010.56  99740.70  99751.77  99945.81  99663.37
    ## result.3 100373.44 100321.06 100287.33 100301.16  99927.88  99870.94 100075.45
    ## result.4  99352.69  98588.12  98571.50  98744.03  98643.67  98693.83  98603.85
    ## result.5  99934.13  99818.82  99958.15 100217.26 100767.85 101211.89 101468.99
    ## result.6  99644.67  99529.57  99562.76  99181.91  99070.24  97785.20  98090.62
    ##               [,8]      [,9]     [,10]     [,11]     [,12]     [,13]     [,14]
    ## result.1  99740.67  99063.48 100010.21 100109.62  99473.73  97427.71  97254.35
    ## result.2 100039.33 100493.71 100815.68 100499.42 100468.11 100454.96 100595.56
    ## result.3 100310.46 100483.09 100711.20 100947.65 100983.92 101154.71 101392.10
    ## result.4  98824.78  99022.82  99363.43  98721.17  98721.57  98492.03  98484.07
    ## result.5 101605.97 101458.02 101623.83 101819.13 101787.22 103316.99 103749.06
    ## result.6  98391.45  98695.84  98772.66  99020.37  99215.58  99321.88  90263.88
    ##              [,15]     [,16]     [,17]     [,18]     [,19]     [,20]
    ## result.1  96942.38  97098.32  97355.91  97478.12  97324.98  97159.97
    ## result.2 100718.04 100839.15 100764.64 101033.58 100934.77 101209.20
    ## result.3 101314.17 101077.41 100738.07 100713.73 100812.52 100606.45
    ## result.4  98676.02  98969.08  99020.67  99270.81  98873.76  98645.80
    ## result.5 103975.52 103888.95 103348.98 102974.25 103341.88 104341.26
    ## result.6  90357.96  90766.87  90800.35  90985.61  90413.44  90392.02

We then used a histogram to plot 25 Total wealth in our portfolio
![](STA-380-Exercises_files/figure-markdown_strict/3.18-1.png)

Next, we decided to look at the profit and loss.

    ## [1] 100570.3

    ## [1] 570.3141

![](STA-380-Exercises_files/figure-markdown_strict/3.19-1.png)

5% value at risk displayed below:

    ##       5% 
    ## -4814.71

Third Possibility: Even Split Strategy
--------------------------------------

For our last strategy, we did an even split for the weights of all 3 of
our stocks. Please note that, our CWB stock is weighted 1% since we had
3 stocks, however, this is still considered a mostly even split.

    ##            ClCl.PFFa ClCl.PGXa ClCl.CWBa
    ## 2017-01-23  33131.13  33251.56  34043.87

Our total wealth is

    ## [1] 100426.6

We decided to run the simulation over a 4 week period. We then plotted
the path our total wealth took in our portfolio over 20 days. Also using
bootstrap resampling to estimate the 4-week

    ## [1] 94873.17

![](STA-380-Exercises_files/figure-markdown_strict/3.23-1.png)

We then decided to simulate 5000 different possible futures. Then
displayed the first 10 dollar amounts of our total wealth

    ##               [,1]      [,2]      [,3]      [,4]      [,5]      [,6]      [,7]
    ## result.1  99176.08  99032.58  98886.51  98670.65  98637.25  98969.24  98859.85
    ## result.2  99944.62  99968.44 100055.89 100112.05  95888.96  95890.77  96143.99
    ## result.3  99994.32  99758.47  99864.20  99978.54 100361.55 100444.19 100379.99
    ## result.4 100255.01 100169.44 100348.96 100369.23 100628.80 100538.88 100398.85
    ## result.5  99991.91  99788.81  99808.03  99931.58 100606.38 100535.38 100740.92
    ## result.6 100097.07 100477.86 100307.02 100192.58 100296.91 100574.90 100660.92
    ##               [,8]      [,9]     [,10]     [,11]     [,12]     [,13]     [,14]
    ## result.1  98730.84  98899.65  98998.17  99116.71  99680.27  99660.53  99507.18
    ## result.2  96685.01  97054.20  96405.06  96736.86  96837.55  97430.24  97393.30
    ## result.3 100645.07 100423.74 100736.30 100172.53 100127.83 100220.89  98904.32
    ## result.4 100393.02 100235.50 100459.45 100738.16 100873.23 100656.58 100999.19
    ## result.5 100881.75 100887.47 100816.69  99787.03 100213.12 100306.34  99671.69
    ## result.6 100113.92 100457.57 100584.15 100593.80 100390.81 100593.28 100560.87
    ##              [,15]     [,16]     [,17]     [,18]     [,19]     [,20]
    ## result.1  99693.10  99773.00  99876.16 100452.53 100245.52 101034.98
    ## result.2  97063.47  97297.42  96958.26  97438.26  97637.10  97772.63
    ## result.3  98999.43  99111.90  98932.08  99829.70  99819.76  99757.60
    ## result.4 100948.59 101268.55 101401.51 101588.01 101708.85 101930.06
    ## result.5  99923.64 100668.50 100707.42 100955.64 101303.46 101562.04
    ## result.6 100468.07 100544.32 100194.00 100374.36 100687.55 100679.02

We then used a histogram to plot 25 Total wealth in our portfolio
![](STA-380-Exercises_files/figure-markdown_strict/3.25-1.png)

Next, we decided to look at the profit and loss.

    ## [1] 100567.5

    ## [1] 567.4568

![](STA-380-Exercises_files/figure-markdown_strict/3.26-1.png)

5% value at risk displayed below:

    ##        5% 
    ## -4798.472

Summary and Report
------------------

All three of our portfolios profited over 200 dollars. According to our
different portfolios, our aggressive strategy had a 5% value at risk of
-2663.451. Our cautious strategy had a 5% value at risk of -2833.097,
and lastly our evenly weighted strategy had a -2943.378 5% value at
risk. When investing more money into ETF’s with a higher YTD, a higher
profit is attained. This is because the company has been growing rapidly
instead of steadily. So in this situation, investing in slowly growing
companies will yield less profit.

Question 4: Market Segmentation
===============================

To start, we first removed chatter, uncategorized and spam from the
dataset as we did not thing these variables were clear or helpful.

We created an elbow plot to determine the optimal number of clusters in
our k means clustering.

    ##  [1] 252192.0 230121.4 215873.7 204176.7 193297.4 183176.0 176078.5 169350.0
    ##  [9] 163954.3 159314.6 155944.8 152723.2 150467.0 148404.2 146550.1

![](STA-380-Exercises_files/figure-markdown_strict/4.2-1.png) After
looking at the plot, we determined that 4 would be the ideal number of
clusters because there is a slight elbow between the 4 and 6 number of
clusters.

Below we are plotting our cluster distribution

    ## 
    ## Attaching package: 'reshape2'

    ## The following object is masked from 'package:tidyr':
    ## 
    ##     smiths

![](STA-380-Exercises_files/figure-markdown_strict/4.3-1.png)

Next, we initialize our k means and get the statistical summary for each
cluster.

    ##        V1               V2               V3               V4        
    ##  Min.   :0.4559   Min.   :0.4685   Min.   :0.4028   Min.   :0.2733  
    ##  1st Qu.:0.8422   1st Qu.:0.6955   1st Qu.:0.7720   1st Qu.:0.4514  
    ##  Median :1.2014   Median :1.0853   Median :1.1317   Median :0.5825  
    ##  Mean   :1.7880   Mean   :1.6820   Mean   :1.6930   Mean   :0.7543  
    ##  3rd Qu.:1.8850   3rd Qu.:1.7227   3rd Qu.:1.7826   3rd Qu.:0.9819  
    ##  Max.   :7.6353   Max.   :8.9399   Max.   :5.8770   Max.   :2.2003

Next, we are going to plot the frequency of tweets in each category
within each cluster.

Plotting category of tweets in Cluter 1:
![](STA-380-Exercises_files/figure-markdown_strict/4.5-1.png) In cluster
one, followers of NutrientH20 tweet mostly about health\_nutrition,
cooking, photo\_sharing, personal\_fitness, and fashion.

Plotting category of tweets in Cluter 2:
![](STA-380-Exercises_files/figure-markdown_strict/4.6-1.png) In cluster
two, followers of NutrientH20 tweet mostly about politics, travel, and
news.

Plotting category of tweets for Cluster 3:
![](STA-380-Exercises_files/figure-markdown_strict/4.7-1.png) In cluster
three, followers of NutrientH20 tweet mostly about sports\_fandom,
religion, food, parenting, school, photo\_sharing and family.

Plotting category of tweets for Cluster 4:
![](STA-380-Exercises_files/figure-markdown_strict/4.8-1.png) In cluster
four, followers of NutrientH20 tweet mostly about photo\_sharing,
current\_events, college\_uni, health\_nutrition, shopping, travel and
online\_gaming.

From our clusters, we can see that the followers of NutrientH20 tweet
about a variety of categories. Among all four cluters, a significant
amount of users compose tweets that fall under the category
photo\_sharing, health\_nutrition, and food. This tells us that these
are the interests that followers of NutritionH20 have in common.
However, there are a wide variety of categories of tweets in each
cluster so there seems to be no significant categories that stand out.

Question 5: Author Attribution
==============================

Pre-processing
--------------

To begin this problem, we first had to process the data so that we could
interpret it. We began by reading in the data using a readerPlain
function. We then created the test and train datasets. For the following
steps, we performed them for both the train and test data sets. We
started by cleaning the file names and then creating a text mining
corpus. Then, we converted alphabets to lower cases, removing numbers,
punctuation, excess space and stop words.

    ## <<DocumentTermMatrix (documents: 2500, terms: 32571)>>
    ## Non-/sparse entries: 540361/80887139
    ## Sparsity           : 99%
    ## Maximal term length: 70
    ## Weighting          : term frequency (tf)

    ## <<DocumentTermMatrix (documents: 2500, terms: 3394)>>
    ## Non-/sparse entries: 382971/8102029
    ## Sparsity           : 95%
    ## Maximal term length: 70
    ## Weighting          : term frequency - inverse document frequency (normalized) (tf-idf)

    ## <<DocumentTermMatrix (documents: 2500, terms: 3394)>>
    ## Non-/sparse entries: 382971/8102029
    ## Sparsity           : 95%
    ## Maximal term length: 70
    ## Weighting          : term frequency - inverse document frequency (normalized) (tf-idf)

PCA
---

Next, we decided to run a PCA in order to determine the interesting
features. We started by eliminating 0 entry columns and used only the
intersecting columns. Since we are wanting to run a classification
model, it is important that we prepare the data for a classification
problem. We accomplish this by running the PCA. Now the dataset
hopefully contains the important information for classification in order
to predict the author.

![](STA-380-Exercises_files/figure-markdown_strict/5.16-1.png)![](STA-380-Exercises_files/figure-markdown_strict/5.16-2.png)

KNN Model
---------

Next, we decided to run our model. We decided to run a KNN model. Our
KNN model information is displayed below.

    ## [1] 2500

    ## [1] 100

Conclusion:
-----------

In conclusion, we created a a KNN model to predict the author of
different texts. The majority of this problem included the
pre-processing in order to get the data in a usable format for
classification modeling.

Question 6: Association Rule Mining
===================================

In this problem, we are analyzing a text file that contains cart
information of a grocery store, aka what different users are buying.
Below, you can see a few different items present in several carts.

    ## 
    ## Attaching package: 'arules'

    ## The following object is masked from 'package:tm':
    ## 
    ##     inspect

    ## The following objects are masked from 'package:mosaic':
    ## 
    ##     inspect, lhs, rhs

    ## The following object is masked from 'package:dplyr':
    ## 
    ##     recode

    ## The following objects are masked from 'package:base':
    ## 
    ##     abbreviate, write

    ## Loading required package: grid

    ## Registered S3 methods overwritten by 'registry':
    ##   method               from 
    ##   print.registry_field proxy
    ##   print.registry_entry proxy

    ## Registered S3 method overwritten by 'seriation':
    ##   method         from 
    ##   reorder.hclust gclus

    ## [1] "citrus fruit,semi-finished bread,margarine,ready soups"             
    ## [2] "tropical fruit,yogurt,coffee"                                       
    ## [3] "whole milk"                                                         
    ## [4] "pip fruit,yogurt,cream cheese ,meat spreads"                        
    ## [5] "other vegetables,whole milk,condensed milk,long life bakery product"
    ## [6] "whole milk,butter,yogurt,rice,abrasive cleaner"

    ##  chr [1:9835] "citrus fruit,semi-finished bread,margarine,ready soups" ...

In order to analyze this data, we decided to turn the data into a
transaction class. From the summary below, you can see that there are
9,835 rows, meaning there are that many transactions or carts. Also from
the summary, you can see that whole milk is the most common item in a
transaction or cart and that the average number of items in the cart is
around 4.

    ## transactions as itemMatrix in sparse format with
    ##  9835 rows (elements/itemsets/transactions) and
    ##  169 columns (items) and a density of 0.02609146 
    ## 
    ## most frequent items:
    ##       whole milk other vegetables       rolls/buns             soda 
    ##             2513             1903             1809             1715 
    ##           yogurt          (Other) 
    ##             1372            34055 
    ## 
    ## element (itemset/transaction) length distribution:
    ## sizes
    ##    1    2    3    4    5    6    7    8    9   10   11   12   13   14   15   16 
    ## 2159 1643 1299 1005  855  645  545  438  350  246  182  117   78   77   55   46 
    ##   17   18   19   20   21   22   23   24   26   27   28   29   32 
    ##   29   14   14    9   11    4    6    1    1    1    1    3    1 
    ## 
    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   1.000   2.000   3.000   4.409   6.000  32.000 
    ## 
    ## includes extended item information - examples:
    ##             labels
    ## 1 abrasive cleaner
    ## 2 artif. sweetener
    ## 3   baby cosmetics

Visualization of Most Popular Items
-----------------------------------

In the histogram below, you can see the frequencies of the most popular
10 items. Whole milk is number 1 as the summary above showed.
![](STA-380-Exercises_files/figure-markdown_strict/6.4-1.png)

Apiori Algorithm
----------------

### First Attempt

We started by using the following values: support = 0.07, confidence =
.08 and length = 2. From this, we only got two rules with whole milk and
other vegetables. These are the two most common items in each cart as
you can see from the histogram above.

    ## Apriori
    ## 
    ## Parameter specification:
    ##  confidence minval smax arem  aval originalSupport maxtime support minlen
    ##        0.08    0.1    1 none FALSE            TRUE       5    0.07      2
    ##  maxlen target  ext
    ##      10  rules TRUE
    ## 
    ## Algorithmic control:
    ##  filter tree heap memopt load sort verbose
    ##     0.1 TRUE TRUE  FALSE TRUE    2    TRUE
    ## 
    ## Absolute minimum support count: 688 
    ## 
    ## set item appearances ...[0 item(s)] done [0.00s].
    ## set transactions ...[169 item(s), 9835 transaction(s)] done [0.01s].
    ## sorting and recoding items ... [18 item(s)] done [0.00s].
    ## creating transaction tree ... done [0.00s].
    ## checking subsets of size 1 2 done [0.00s].
    ## writing ... [2 rule(s)] done [0.00s].
    ## creating S4 object  ... done [0.00s].

    ##     lhs                   rhs                support    confidence coverage 
    ## [1] {other vegetables} => {whole milk}       0.07483477 0.3867578  0.1934926
    ## [2] {whole milk}       => {other vegetables} 0.07483477 0.2928770  0.2555160
    ##     lift     count
    ## [1] 1.513634 736  
    ## [2] 1.513634 736

![](STA-380-Exercises_files/figure-markdown_strict/6.6-1.png)

### Second Attempt

Next, we decreased support to 0.05, increased confidence to 0.3 but left
length the same. This gave us 3 rules and a relationship between
rolls/buns, yogurt, other vegetables that all go through whole milk. All
of these items are still in the top 10 of most frequently bought items.

    ## Apriori
    ## 
    ## Parameter specification:
    ##  confidence minval smax arem  aval originalSupport maxtime support minlen
    ##         0.3    0.1    1 none FALSE            TRUE       5    0.05      2
    ##  maxlen target  ext
    ##      10  rules TRUE
    ## 
    ## Algorithmic control:
    ##  filter tree heap memopt load sort verbose
    ##     0.1 TRUE TRUE  FALSE TRUE    2    TRUE
    ## 
    ## Absolute minimum support count: 491 
    ## 
    ## set item appearances ...[0 item(s)] done [0.00s].
    ## set transactions ...[169 item(s), 9835 transaction(s)] done [0.01s].
    ## sorting and recoding items ... [28 item(s)] done [0.00s].
    ## creating transaction tree ... done [0.00s].
    ## checking subsets of size 1 2 done [0.00s].
    ## writing ... [3 rule(s)] done [0.00s].
    ## creating S4 object  ... done [0.00s].

    ##     lhs                   rhs          support    confidence coverage  lift    
    ## [1] {yogurt}           => {whole milk} 0.05602440 0.4016035  0.1395018 1.571735
    ## [2] {rolls/buns}       => {whole milk} 0.05663447 0.3079049  0.1839349 1.205032
    ## [3] {other vegetables} => {whole milk} 0.07483477 0.3867578  0.1934926 1.513634
    ##     count
    ## [1] 551  
    ## [2] 557  
    ## [3] 736

![](STA-380-Exercises_files/figure-markdown_strict/6.7-1.png)

![](STA-380-Exercises_files/figure-markdown_strict/6.8-1.png)

### Third Attempt

Finally, we decreased support to 0.0018, increased confidence to 0.9 and
still left length the same. This gave us 4 rules but gave us a much
better picture. From the graph, we can see an association between
purchasing bottled beer, red/blush wine and liquor. We can also see an
association between purchasing other vegetables, fruit/vegetable juice,
tropical fruit and whipped/sour cream. From there, it branches out even
further to show us other items and how they could be associated.

    ## Apriori
    ## 
    ## Parameter specification:
    ##  confidence minval smax arem  aval originalSupport maxtime support minlen
    ##         0.9    0.1    1 none FALSE            TRUE       5  0.0018      2
    ##  maxlen target  ext
    ##      10  rules TRUE
    ## 
    ## Algorithmic control:
    ##  filter tree heap memopt load sort verbose
    ##     0.1 TRUE TRUE  FALSE TRUE    2    TRUE
    ## 
    ## Absolute minimum support count: 17 
    ## 
    ## set item appearances ...[0 item(s)] done [0.00s].
    ## set transactions ...[169 item(s), 9835 transaction(s)] done [0.01s].
    ## sorting and recoding items ... [149 item(s)] done [0.00s].
    ## creating transaction tree ... done [0.01s].
    ## checking subsets of size 1 2 3 4 5 6 done [0.01s].
    ## writing ... [4 rule(s)] done [0.00s].
    ## creating S4 object  ... done [0.00s].

    ##     lhs                        rhs                    support confidence    coverage      lift count
    ## [1] {liquor,                                                                                        
    ##      red/blush wine}        => {bottled beer}     0.001931876  0.9047619 0.002135231 11.235269    19
    ## [2] {butter,                                                                                        
    ##      pip fruit,                                                                                     
    ##      whipped/sour cream}    => {whole milk}       0.001830198  0.9000000 0.002033554  3.522284    18
    ## [3] {domestic eggs,                                                                                 
    ##      tropical fruit,                                                                                
    ##      whipped/sour cream}    => {whole milk}       0.001830198  0.9000000 0.002033554  3.522284    18
    ## [4] {fruit/vegetable juice,                                                                         
    ##      tropical fruit,                                                                                
    ##      whipped/sour cream}    => {other vegetables} 0.001931876  0.9047619 0.002135231  4.675950    19

![](STA-380-Exercises_files/figure-markdown_strict/6.10-1.png)
