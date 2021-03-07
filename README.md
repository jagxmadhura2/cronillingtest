# cronjobbilling test


The below cron job expression runs the jobs on 1st of every month at 12 am, it wil b in 24hrs format
0 0 1 * *

syntax :  minutes hours day month year

by default job status will be false >> if the cron job expression matches above one then job will trigger and job status will change to true, once all jobs finished again we have to reset the job status to false and then process repeats 

Test plan:

Scenario1:
Test by changing the minutes expression 
negative scenarios
eg: 50 0 1 * *
01 0 1 * *

postive scenario:
00 0 1 * *
00 00 1 * *
0 00 1 * *
0 0 1 * *

Scenario2:

Test by changing the hours expression
test with negative scenarios
eg: 

00 01 1 * *
01 01 1 * *
00 12 1 * *
00 24 1 * *

postivie scnearios:
00 0 1 * *
00 00 1 * * >> this is also covered as part of minutes testing so we can ignore

Scenario3:
Test by changing the day 

test with negatve inpouts
00 01 2 * *
00 00 2 * *
01 01 2 * *


Scneario4:
Test with month by providing different input values in cron expression

Scenario5: Test wtith different year as inpout values in cron expression

Scenario6: test with different combinations of minuts, hours, day, month, year


Test cases and test execution:
Write test cases for both positive and negative scenarios for all the combinations and execute 
and check whether the expression matches with our original expression ( 0 0 1 * *)

If the expression matches check the job status and check jobs is running or not >>
If the expression doesnot match job status should be false and no jobs should run
If the expression matches and still jobs are not running then check the error and file the bug

