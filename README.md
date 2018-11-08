## read_summary_file
Description: a function to read CKiD/MOAD, data summary files into R with column names     
Required Packages: dplyr, readr
Optional Packages: Hmisc 
## Usage 
```
read_summary_file(filename, server = T, location = 'K:', type = 'common', keep = NA, drop = NA)
```

## Arguments                                                            
**filename**    name of the file that you are interested in reading in. Needs to be written in quotes to properly run.

**server**      logical. TRUE if you are pulling data from the server (e.g. K drive).                                            
            location    file location. if server = TRUE, this should be 'K:' if server = FALSE, location should be a vector of length
            2, with the location of the .data file first, and the location of the .ndx file second. No backslash at the end of the file 
            locations.                                  
            
**type**        common or current.                                        

**keep**        any variables to keep. will drop all others. case sensitive

**drop**        any variables to drop. will keep all others. case sensitive 

**Note:** for keep and drop, you can use the function      
           Cs(var1, var2, ...) instead of c('var1', 'var2', ...) to save time                                                  
## Example:                                                              
```
     cardio <- read_summary_file(filename = 'cardio')           
     kidhist <- read_summary_file(filename = 'kidhist',         
                keep = Cs(KID, DOB, MALE1FE0, GNGDIAG)) 
```
