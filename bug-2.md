\# Bug 2



\## Title



Statistics total count does not match displayed books



\## Severity



Medium



\## Steps to Reproduce



1\. Open application

2\. View book list

3\. Call /api/stats



\## Expected Result



Total count should equal displayed books.



\## Actual Result



API returned:



{

&#x20; "total": 7

}



Displayed books did not match reported total.



\## Evidence



/api/stats response and screenshot.



