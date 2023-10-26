# DNA Analyzer

The  DNA Analyzer is a command line tool to perform a variety of RCA / Log Analyzer, Various application data collection from Postgres database table, Finding inconsistent data existence from various application related Postgres table and Search Known defects based on Log Analyzer result.

This tool uses various CLI Show commands in DNAC, Show commands in Postgres tables, and makes REST API calls to the CDETS Application. This tool is completely read-only and it will not perform any write operation into DNAC Application.
 
#**History:**

As part of  SDA Escalation Engineer, Developer, or DevTest Engineer, we have to analyze the DNAC RCA log files every day and sometimes need to analyze multiple files to find needle in hayes stack. In order to avoid such a laborious process and spending time on repeated tasks, SDA escalation team prepared this Log Analyzer script which will find the task success/failure details from the log.

**For Escalation team:**
This will help reduce the burden of going through line by line in a log file.

**For Developer/Test Engineer:**
This tool will help in the day-to-day tasks of quickly determining the failures and enhancing the code wherever it is required. This can allow them to spend time on other code and feature development/testing.

**For TAC Engineer:**
This tool will help reduce the number of BEMS cases as it will help find the error which can be searched in a known issue list.


#**Usage Example:**


##To Download

This script needs to be downloaded onto the Cisco DNA Center.  First ssh to DNAC.

```
ssh -p 2222 maglev@<dnacIP>
```

The next step is to get the script onto the Cisco DNA Center.  

There are three ways of doing this, depending on access from DNAC to the internet
 
### Option 1.  git clone direct
If you have access to the internet from DNAC, can clone the repository (containing the executable)

```
git clone https://github.com/CiscoDevNet/DNA_Analyzer
```
### Option 2. git clone via proxy
If DNAC needs a proxy to get to the internet, you will need to provide a proxy for git command.
NOTE:  please do not set a permanent environment variable as this will stop you from accessing some DNAC commands like maglev.

The example below uses an inline environment variable, just for the git command.  Make sure to put in the correct proxy url (including port) 
```
https_proxy=https://<your proxy> git clone https://github.com/CiscoDevNet/DNA_Analyzer
```

### Option 3. Isolated environment.  
You will need to clone (using method 1 or 2) to an intermediate machine and copy to DNAC, using scp.  Remember to use port 2222 with the -P option to scp.
```
scp -P 2222 ./dna_analyzer  maglev@<mydnac>:
```


## To get the latest version
We are adding new features quite often.  If you have downloaded an older version, it is very easy to get the latest.  Provided you used option #1 or #2, you can simply change directory into the dna-analyzer directory and use git pull, instead of git clone.  You might need to provide proxy as in option #2.
```
$ cd ./dna_analyzer 
$ git pull

chmod 755 *
```

## To Run

There will be a directory called dna-analyzer.  You can either change into the directory or run directly from the home directory.
You will be showing the menu and options and the rest of them are self-explanatory.
```
$ ./dna-analyzer/DNA_Analyzer

*****************************************************************************
*****************************************************************************
*****                                                                   *****
*****          Welcome to the Cisco DNA Center Analyzer Tool            *****
*****                         Version 2.1.1                             *****
*****                                                                   *****
*****************************************************************************
*****************************************************************************


                                                 Cisco DNAC Data Analyzer
                 Options
                         1 -> Debug Bundle Collector 
                         2 -> Log Analyzer 
                         3 -> Database Data Collection 
                         4 -> Database Compliance checker 
                         5 -> SDA Audit and Telemetry 
                         6 -> Search Known Cisco External Defect / Issues 
                         7 -> Apply Workaround for a Known Defect 
                         8 -> Exit 


         For Feedback/Support Reach out : log-analyzer-feedback@cisco.com

***************************************************************************


```

# Logs and Output files
After the script finishes the logs and report will be available fore references.
## Report and Logs can be found at:
 Cisco DNA Center Analyzer Tool logs will be available in ./dna_analyzer , ./dna_analyzer_logs and Reports will be available in ./dna_analyzer/reports. 
 Collect all the logs and attach to Service request if you are seeking help from escalation BU.


