# Ticket Breakdown
We are a staffing company whose primary purpose is to book Agents at Shifts posted by Facilities on our platform. We're working on a new feature which will generate reports for our client Facilities containing info on how many hours each Agent worked in a given quarter by summing up every Shift they worked. Currently, this is how the process works:

- Data is saved in the database in the Facilities, Agents, and Shifts tables
- A function `getShiftsByFacility` is called with the Facility's id, returning all Shifts worked that quarter, including some metadata about the Agent assigned to each
- A function `generateReport` is then called with the list of Shifts. It converts them into a PDF which can be submitted by the Facility for compliance.

## You've been asked to work on a ticket. It reads:

**Currently, the id of each Agent on the reports we generate is their internal database id. We'd like to add the ability for Facilities to save their own custom ids for each Agent they work with and use that id when generating reports for them.**


Based on the information given, break this ticket down into 2-5 individual tickets to perform. Provide as much detail for each ticket as you can, including acceptance criteria, time/effort estimates, and implementation details. Feel free to make informed guesses about any unknown details - you can't guess "wrong".


You will be graded on the level of detail in each ticket, the clarity of the execution plan within and between tickets, and the intelligibility of your language. You don't need to be a native English speaker, but please proof-read your work.

## Your Breakdown Here

## Ticket RED-1

## time/effort estimates : 1hrs

## Create a new Agent customId column
  Add  a new column to Facilities, Agents, and Shifts tables  called agent_custom_id

 ## Acceptance Criteria
add new column agent_custom_id in each of the tables (Facilities, Agents, and Shifts)

## Implemention
* Create a new column agent_custom_id
* Set data type to BINARY (16)
* set the DEFAULT NOT NULL
* COMMIT CHANGES

## Ticket RED-2
## time/effort estimates : 3hrs

 Write a script that generate uuid and  update the column agent_custom_id in each of the tables (Facilities, Agents, and Shifts)

 ## Acceptance Criteria
 Write a script that generate uuid and update the rows of the column agent_custom_id in each of the tables (Facilities, Agents, and Shifts) 

 ## Implemention
* Create script with the method update CustomID(agent_custom_id)
* In the method add a query that updates each rows of the column  agent_custom_id in each of the tables (Facilities, Agents, and Shifts) 
* Run the script to enable the update of each rows of column agent_custom_id  in each of the tables (Facilities, Agents, and Shifts) 


## Ticket RED-3
## time/effort estimates : 4hrs

Create a new function  facilitiesAgents and update the function  generateReport

 ## Acceptance Criteria
create a function called facilitiesAgents and add the uuid method  to the function generateReport

 ## Implemention
* Create function  facilitiesAgents with ability to save customID into the column agent_custom_id  by generating UUID  save the record for each agents
* update generateReport function with the customID (agent_custom_id) to enable the ablity to generate report by customID (agent_custom_id)
* write unit test for both functions