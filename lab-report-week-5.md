# Lab Report 5: Researching the command grep

## Option 1(Using grep with -c)

### Example 1
```
(base) dhruv@Dhruvs-MacBook-Air-2 technical % grep -c "I" government/About_LSC/Comments_on_semiannual.txt 
47
```

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

## Option 3(Using grep with -l)
