# Publication 78 Data

From: https://www.irs.gov/charities-non-profits/tax-exempt-organization-search-bulk-data-downloads

> Using the link below, you may download as a zipped text file the most recent list of organizations eligible to receive tax-deductible charitable contributions (Pub. 78 data). The download file is a large compressed file, from which you may extract a very large delimited text file. This file is updated monthly. Opening the file using word processing software may prevent formatting/appearance issues that may be present if the file is viewed with a text editing program.

Format: Pipe-Delimited ASCII Text

Download Organizations Eligible to Receive Tax-Deductible Charitable Contributions


```r
file.url <- "https://apps.irs.gov/pub/epostcard/data-download-pub78.zip"

download.file( url=file.url, "pub78.zip" )

unzip( "pub78.zip" )

file.remove( "pub78.zip" )

pub78 <- read.delim( file="data-download-pub78.txt", 
            header = FALSE, 
            sep = "|", 
            quote = "",
            dec = ".", 
            fill = TRUE,  
            colClasses="character"
          )

names( pub78 ) <- c("EIN","Name","City","State","Country","CharityType")
```
