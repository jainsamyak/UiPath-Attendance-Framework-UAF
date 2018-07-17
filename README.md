# UIPath Attendance Framework (UAF)
#### An attendance management framework built solely on UiPath

## Key features of the framework
- Automatic merging of attendance files (format:.xlsx)
- Attendance timestamping and auditing
- Automatic reporting of students below attendance threshold 
- Email Notifications
- Scalable, customisable and easy to manage
---

## Initial setup
When launching for the first time, the Framework will ask for a number of parameters to be input from the user. These parameters are global settings used across the framework and are stored in the **Config.xlsx** file in Data folder.

## UiPath Packages Required
- UiPath.Excel.Activities
- UiPath.Mail.Activities
- UiPath.Web.Activities

## Storing attendance files
Depending upon the input location, the user is expected to store attendance files batchwise, i.e a separate folder for each batch. Inside the batch folder, attendance files across various subjects/departments may be stored. 

**NOTE: It is expected that each attendance file in a folder contains attendance of only one subject. Please refer the sample files in the 'Data\Demo' folder for format and details.** 

## Calculation of Overall Attendance
The framework processes attendance batchwise, and once launched, UAF calculates the overall attendance for each record in each head and merges them into the "Summary.xlsx" file (by default) and stores the file in the Output directory under the Batch folder. 

**NOTE: The number of sessions in each attendance file is crucial for processing and the cell containing the information must be configured accordingly in the "Config.xlsx" file.**

## Reporting of Low Attendance
The framework offers the fetaure of automatic reporting of people below the given attendance threshold. The activity requires an Outlook account to be set up on the system through which the mails would be sent.

---

## States and their corresponding functions
```
1. Check initialized: Checks if the framework has been setup and launched atleast once.
2. Init: Initializes all system parameters
3. Check More Batches: Checks if batches are remaining to be processed.
4. Read Attendance File: Invokes "Read Attendance.xaml" and builds an array of Datatables containing overall attendance for each head.
5. Generate Summary: Creates the aggregated summary file and appends the overall attendance of each record in each head.
6. Notify: Reads the summary created and notifies the people below threshold attendance.  
```
## LICENSE
MIT License
Please view the [LICENSE]() file for more details.




