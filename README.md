# PostMortem/Root Cause Analysis for AES EDI | JIRA Issue ( AESEDI-53447)

## Author
Davide Siluri

## Report Status
Resolved

## Outage Description
The customer data was not sent from AES EDI. The investigation showed that the file with the data was sent however, it did not get processed due to an issue with the AES CIS service.

## Affected users
Users related to EDI-CIS monitoring service.

## Start Date/Time
19/11/2019 - 11:56 AM

## End Date/Time
19/11/2019 - 01:00 PM

## Duration
1 hour and 4 minutes

## Timeline

| Time          | Description   | 
| ------------- |-------------|
| 11:56         | Discovering of the missing files |
| 12:00      | Restarting of the AES CIS monitoring module      |
| 12:15 | Starting of the data processing of the records files     |
| 13:00	        | Completion of the data processing of all the 486,000 records files

	
## Contributing Conditions Analysis
Customer created a Jira Ticket to alert us on this failure. Please refer JIRA Issue: (AESEDI-53447)
A large amount of files were not processed.

## Resolution
Reloading the AES CIS monitoring service allowed us to spot the missed records that were not discovered automatically.
Following this the data file was resent leading to the resolution.

## Recommendations
More monitoring plugins and modules to watch this critical part of our infrastructure.

Slack notifications have to be added for alerting the team whenever a data discrepancy is detected in future so that such occurences are prevented in future.

Patching opearations should not be executed while data processing is in progress at AES EDI.

