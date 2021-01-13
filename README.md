## Question

In a university, your attendance determines whether you will be allowed to attend your graduation ceremony. You are not allowed to miss classes for three or more consecutive days. 
Your graduation ceremony is on the last day of the academic year, which is the Nth day.

Your task is to determine the following:

1. The number of ways to attend classes over N days.
2. The probability that you will miss your graduation ceremony.

## Solution Explanation

Consider the number of possible ways to attend classes for k days, with out missing 3 or more days consecutively to be C(k)

There are 4 different possibilities of attendence in the last 2 days (1 - present, 0 - absent) <br />
00, 01, 10, 11

Consider count of combinations ending with <br />
'00' as C1(k),<br />
'01' as C2(k),<br />
'10' as C3(k),<br />
'11' as C4(k)<br />

C(k) = C1(k) + C2(k) + C3(k) + C4(k)

For k+1 days, C1(k+1) is the same as C3(k) (adding 0 for the k+1 th day)<br />
Other values can be calculated similiarly for k+1 days

Now that we have the necessary equations, we iterate these for n days and get the necessary values
