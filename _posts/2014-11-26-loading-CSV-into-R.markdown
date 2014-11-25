---
layout: post
title:  "Loading a dataset saved as CSV files into R"
date:   2014-11-26 11:00:00
categories: Recipe
---

###Loading a dataset saved as CSV files into R

> *CSV files are commonly used to record and publish data sets. Software such as Microsoft excel, Google docs and a wide range of domain specific tools provide options for exporting data in this format. As such, statistical environments such as R support working with CSV files. But getting the data from these files into the R environment is often one of the first hurdles when undertaking any analysis. In this recipe we cover the basics of loading data stored in CSV files into R, pointing out a few important caveats as we go

## Outline

* Locate the file
* Check for column header fields
* Examine how the data values are separated
* Determine how missing data values are stored
* Load the data into R
* Checking your import
* Saving your data
* Removing your data


## Jargon
CSV: [Comma Separated Value file] (http://en.wikipedia.org/wiki/Comma-separated_values)


## Requirements
* R is already [installed] (http://www.r-project.org/)


##1.  Locate the File

1. The first step is to locate where the file is currently saved. In many cases this means a location on your personal computer, but the file may also be published on the web. The commands used in the later steps will work with both local CSV files and ones published on the web.

2. Find and note down the full address of the file we want to load into R. For files located on the web, this will begin with the full “http://“ preamble, while local files we will also capture the full file address.

{% highlight %}
Windows C:\user\docs\nzrivers.txt
Mac: /Users/rhos012/Documents/nzrivers.txt
Web: http://www.statsci.org/data/oz/nzrivers.txt
{% endhighlight %}

##2. Check the headers

1. With CSV files it is common for the first line to capture the names of the column headings (just like you would see in a spreadsheet). When importing data into R it is important to note if your file contains these columns headers on the first line or not.

2. Simply note down whether the first line of the file contains the column headers, or jumps straight into the data values.


##3. Examine how the data is separated 

1. The most common means for separating the data values in a CSV file is using commas (hence the name!). But this is not the only way. Other options include using tabs - often called tab separated values. It’s important to quick examine the formatted used for the file of interest the saves headaches later.

2. Open the file in a text editor, or if you are familiar your favorite command line tool. Note down if you see commas ‘,’ separating the values in your file, or if another means is used such as tabs. Note down if you notice something other than commas being used


##4 - Determine how missing values are stored

1. You, your colleagues or the organizing providing the data may have chosen different methods to represent missing data values. By default R will assume that missing values are represented by leaving the field blank. But it is also able to recognize a range of other methods.

2. Record the different styles used to represent missing data values. For example the following are commonly employed ‘(“NA", "-", “?”)’


##5. Load the Data into R

1. In the R terminal run the command below to load your data. This command will assume: The first line captures column names, the file uses commas to separate values, decimal points are used for representing numbers, and that missing fields are left blank

{% highlight %}
mydata <- read.csv("/Users/rhos012/Documents/nzrivers.txt")
mydata <- read.csv("http://www.statsci.org/data/oz/nzrivers.txt")
{% endhighlight %}

2. But in your case if any of these assumptions, the following command shows how you can explain this to R.

{% highlight %}
mydata <- read.table(file=“/Users/rhos012/Documents/nzrivers.txt”, sep=“/t”, header=TRUE, stringsAsFactor=FALSE, na.strings=(“-“,”NA”,”?”))
{% endhighlight %}

##6. Checking your import

1. Often it may be valuable to inspect the data you imported to reassure yourself. The following commands provide helpful ways of doing this.

{% highlight %}
str(myData) - Provides a summary of the new object you have created, listing the initial values for each column.
dim(myData) - Examines the dimensions of your data; in the simplest case showing the number of rows and columns in your data
lapply(myData, class) - Prints out the type of data R believe each column stores, usually numeric.

myData - Typing in the name of your data object will result in the file being printed on the terminal (think twice about running this for very large files)
{% endhighlight %}

##7. Saving your data

{% highlight %}
save(myData, file="filename.rda")
Reload it at any time with:
load("filename.rda")
{% endhighlight %}


##8. Removing your data

1. Keeping your workspace clean is often desired, with the following command you can remove the data object from your current workspace

{% highlight %}
rm(myData)
{% endhighlight %}

