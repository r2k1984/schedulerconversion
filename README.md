# schedulerconversion
Tool developed  has the capability to interpret exports from the ROBO scheduler and generate an XML file that can be understood by Control-M. This XML file facilitates the import of batch schedule definitions into Control-M. The following steps outline the process to be followed when using this tool:

Export the required information from the ROBO scheduler. This export will contain the necessary data related to the batch schedule definitions. Exporting of the details from the scheduler are performed by the admins . Below are the fields from the old scheduler to be exported.

**Application Details:**

APPLICATION : [Insert Application Name]

SUB_APPLICATION : [Insert Sub Application Name]

**Job Details:**

JOBNAME : [Insert Job Name]

DESCRIPTION : [Insert Detailed Description of the Job]

RUN_AS : [Insert User ID for Job Triggering]

CRITICAL : [Insert Criticality Level of the Job]

CYCLIC : [Indicate if the Process is Cyclic or Not]

INTERVAL : [Insert Interval at which the Cyclic Process Needs to be Triggered]


**Execution Details:**

CMDLINE : [Insert Command to be Triggered]

MAXWAIT : [Insert Maximum Wait Duration for the Job]

MAXRERUN : [Insert Maximum Number of Reruns Allowed for the Job]

AUTOARCH : [Indicate Whether the Job Can be Auto Archived]


**Time and Schedule Details:**

TIMEFROM : [Insert Time from which the Job Can be Triggered]

TIMETO : [Insert Time until which the Job Can be Triggered]

DAYS : [Insert List of Days on which the Job is Triggered]

Month: [Insert List of Months in which the Job Can be Triggered]

DAYS_AND_OR : [Insert Days with Specific Conditions]


**Additional Job Settings:**

USE_INSTREAM_JCL : [Indicate Whether the Job Uses Instream Job]

NAME : [Insert Name(s) to be Notified in Case of Job Failure]

ONFAIL : [Specify the Next Action to be Taken on Job Failure]

ONOK  [Specify the Process to Notify on Job Success]

TIMEZONE : [Specify the Timezone of the Job]


Please note that the above information is a general representation based on the provided details. Modify the content as per the specific values and requirements for each field in your actual application.

Open the provided Excel sheet and populate it with the information obtained from the ROBO scheduler export. It is crucial to ensure that all the relevant details are accurately entered into the Excel sheet. This includes job names, schedules, dependencies, and any other relevant information.

**Job Settings:**

FOLDER_DATACENTER: Specifies the data center environment for the folder, indicating whether it is intended for development, testing, quality assurance (QA), or production (Prod).

VERSION: Indicates the version of Control-M to be used, such as 9.19, 9.20, or 9.21.

PLATFORM: Indicates the operating system platform on which the job will run, such as Unix or Windows.

FOLDER_NAME: The name assigned to the folder where all the scripts will be loaded.

REAL_FOLDER_ID: The unique folder ID assigned by the system.

PARENT_FOLDER: Specifies the name of the parent folder if the current folder is a subfolder.

LAST_UPLOAD: The date when the folder was last uploaded or modified.

JOBISN: The unique identifier (ID) of the job within the Control-M system.

CREATED_BY: The username of the user who created the job.

TASKTYPE: Indicates whether the job to be triggered is a command or a script.

NODEID: Specifies the ID of the node where the script should be triggered if there are agents running in multiple instances.

CREATION_USER: The user ID of the creator of the script.

CREATION_DATE: The date when the script was initially created.

CREATION_TIME: The time of day when the script was initially created.

CHANGE_USERID: The user ID of the person who made changes to the script.

CHANGE_DATE: The date when changes were made to the script.

CHANGE_TIME: The time of day when changes were made to the script.

RULE_BASED_CALENDAR_RELATIONSHIP: Indicates the relationship between jobs if there are dependencies, represented by the letter 'O'.

APPL_TYPE: Specifies the type or category of the application associated with the job.

MULTY_AGENT: Indicates whether the job is triggered on multiple agents or a single agent.

ACTIVE_FROM: Specifies the date from which the job should become active and start running.

IS_CURRENT_VERSION: Indicates whether the job is the current version or an older version.

VERSION_SERIAL: The version number assigned to the job.

VERSION_HOST: Specifies the host on which the job is triggered.

CYCLIC_TOLERANCE: Specifies the number of times a cyclic job can be triggered in case of failure or errors.

CYCLIC_TYPE: Indicates whether the job is a cyclic job, which is a job that repeats on a predefined schedule.


After updating the Excel sheet, execute the included Excel macro. This macro is designed to process the data and generate an XML output file specifically tailored for importing into Control-M. The macro will analyze the information provided in the Excel sheet and transform it into a format that Control-M can understand.

Excel macro contains 70+ fields from the robo scheduler such as schedule name, job name , frequency, duration , alerting mechanism contact mechanism and dependencies. All the information need to be captured in the excel sheet from ROBO scheduler to 

Once the XML output file is created, proceed with the import process in Control-M. This step involves using the Control-M interface or any designated import functionality to import the generated XML file. This import operation serves to validate that all the jobs and associated details are correctly imported into Control-M.

By following these steps, the custom-built tool streamlines the process of migrating batch schedule definitions from ROBO scheduler to Control-M. It automates the conversion of exported data into a compatible format, enabling a seamless transition and ensuring accurate import of the scheduling information.


**Execution of the tool**

1. Download the Excel Macro File.
2. Update the data in the excel sheet.
3. Make sure to update the output file path Open "C:\control-m\jobs.xml" For Output As #2 to appropriate path.
4. Execute the macro "controlm_XML_Creation_Macro" and XML file will be created.
5. XML file created is not formatted and control-m only accepts formatted XML statements.
6. Use any of the tools available in internet or notepad++ XML parser to parse the xml. You can use Chrome to parse the XML as well.
7. Once the XML is parsed it will be loaded in to control-m using import option.

