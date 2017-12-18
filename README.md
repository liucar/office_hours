An office hour simulator that models a professor meeting students during office hours. The driver program will run 100 office hour simulations. It uses a priority queue to model students standing in line and a multimap to store student names and their topics.

## Contents:

	*  office_hours_driver.cpp
	*  office_hours.h
	*  office_hours.cpp
	*  topics.txt
	*  names.txt
	*  README.txt

## How to Run:

	1. Compile the program using your compiler (making sure that
	   “topics.txt” and “names.txt” is in the same directory)

	2. Run the driver program in the command prompt or IDE

	3. The program loops the office hour simulation 100 times. 
	   Every student is randomly assigned a name from
	   “names.txt” (10 names) and a random topic from “topics.txt”
           (10 topics). 

	4. The following are output to console:

	   Every minute (modeled as 1 second in time):
		* If a meeting is in session (0 for False, 1 for True)
		* Number of students in line
		* A timer keeping track of minutes elapsed

	   Alerts:
		* New Arrival *
			- Student’s service rate (minutes)
			- Student’s arrival probability (percentage)
			- Student’s urgency (1-3, 3 being top priority)
			- Student’s topic (from “topics.txt”)

		** New Student Meeting **
			- Student’s wait (minutes)
			- Student’s service rate
			- Student’s urgency
			- Student’s topic

	   End of every office hour:
		* Total number of students served
		* Sum of all wait times
		* Sum of all meeting times
		* Minutes professor stayed past hour
		* A dividing line “—————————————“

	   End of 100 simulations:
		* Average student wait time
		* Average student meet time
		* Average professor overtime

	   
	5. The following reports are generated:

	   “report.txt” - Logs every time a student goes to office hours
			  (Name, Topic, OH#) and at the end, calculates 
			  total number of office hour visits

	   “sorted.txt” - Sort function results. To use sort function:
			  
			  sort(“report.txt”, 
				“studentName” or “questionTopic”, 
				“ascending” or “descending”);

	   “search.txt” - Search function results. To use 
			  search function:
			  
			   search(“report.txt”, 
				  studentName” or “questionTopic”, 
				  desired name or topic as a string);
	   

## Usage Notes:

-   Office hours run for 1 hour (modeled as 1 minute in time).
	   No new arrivals occur after 1 hour, but the simulation can 
	   go overtime if there are still students waiting to meet 
	   with the professor. The professor will stay until there 
	   are no more students.
	
-  Service rate is a random integer between 5 to 20 min

- Probability of arrival is randomly between [0%, 20%)

- Urgency is randomly between 1 to 3. Students with 
	   questions of urgency 3 will be met with first, then 2’s,
	   and then 1’s. (However, they will not interrupt a lower
	   priority meeting already in session.)
