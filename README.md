# Is NSS Worth it?


### Motivation

---

As a recent college graduate eager to enter the tech industry without an income or significant savings to my name, I was curious whether or not I was getting my money's worth by attending Nashville Software School (NSS). My decicion to enroll was mostly prompted by the success stories of friends and family who have gone through different programs at NSS before me, which gave me a sense of confidence in the ability of NSS to prepare its students for entering the tech workforce. Though this confidence wasn't unwarranted, I hadn't ever looked at reporting results for any other similar bootcamps. Although there are not that many competitors in the Nashville area, the COVID-19 pandemic has prompted many bootcamps around the country to move to fully remote schooling, opening up many more potential options for prospective bootcamp students such as myself.

NSS's marketing material advertises its high graduation and job placement rates, which are extremely appealing to prospective students, but I began to wonder, what kinds of results are other bootcamps generating? Are NSS's results special? Are they common? Knowing what I do now, if I had the choice to select a different bootcamp, would I be incentivized to?

### Data Questions

---

1. Are prospective students incentivized to choose NSS over other bootcamps, if given the opportunity?
1. How well does NSS and its competitors prepare their students for success?
2. What are those competitors excelling at where NSS is not?

### Technologies Used and Data Sources

---

#### Technologies
- Python
	- [Jupyter Notebooks](https://jupyter.org/)
	- [pandas](https://pandas.pydata.org/)
	- [matplotlib](https://matplotlib.org/)
	- [requests](https://pypi.org/project/requests/)
	- [beautifulsoup4](https://pypi.org/project/beautifulsoup4/)
	- [numpy](https://numpy.org/)
- [iLovePDF](https://www.ilovepdf.com/)
- Microsoft Excel
- Google Slides

#### Data Sources
- [Council on Integrity in Results Reporting (CIRR)](https://cirr.org/)
	- [Tech Elevator](https://www.techelevator.com/locations/coding-bootcamp-detroit-michigan/)
	- [Hack Reactor](https://www.hackreactor.com/)
	- [Project Shift (now Parsity)](https://projectshift.io/)
	- [Hack Upstate Careers in Code](https://careersincode.org/)
	- [Codeup](https://codeup.com/)
	- [Code Platoon](https://www.codeplatoon.org/)
	- [Codesmith](https://www.codesmith.io/)
	- [Epicodus](https://www.epicodus.com/)
	- [Full Stack Academy](https://www.fullstackacademy.com/tech-bootcamp)
	- [Launch Academy](https://launchacademy.com/)
- [Nashville Software School](https://nashvillesoftwareschool.com/programs/web-developer-full-time/)
- [Tennessee Higher Education Commission (THEC)](https://www.tn.gov/content/dam/tn/thec/bureau/student_aid_and_compliance/dpsa/apr/2021/1769%20Nashville%20Software%20School%20Inc%20-%20APR%202020-2021.pdf)
- [Livingcost.org](https://livingcost.org/)

### Data Acquisition

---

In order to make any sort of meaningful comparison between bootcamps, I first had to establish criteria that might serve as some sort of control between every bootcamp examined. The criteria I chose was as follows:

	1. In the United States
    2. Similar Bootcamp Program Structure
        - Full Stack Web Development, divided into front-end and back-end sections
    3. Council on Integrity in Results Reporting (CIRR) certified

This last condition was recommened to me by an NSS administrator, who showed me that CIRR certified data reports all share an identical format. Using data that did not already share formatting would have extended the length of this project by months, if it was able to be completed at all. It is worth noting that NSS is not CIRR certified, but THEC data reports contain much of the same information that bridging the gap between formats is not too grand a task. I did not select any other programs within the state of Tennessee, so NSS remains the only data report pulled from THEC at this time.

One other distinction I made between selected bootcamps was the 'type' of city each bootcamp was in. NSS states that part of its purpose is to feed the growing tech industry in the city of Nashville. Many bootcamps, however, were not in cities with small and immature tech industries, but rather, highly populated metropolises with local, established industry dynamics. Thus, for the ten bootcamps I selected to compare to NSS, 5 are located in "up and coming" cities, of which I consider Nashville to be, and 5 are in "tech hub" cities, with higher populations, increased job prospects, and various centers of learning that the former group have not yet had the chance to create.

All data sets pulled consisted of tables in pdf form. All CIRR certified reports were at least two pages long, containing one or more non-tabular summary page(s) preceding their results table on the final page. NSS's THEC report consisted of a single table split across three pages, with each page maintaining the same rows, but varying columns.

Furthermore, part of my analysis included the use of State costs of living. Using the website livingcost.org, I webscraped a table that contained all the costs of living by US state, converting it to a pandas dataframe for use as needed.

Finally, a separate part of my analysis made use of the tuitions and durations of each program. This information was not readily available in a single dataset, so I had to compile that information independently from each bootcamp's website, putting them into a table through excel, converting it to a CSV file, then reading that in through pandas methods.

### Data Cleaning

---

I relied heavily on the website ilovepdf.com to do much of my data cleaning. For all CIRR certified datasets, I had to strip only the final page of each report, convert each newly-single-paged pdf to an excel sheet, save each excel sheet as a CSV file, then read it in through pandas as a dataframe. The structure of these dataframes were a little messy, since the original table was likely not intended to be in CSV format, but since all CIRR certified files shared the same format, all that was necessary was locating the position of any relevant data within the data frame for a single file; This was also the location of the respective data for every other CIRR file.

NSS's data was handled very slightly differently. Instead of stripping a single page, like all CIRR files, I had to strip each page individually, convert each page to an excel, save as a CSV, bring it into my Jupyter notebook as three separate dataframes, and finally, merge all three together on row names (since each page had identical row formatting), thus creating a single dataframe containing all of the NSS data from the THEC report.

Unfortunately, the CIRR reports and the THEC report did not contain exactly identical data, so my analysis, which was contingent on the comparison of bootcamps, is necessarily limited in scope until additional data for both sets of bootcamps can be collected.

At this time, my application of these datasets is extremely inefficient leading up to the final charts generated in my Jupyter notebook. I intend to rectify this by combining all relevant data into a single useable dataframe from which I can pull information to construct my analysis, a process I have already begun, but not yet completed by the delivery date of this project (January 5, 2023)

### Data Presentation

---

The method used to compare different facets of my presentation was to implement graphics throught the matplotlib.pyplot Python package. Following that, I constructed a Google Slides presentation to showcase my analysis and associated caveats, my findings, and the response to my data questions. This slide deck is converted to a PDF and available within this repo
