# Hypothesis-Testing
Project part of an online Data Science course, deciding whether University towns have their mean housing prices less effected by recessions and running a t-test.

For the first part, I read the information from the university_towns.txt and parsed
the input, then returned a data frame with 2 columns, 'State' and 'Region Name'.

Then I read a new data frame from the excel file gdplev.xls and parsed it so that is
has 2 columns, Quarter and GDP. The recession start is represented by the quarter
that has the GDP bigger than the next 2 quarters(and the next quarter has a GDP bigger than the second next). Similarly I obtain the recession end.

In the next function, I use the previously computed recession start/end to extract the
recession bottom, that is, the quarter from the recession which had the lowest GDP.

In the convert_housing_data_to_quarters function I built a data frame, converting the
housing data to quarters, and used multi-index for State and Region Name. In order
to do that, I also used a dictionary that associated each state code with a state
name(ex: OH - Ohio). Firstly I deleted the non-necessary columns, for years 1996-2000
and 2000-2016.
Then I created new columns in the data frame for quarters, using a mean of the 3 months
in a season.

In the end I runned a ttest that decided whether the hypothesis is true, also
returning a value of confidence.
