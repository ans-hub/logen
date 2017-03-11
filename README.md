# Logen (Logs Generator)

This bash script is provides generate mock data for test applications, that needs to work with dates range in different files. Script putting lines like "4832 2980 date 21390" in text files or gz archives.

## Usage

Usage of this script is explained by the example for generating string like *"%d5 %d5 %d5 date %d5"*. 

### Install
~~~~
git clone https://github.com/ans-hub/logen.git
~~~~

### Make script executable:
~~~~
$ chmod +x logen
~~~~

### Make symbolic link to script
~~~~ 
$ sudo ln -s ~/folder_with_logen_app/logen /usr/local/bin/logen
~~~~
*Note: in next steps all code writed without "./", as if you have performed command above.*

### Read built-in help for command usage:
~~~~
$ logen -h
~~~~
### Build options for script and test it in shell:
~~~~
$ logen -o "data" -d "[%Y-%b-%d:%H:%M:%S" -s 4 -g "4,5,\040,3" "2016-12-29 12:34:00" "2017-01-07 11:03:00"
~~~~
The command above will have generated 10 files with date string like "21782 35321 [2016-12-29:12:34:00 43212" and interval with 4 seconds. By default, logen script change mtime of created files.

## More examples:
Examples with different mock data source you may find in test case script "logen_test_main" or "logen_test_perfomance"
Real usage of logen script in test cases you may see in the [Dasp](https://github.io/ans-hub/dasp) script

## Recemmendations:

Use -t option to improve perfomance

## Known issues:

Auto packing generated data in gz archive is planned in the next versions