# DNA Analyzer

The  DNA Analyzer is command line tool to perform a variety of RCA / Log Analyzer, Various application related data collection from postgres database table, Finding inconsistent data existence from various application related postgres table and Search Known defect based on Log Analyzer result.

This tool uses various CLI Show command in DNAC, Show command in postgres tables and Makes REST API calls to CDETS Application. This toool is completely read only and it will not perform any write operation into DNAC Application.
 
#**History:**

As part of SDA Escalation Engineer, Devloper or DevTest Engineer, we have to analyze the DNAC RCA log files every day and sometimes needs to analyze multiple files to find needle in hayes stack. In order to avoid such laboriour process and spending time on repeated task, SDA escalation team prepared this Log Analyzer scripts which will find the task success/failure details from the log.

**For Escalation team:**
This will help reduce the burden of going through line by line in log file.

**For Develper/Test Engineer:**
This tool will help in day-to-day task of quickly determing the failures and enhance the code wherever it requires. This can allow them to spend time on other code and feature devleopment/testing.

**For TAC Engineer:**
This tool will help reduce number of BEMS case as it will help find the error which can be searched in known issue list.


#**Usage Example:**


##To Download

This script needs to be downloaded onto Cisco DNA Center.  First ssh to DNAC.

```
ssh -p 2222 maglev@<dnacIP>
```

The next step is to get the script onto Cisco DNA Center.  

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

There will be a directory called dna-analyzer.  You can either change into directory, or run direct from the home directory.
You will be showing menu and options and rest of them are self explanatory.
```
$ ./dna-analyzer/DNA_Analyzer

*****************************************************************************
*****************************************************************************
*****                                                                   *****
*****          Welcome to the Cisco DNA Center Analyzer Tool            *****
*****                         Version 1.0.2                             *****
*****                                                                   *****
*****************************************************************************
*****************************************************************************



						 Cisco DNAC Data Analyzer
		 Options
			 1 -> Log Analyzer 
			 2 -> Database Data Collection 
			 3 -> Database Compliance checker 
			 4 -> SDA Audit and Telemetry 
			 6 -> Search Known Cisco External Defect / Issues 
			 7 -> Exit 


	 For Feedback/Support Reachout : log-analyzer-feedback@cisco.com

***************************************************************************

```

# Logs and Output files
After the script finishes the logs and report will be available fore references.
## Report and Logs can be found at:
 Cisco DNA Center Analyzer Tool logs will be available in ./dna_analyzer_logs and Reports will be available in ./dna_analyzer/reports. 
 Collect all the logs and attach to Service request if you are seeking help from escalation BU.


