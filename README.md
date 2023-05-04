# Writing Group Survey Interpreting Tool Documentation

## Why did we create this? 
Elizabeth Schwartz created this python program to automatically interpret results of a survey intended to match respondents into sustained writing groups based on their preferences of modality, sessions per week, and length of sessions. The ultimate goal of the program is to create more options for sustained writing groups of graduate students without further burdening the WW administrative team.

## How to use it? 

This program ingests two CSV files from which it creates writing groups based on respondents overlapping preferences. It creates a csv file with rows representing emails to send that alert the user if they have been matched into a group or not. For respondents who were matched to a group, the email text provides them with their group members’ discord handles.

To use the program, first locate the survey. In the center of the top of the screen, switch from the questions tab to the Responses tab. In the upper right hand side of the responses tab, select “View in sheets.” Once in sheets, select the File tab. Hover over the Download option on the file tab. Select the “Comma Separated Values (.csv)” option. Note that we are downloading the google sheet as a comma separated values (or csv) file because this is a format that python can read more easily. 

Next, we need to create a completely blank csv file. There are a number of ways we could accomplish this, but while we’re in google sheets, we may as well stay here. Back in google sheets, select File again. At the top of the File option menu, hover over the “new” option. Select new google sheet to produce a blank sheet. On the new sheet, locate the File tab again. Hover over download, and click the CSV option. You can name this file whatever you choose, but note that it will be used to store email information. I have named mine “writing-group-emails.csv” 

*** Note that using  hyphens or underscores in file titles in lieu of spaces is best practice in python. It can ensure python is able to locate and read the names of the files you specify. 

Now that you’ve downloaded the survey results file and created an empty csv file, you’re ready to run the python program in google colab. Colab is an online version of python much like google sheets is an online version of Excel. It contains many of the same capabilities as Python, but it does not require you to actually install anything on your computer. Locate this in this github repository. 

The top of the colab notebook contains a text field with a succinct version of the steps and directions we just covered. You can ignore that for now. 

We need to actually run blocks containing code (or code cells) in the colab notebook. To do so, you can click into the cell at the top of the notebook and press your “shift” key and “return” key at the same time. This will cause the cell to run. You’ll know your cell is finished running because a small green check mark will appear on the left hand side of it. Alternatively, you can click the play button on the left hand side of a cell to run it. It is important to run all the cells in the colab notebook in the exact order they are written in. This is because the output of one cell block is necessary to run the one following it. 

The first code cell in the colab notebook contains all the python libraries we will use to run the program. After you run this cell, nothing will happen. That’s a good thing. 

The next cell you will run will cause a “Choose file” button to appear under it. Select the button, navigate to your survey results file, and upload it. Prior to running the next cell, we need to locate the file we just uploaded in the colab environment. To do so, locate the file icon on the left hand side of the page. Click on it. This should expand into a list of files and documents. Locate the file we just uploaded. If you can’t find it, it’s probably in the folder called content. Once you find the file we uploaded, right click on it. Select “copy path.” Now we can run the next cell. When that cell runs, it produces a small dialog box. Paste the file path in the box. 

In the next two cells, you will repeat this process exactly with the empty csv file you created. 

Locate the file in the left hand tab by clicking on the file icon (hint-if you can't find it, it's probably in the content folder).
Right click the file you uploaded. Select "copy path"
when prompted to input the results file path, paste the file path from your clipboard.
You will not need to do anything manually for the rest of the notebook. Just make sure to run all the remaining cells. By the last cell, you will have populated the empty csv file with writing groups and introductory emails to send them. Before you send those emails, make sure to manually review the text the last cell creates. This text contains the email address of anyone who reported a safety concern and the text they entered when asked about their safety concern. Note that often times people will enter words like “None”, “nope”, “NA”, etc. in this field. The program does not robustly weed these answers out in order to prevent accidentally discarding real safety concerns. Therefore, you will need to manually review each concern reported. 

## Limitations 

Right now the program has a number of limitations. We are only able to match people into synchronous groups (asynchronous respondents are simply emailed the link to the WW discord server). Moreover, we do not have a good way of capping the number of people in a group at the moment. The original survey design asked respondents how many people they would prefer to work with, but I discarded this question for the sake of simplicity. Lastly, the length of sessions is determined simply by averaging the session length responses for people who wanted to meet for the same number of days per week in the same modality. Another version of the program could group people based on the proximity of session durations to each other. 

The largest limitation right now is that we cannot change the survey design without needing to completely revise the survey interpreting tool. This means that if we realize the survey question text is confusing, want to expand options to it, etc., we would need someone with programming knowledge to revise the tool to match the updated survey.

To truly make this technical solution sustainable, the Writers Workshop should actively recruit students with programming interests to take on the project. We could, for example, consider inviting consultants with programming experience to join the WWCC to expand this project. Or, perhaps an undergraduate student in an incoming consultant cohort could pick up this project as part of their WRIT 300 research! Finally, through making the programming publicly available on a Writers Workshop owned GitHub repository, we could distribute it and encourage people at other writing centers to adopt similar approaches for creating sustained writing groups at their institutions. 



