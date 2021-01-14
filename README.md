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

Now, let's try calculating all the 4 values for k+1 days,

<ins>sequences of length k+1 with last 2 values 00 -> C1(k+1)</ins>:<br /> 
These can be formed by adding a 0 (mark k+1 day as absent) to existing sequences with length k and 0 at the end (absent on day k). But we cannot add 0 to sequences of length k with two 0's at the end (absent on day k and day k-1) as we are not allowed to have 3 0's in a row. So, the only way is to add 0 to k length sequences ending with '10'. So,<br />
#### C1(k+1) = C3(k)

<ins>sequences of length k+1 with last 2 values 01 -> C2(k+1)</ins>:<br />
These can be formed by adding a 1 (mark k+1 day as present) to existing sequences with length k and 0 at the end (absent on day k). So,<br />
#### C2(k+1) = C1(k)+C3(k)

<ins>sequences of length k+1 with last 2 values 10 -> C3(k+1)</ins>:<br />
These can be formed by adding a 0 (mark k+1 day as absent) to existing sequences with length k and 1 at the end (present on day k). So,<br />
#### C3(k+1) = C2(k)+C4(k)

<ins>sequences of length k+1 with last 2 values 11 -> C3(k+1)</ins>:<br />
These can be formed by adding a 1 (mark k+1 day as present) to existing sequences with length k and 1 at the end (present on day k). So,<br />
#### C4(k+1) = C2(k)+C4(k)

Now that we have the necessary equations, take the base case with n=2 where each of these counts is equal to 1 and repeat these equations to get C1(n), C2(n), C3(n), C4(n)

Total no of ways of attending classes is the sum of all 4 counts, which is C1(n)+C2(n)+C3(n)+C4(n)<br />
Total no of ways of missing the graduation (absent on last day) is the number of sequences with 0 at the end, which is C1(n) + C3(n)
