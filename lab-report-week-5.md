# Lab Report 5: Researching the command grep

## Option 1(Using grep with -c)

### Example 1
```
(base) dhruv@Dhruvs-MacBook-Air-2 technical % grep -c "such" government/About_LSC/Comments_on_semiannual.txt 
4
```
The grep -c command checks how many lines in this specific text file have the string "such" in them. The string does not have to be a word by itself and can just be a substring of some word in the line to count. 

### Example 2
```
(base) dhruv@Dhruvs-MacBook-Air-2 technical % grep -c "I" government/About_LSC/*                         
government/About_LSC/CONFIG_STANDARDS.txt:32
government/About_LSC/Comments_on_semiannual.txt:47
government/About_LSC/LegalServCorp_v_VelazquezDissent.txt:56
government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt:53
government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt:10
government/About_LSC/ODonnell_et_al_v_LSCdecision.txt:29
government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt:55
government/About_LSC/Progress_report.txt:114
government/About_LSC/Protocol_Regarding_Access.txt:16
government/About_LSC/Special_report_to_congress.txt:58
government/About_LSC/State_Planning_Report.txt:280
government/About_LSC/State_Planning_Special_Report.txt:61
government/About_LSC/Strategic_report.txt:170
government/About_LSC/commission_report.txt:292
government/About_LSC/conference_highlights.txt:43
government/About_LSC/diversity_priorities.txt:32
government/About_LSC/reporting_system.txt:29
```
This example checks all of the text files within the folder About_LSC and returns how many lines the string "I" appears in all of them. This helps to search many files quickly. 

### Example 3
```
(base) dhruv@Dhruvs-MacBook-Air-2 technical % grep -c "secretary" 911report/* 
911report/chapter-1.txt:4
911report/chapter-10.txt:2
911report/chapter-11.txt:0
911report/chapter-12.txt:0
911report/chapter-13.1.txt:16
911report/chapter-13.2.txt:1
911report/chapter-13.3.txt:1
911report/chapter-13.4.txt:0
911report/chapter-13.5.txt:5
911report/chapter-2.txt:0
911report/chapter-3.txt:13
911report/chapter-5.txt:0
911report/chapter-6.txt:7
911report/chapter-7.txt:0
911report/chapter-8.txt:0
911report/chapter-9.txt:1
911report/preface.txt:0
```
Similar to the prior example, this example also checks within all the text files within a given folder and has the same benefit of allowing a user to search more than one file at once for a particular string. This can also be done for all of the text files within technical itself and not just smaller folders such as 911report. 

## Option 2(Using grep with -i)

### Example 1

```
(base) dhruv@Dhruvs-MacBook-Air-2 technical % grep -i "communities" government/About_LSC/Comments_on_semiannual.txt 
State Planning Initiative. Building State Justice Communities: A
state communities of justice - integrated and coordinated legal
leadership sensitivity to client communities, LSC has convened a
Client-Centered State Communities of Justice". The conference
their communities.
```

The grep -i command gives the specific lines within a given text file that have a specific substring and prints them out. 


### Example 2

```
(base) dhruv@Dhruvs-MacBook-Air-2 technical % grep -i "chairman" government/About_LSC/*
government/About_LSC/Comments_on_semiannual.txt:Douglas S. Eakeley, Chairman Legal Services Corporation May 31,
government/About_LSC/Special_report_to_congress.txt:to services provided by LSC grantees. Subcommittee Chairman Rep.
government/About_LSC/commission_report.txt:Hon. John N. Erlenborn, Chairman Professor T. Alexander
government/About_LSC/commission_report.txt:Douglas S. Eakeley, Chairman Hon. John N. Erlenborn, V
government/About_LSC/commission_report.txt:ice-Chairman Hulett H. Askew LaVeeda M. Battle Hon. John T.
government/About_LSC/commission_report.txt:appointed Mr. Casellas as Chairman of the U.S. Equal Employment
government/About_LSC/commission_report.txt:Chairman of the Board of Directors of the Philadelphia Bar
```
The grep -i command can also be used on all the text files in a given folder as shown above. When used on an entire folder, the command returns which specific text file the string was found in for each isntance of the string.  

### Example 3

```
(base) dhruv@Dhruvs-MacBook-Air-2 technical % grep -i "Wolfowitz" 911report/*
911report/chapter-10.txt:                Ashcroft, Mueller, Tenet, Deputy Secretary of Defense Paul Wolfowitz, and Cofer
911report/chapter-10.txt:                administration should do about Iraq. Deputy Secretary Wolfowitz made the case for
911report/chapter-10.txt:            Secretary Powell recalled that Wolfowitz-not Rumsfeld-argued that Iraq was ultimately
911report/chapter-10.txt:            Powell said that Wolfowitz was not able to justify his belief that Iraq was behind
911report/chapter-10.txt:                Wolfowitz's argument "much weight." Though continuing to
911report/chapter-10.txt:            Within the Pentagon, Deputy Secretary Wolfowitz continued to press the case for
911report/chapter-10.txt:                eliminating that threat. Wolfowitz contended that the odds were "far more" than 1 in
911report/chapter-10.txt:                1993 attack on the World Trade Center. 73 The next day, Wolfowitz renewed the
911report/chapter-13.4.txt:                Paul Wolfowitz interview (Jan. 20, 2004); Stephen Hadley meeting (Jan. 31, 2004).
911report/chapter-13.4.txt:            200. NSC memo, Hadley to Armitage, Wolfowitz, McLaughlin, and O'Keefe, "Next Steps on
911report/chapter-13.4.txt:            220. Paul Wolfowitz interview (Jan. 20, 2004); Donald Rumsfeld interview (Jan. 30,
911report/chapter-13.4.txt:                Wolfowitz, and Myers, "Re: Predator," July 11, 2001. On Rice's intervention, see
911report/chapter-13.4.txt:            245. NSC memo, Hadley to Armitage, Wolfowitz, Myers, and McLaughlin, resolving
911report/chapter-13.5.txt:                Wolfowitz's position on Iraq, see Bob Woodward, Bush at War (Simon &
911report/chapter-13.5.txt:                recollection of Wolfowitz's remarks at Camp David. DOD transcript, "Secretary
911report/chapter-13.5.txt:            73. DOD memo, Wolfowitz to Rumsfeld, "Preventing More Events," Sept. 17, 2001. We
911report/chapter-13.5.txt:                bombing. Wolfowitz added in his memo that he had attempted in June to get the CIA to
911report/chapter-13.5.txt:            74. DOD memo, Wolfowitz to Rumsfeld, "Were We Asleep?" Sept. 18, 2001.
911report/chapter-13.5.txt:            22. DOD memo, Rumsfeld to Myers, Wolfowitz, Pace, and Feith, "Global War on
911report/chapter-6.txt:                too much time had passed and his deputy, Paul Wolfowitz, thought that the Cole
911report/chapter-6.txt:                Secretary Wolfowitz was confirmed in March 2001 and Under Secretary of Defense for
911report/chapter-6.txt:                Wolfowitz took the position that the CIA should have to pay for it; the CIA
911report/chapter-6.txt:                Wolfowitz, and Joint Chiefs Vice Chairman Richard Myers to deploy Predators capable
911report/chapter-6.txt:            The Defense Department favored strong action. Deputy Secretary Wolfowitz questioned
911report/chapter-8.txt:                Tenet in July that Deputy Secretary of Defense Paul Wolfowitz questioned the
```

The grep -i command is used on an entire folder in the same way as above showing all the lines within the 911report folder that have the string "secretary". It is useful for finding the context of specific words/strings within specific text files. 

## Option 3(Using grep with -l)


### Example 1
```
(base) dhruv@Dhruvs-MacBook-Air-2 technical % grep -l "government" biomed/* 
biomed/1471-2091-2-12.txt
biomed/1471-2253-2-4.txt
biomed/1471-2296-3-3.txt
biomed/1471-2318-3-2.txt
biomed/1471-2350-4-6.txt
biomed/1471-2377-3-4.txt
biomed/1471-244X-2-9.txt
biomed/1471-2458-2-16.txt
biomed/1471-2458-2-3.txt
biomed/1472-6882-1-12.txt
biomed/1472-6947-1-5.txt
biomed/1472-6947-2-7.txt
biomed/1472-6947-3-5.txt
biomed/1472-6963-1-8.txt
biomed/1472-6963-3-1.txt
biomed/1472-6963-3-7.txt
biomed/1475-2875-1-14.txt
biomed/1475-2875-2-10.txt
biomed/1475-9276-1-3.txt
biomed/1476-069X-1-3.txt
biomed/1476-069X-2-9.txt
```

The grep -l command prints out which text files have a given string. This is similar to the grep -c command except it does not return how many lines in each file have the particular string.


### Example 2
```
(base) dhruv@Dhruvs-MacBook-Air-2 technical % grep -l "communities" government/About_LSC/*
government/About_LSC/CONFIG_STANDARDS.txt
government/About_LSC/Comments_on_semiannual.txt
government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
government/About_LSC/Progress_report.txt
government/About_LSC/State_Planning_Report.txt
government/About_LSC/State_Planning_Special_Report.txt
government/About_LSC/Strategic_report.txt
government/About_LSC/commission_report.txt
government/About_LSC/conference_highlights.txt
government/About_LSC/diversity_priorities.txt
government/About_LSC/reporting_system.txt
```
This example is also run on a entire folder of text files. It is important to note that running -l or any of these three commands on a single file is not very helpful because searching a single file for a substring can be easily done without terminal commands. 

### Example 3
```
(base) dhruv@Dhruvs-MacBook-Air-2 technical % grep -l "Wolfowitz" 911report/*
911report/chapter-10.txt
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-6.txt
911report/chapter-8.txt
```
This example is also run on a entire folder of text files like the first two examples. This command can save time in checking if a folder has a particular string. A particular use might be trying to find which files are written by a specific author. 
