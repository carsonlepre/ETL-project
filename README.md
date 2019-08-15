# ETL-project
ETL mini project with Joseph and Carson.

ETL Mini-Project

The purpose of our code was to generate a graph that represented the real time tire pressures of the tires in a fleet of electric vehicles.

This project was all about extracting data, transforming it, and loading it into a usable schema in a database. Instead of extracting it from a company or school that provides an API for the purpose of providing data to web developers, we used an Excel spreadsheet that Carson uses at work to log certain mechanical events. This created an interesting situation in which “extraction” couldn’t really happen until data had been input.

Data Input

This data was logged by hand, into a notebook during mechanical inspections of the vehicles in a shared electric vehicle fleet. Inputting that data into an Excel spreadsheet was taking a ton of time, so Carson used a strategy involving a basic bash script. Inputting the paper notes into a text file called input.md, and then using the Unix concatenation function (cat) as well as the Unix translate function (tr) he made the input file into a comma-separated values file that could be easily read by excel and put into a usable worksheet much more quickly than raw input. The bash script was nothing more than cat input.md | tr " " ",  “ > output.csv  but it was exactly what was needed. 

Extraction and Transformation


The first part of the python script aggregates the various sheets from the excel workbook (each sheet represents data from a specific week) into a single Pandas data frame. This data frame includes a ton of information we don’t need, so the next step was to drop everything other than the columns with the front tire pressure data (front_PSI) and rear tire pressure data (rear_PSI). Then we used matplotlib’s extremely easy formatting to generate the graph. Doing “data = [name_of_dataframe] when calling matplotlib is pretty convenient.

We ran a little short on time however, and our original plan included an html-based flask application that could take in the data, log it into the database, and output the graphs to the console. Perhaps later we’ll develop this added functionality. In the meantime hopefully ‘Extract, Transform, Prepare for loading, and Visualize’ will be satisfactory. 

A brief note on data cleaning: this data isn’t exactly proprietary, but it’s close enough that the responsible thing for us to do was to include a scraping of all data that seemed specific to the brands and companies involved in the collection of the data. 
