Problem Statement :

In this project Create a dashboard in Power BI for the call center manager that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset.

Possible KPIs include (but not limited to):

Overall customer satisfaction

Overall calls answered/abandoned

Calls by time

Average speed of answer

Agent’s performance quadrant -> average handle time (talk duration) vs calls answered

Data Analysis (DAX):

Average of seed of answerd = AVERAGE('Sheet 1'[Speed of answer in seconds])

Average of statisfaction = AVERAGE('Sheet 1'[Satisfaction rating])

Count satisfation rating = COUNT('Sheet 1'[Satisfaction rating])

Possitive satisfation rating = CALCULATE(COUNT('Sheet 1'[Satisfaction rating]),FILTER('Sheet 1','Sheet 1'[Satisfaction rating] IN {4,5}))

Overall Customer Satisfation = DIVIDE([Possitive satisfation rating],[Count satisfation rating],0)

resolved calls = COUNTX(FILTER('Sheet 1','Sheet 1'[Resolved] = "Yes"), 'Sheet 1'[Resolved])

Unresolved calls = COUNTX(FILTER('Sheet 1','call centre trends'[Resolved] = "No"), 'Sheet 1'[Resolved])

total calls = CALCULATE('Sheet 1'[total calls answered] + 'Sheet 1'[total calls unanswred])

total calls answered = COUNTX(FILTER('Sheet 1','Sheet 1'[Answered (Y/N)] = "Yes"),'Sheet 1'[Answered (Y/N)])

total calls unanswred =COUNTX(FILTER('Sheet 1','Sheet 1'[Answered (Y/N)] = "No"), 'Sheet 1'[Answered (Y/N)])
