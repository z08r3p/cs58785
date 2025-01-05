java cAssignment – Spatial Data and Asset / Facilities Management Submission Date: see Moodle, note pre-submission topic declaration Submission Method (links to all forms on Moodle):
o Submission
▪ A PDF of your pyramid, uploaded via Moodle / Turnitin
▪ Completing an online form with information about the decisions
you are making
▪ Five separate SQL scripts via an online form
▪ A PDF of your map uploaded via Moodle/Turnitin
▪ A PDF of your 3D visualisation uploaded via Moodle/Turnitin
This assignment is worth 70% of the marks for the module.
- An assignment is an independent piece of work:
o Your work should not be identical to, or similar to, that of any other student or the work we do in class. Please make sure you follow all UCL procedures for academic integrity.
o Discussing your assignment work or sharing your work with other students or having very similar answers is collusion.
- If you have questions about this assignment, please post them on Moodle
- That way everyone is given the same information
- That way I remember what I’ve said to you and don’t mark you down for doing
something that I wasn’t expecting
- Any questions should be generic – as this is an assessment which will gauge
how much you’ve learned during the module I won’t be able to solve very
specific assignment-related problems for you.
- Do not post any part of your assignment answer on Moodle
- The deadline for posting questions is 5 days before the assignment deadline
- This is a digital submission – it is up to you to ensure that the files you upload to Turnitin or the online submission process are not corrupt in any way (in Turnitin you might be able to do this by downloading the uploaded files to check them, for the online submissions you will receive an e-mail which you should keep as evidence of successful submission)
   o Pre-Submission –
 ▪ Declare your topic title, description and the names, geometry
 types and dimensions of your three location-based, nested, assets
 – to avoid risks of plagiarism your topic area should come from
 the existing list. Online form, first come first served
    - We reserve the right to block the Moodle forum if too many questions are
 asked multiple times and/or if questions are asked where the answer is in the
 assignment text. This would mean that none of your fellow students will be
 able to ask questions so be very careful!
   NB: You are limited to a maximum of 10 e-mails per day to avoid overloading
 the testing system
Page 1 of 15

Database Design and Build (70%)
Overview
The assignment involves the selection of a location-based asset management topic of your choice for which you will create a hierarchical pyramid to show how the features (assets) and decisions based on information about those features nest upwards.
The pyramid should have 3 levels of spatial nesting
You will then make a list of 7 decisions. Two of the decisions MUST use data output from lower level decisions (i.e. bottom-> middle and middle -> top). All decisions should relate to ONE level of the pyramid (up to you which level for the other decisions).
You will then create the physical database for your topic, insert some data and demonstrate using queries how this data can be used as evidence for the decisions.
   Page 2 of 15

Step 1 - Topic Pre-Selection/Declaration (online form, link on Moodle)
See Moodle for details of where the topic list has been sourced from.
Select a topic and provide a topic title and list your three spatial asset tablenames and geometry types and dimensions. These must be nested (i.e. the top level contains the middle level and the middle level contains the bottom level)1:
• The top level should be a 3D volume
• The middle level should be a 3D volume or a 2D area (provided it nests
inside the top level using st_contains)
• Thebottomlevelcanbea2Dor3Dpointora2Dor3Dlineora2Dorarea
or a 3D volume (provided it nests inside the middle level using st_contains) Not nesting the assets correctly will result in marks being lost for decisions as well
.
s – i.e. do not adapt existing text
and SQL – make sure you start completely from scratch.
  You MUST check the topic description before you select a topic, and make sure you understand the topic. If the remainder of your assignment does not match the topic
 you will not pass.
 There is no specific deadline for this task but you should make sure you lock in your
 topic BEFORE doing any other work on the assignment!
 You should not use a university or school example as this would be too similar to the
  example we covered in class and would be plagiarism
Your decisions should also not
 be similar to those used in the class or lab example
 1 You will also have other tables as part of your assignment – these can be spatial or non-spatial, and the spatial tables can be 2D or 3D
Page 3 of 15

Step 2 - Decisions (online form, link from Moodle)
List the Decisions (link to online form will be given in Moodle)
1. Write a description of the 7 decisions that your database will support
• The decisions need context and should include some information as to what information is needed but also WHY the information is needed, how it will be used by the decision maker - In other words, you need to be clear on what the information will actually be used for
– what is being decided.
• All decisions should be based on a numeric value
• Decisions should also include a realistic threshold value in the text
See Appendix and Step 4 for further information.
2. You should have two decisions that build on information provided by a lower level query (i.e. three decisions in total). You should make use of VIEWS to achieve this.
• Create a view for the decision corresponding to the bottom level of the pyramid, and for the decision query select from this view
• Create a view for the decision corresponding to the middle level of the pyramid that includes data from the view from the bottom level of the pyramid, and for the decision query select from this view
• Create a view for the decision corresponding to the top level of the pyramid, that includes data from the middle level view, and for the decision query select from this view
  Page 4 of 15

Step 3 – Pyramid (turnitin upload)
1. CreateaTHREELEVELpyramidforthisorganisation–similartotheexamplefrom the Centennial case study. This should include the names of the spatial asset/features that are at the bottom, middle and top levels of your pyramid
a. ThesenamesmustbeIDENTICALtothenameofthetablethatstoresdata for this feature.
b. All table names should be lower case
c. All three tables (assets) must match the tables you declared in the pre-
submission stage
d. All three features must be spatial – i.e. mappable (they can be 2D or 3D
depending on how they were originally declared)
e. The features must nest – i.e. features at the lowest level must be
contained inside features at the middle level, and features at the middle level contained inside features at the upper level.
Include a cover sheet in this PDF as Moodle requires a minimum of 35 words for plagiarism checks.
 Page 5 of 15

Step 4 - Database creation (5 script files, online form)
For this part of the assignment:
1. Script creation as follows:
a. Create an SQL script that contains the SQL used to create the tables in your
database system. Call this script: createtable_ucxxxxx.txt (where ucxxxxx is your UCL login). All table names should be lower case, use _ to separate out any words (not spaces or -)
• Make sure you use addGeometryColumn to add location columns – the SQL testing scripts will not work if this is not present
b. Create a separate SQL script for all the constraints. Call this script:
createconstraints_ucxxxxx.txt
c. CreateaseparateSQLscripttopopulateeachtablewithdata-callthisscript insertdata_ucxxxxx.txt:
• A minimum of 2 rows of data for the top level of the pyramid
• A minimum of 3 rows of data for the middle level (nested within the
top level data)
• A minimum of 9 rows of data for the bottom level (nested within the
3 rows of the middle level)
• A minimum of THREE rows of data for all other tables.
The data should be sufficient to allow you to test out the SQL for your listed decisions.
So that we can test your work independently, your SQL must create ALL the data required from scratch – don’t use any data that has been imported via QGIS / sourced from third parties. The spatial data you create does not need to be very sophisticated in terms of geometry complexity.
All data should use a projected coordinate system (i.e. not lat/lng2 – if you don’t know the projected coordinate system for your location use British National Grid)
d. Upload a script that creates a series of views that will help to simplify your queries – minimally, you should have 3 views, one for each level of the pyramid that aggregates from the lower levels. You should also have a latest_parameters view. Your file should only contain views – do not include the select statements to test the views. Call this createviews_ucxxxxx.txt
2 As lat/lng units are degrees/minutes/seconds when you try and measure a length or area you get very strange answers
   • Make sure you use the parameters approach following the in-class
 example.
  Page 6 of 15

e. Create a script file with the 7 SQL queries that provide data used to support the decisions you listed in the first part of the assignment. Call this decisions_ucxxxxx.txt
•
The result of each decision query should appear as a three-column table, with ONLY ONE ROW as follows.:
Threshold Value Result
As a very simple example of hard coding in SQL (note the single straight quotes)
select ′This is a decision′, ′22.3′, > from ucfscde.buildings;
select * from ucxxxxx.view_name
   Decision
      • The decision text is hard coded in your SQL, the threshold value is
  hard coded in the SQL, the result is a number calculated from the
 inserted data.
 • To meet the Step 2 (2) criteria, three of the seven statements should
 be just
2. Use the provided test system (link on Moodle) to upload and test your scripts. You will receive an e-mail report each time you run the test. Keep this as evidence that you have submitted your scripts.
Some CHECKS
• The SQL scripts should be manually created – i.e. typed by you
• You must use the provided PostGIS database
• The first line of the createtable script should drop cascade the ucxxxxx schema (if it
exists) and create it again
•
ucxxxxx.buildings and queries select from ucxxxxx.buildings
• Do not include views in the decision queries – use a separate views file
• Include comments in your scripts to make them easy to read – use -- to mark the
comments
o Any comments should be prefixed by -- (not /* */)
• Each element (create table, constraint, row insert, decision query etc) in the script should be separated by a ;
• Make sure that the filenames are correct.
• Any decision that requires the use of number values as part of the calculation –
distances, minimum or maximum sensor values, cost for painting, available budget and simila代 写program、SQL
代做程序编程语言r should use parameters.
All the SQL should work in your schema – e.g. your create table scripts should be similar
to: create table     .buildings (......), your insert scripts insert into
ucxxxxx
Page 7 of 15

Step 5 – Map and 3D visualisation (one PDF via Turnitin)
Upload a PDF to Moodle containing a QGIS screenshot showing the spatial data you create and a 3D screenshot created in FME. The screenshots should include the entire QGIS/FME windows (including menus and layer list) so that it clearly shows that the data is spatial and the map has been created from data in the database.
 Page 8 of 15

Marking Process
This assignment will be marked semi-automatically (nearly fully automatically), so it is very important that you follow instructions to the letter. Automated marking includes (but is not limited to):
• Running all the SQL scripts you upload and creating your database – this will NOT be done on the system we use in class, as we have a separate test database for the purpose so it is important to make sure your scripts run from beginning to end
o Don’t forget to drop cascade and create the schema in the createtable script
• Making sure you use the exact table names for the three assets that you declared in the initial form
• Checking that the geometry for the three levels of your pyramids actually does nest as expected
• Checking that all your tables have o Primary keys
o Unique constraints
• Checking that your data is valid – e.g. that you have the required rows of data
in all the tables, that primary/foreign key constraints are enforced, that geometry is correct and is nested as required
• The later parts of the assignment are dependent on the earlier parts – e.g. if your decision is not worded as required you will also lose marks for the related SQL.
  o Don’t forget to use your UCL login ucxxxxx as the schema name
 o Make sure that all your tables and views are created in the schema
Page 9 of 15

Marking Scheme
Marks will be awarded as follows:
 ** NB – if your assignment is too close to that covered in class we will reduce your
 overall mark. If your files don't work with the automated marking system you could
 score 0 marks **
  Component
    Maximum Mark out of 70
     Comment/Hint (in addition to information above)
   Learning Outcome
  Topic declaration (via online form)
  4
 You must make sure that the table names and geometry types and dimensions you provide here are those you use in the final SQL. 0 marks for this component if this is not the case.
Make sure you actually understand the topic before selecting it - check the provided website
 Be able to demonstrate how spatially-enabled relational databases can be used in practice - from identifying the decisions to be made, through designing the database, capturing the data and providing information for those decisions, in the context of real- world applications
  List of decisions (via online form)
    7
   Marks will be deducted if your decisions aren't worded correct – see Appendix.
If the decisions are not correctly phrased and/or are not relevant to the selected topic marks are also lost for the SQL
   Be able to demonstrate how spatially-enabled relational databases can be used in practice - from identifying the decisions to be made, through designing the database, capturing the data and providing information for those decisions, in the context of real- world applications
  Pyramid (upload to Moodle)
Map and 3D visualization (upload to Moodle)
   6
  Pyramid diagram must include all the components shown in the Centennial example (e.g. list of decisions, hierarchy of the assets).
QGIS screenshot must include the layer list clearly showing the colours for each layer (i.e. the entire QGIS screen, not just the map). The 2D map must show all three of your spatial features each nested within the other.
The 3D visualisation must show all three of your spatial layers - i.e. provide a screenshot of all of the FME screen
  Be able to demonstrate how spatially-enabled relational databases can be used in practice - from identifying the decisions to be made, through designing the database, capturing the data and providing information for those decisions, in the context of real- world applications
Understand the power of a relational database – and of location – to integrate data from disparate sources and manage and share that data centrally
  Page 10 of 15

     SQL – CREATE TABLE
0 if the script does not run as an
entire script OR you do not use 3 the correct schema, or if you
don’t DROP CASCADE and CREATE the schema first.
Understand how to model data and spatial data for storage in a relational database
  SQL – CONSTRAINTS
    3
   0 if the script does not run as an entire script OR you do not use the correct schema. This means that if your CREATE TABLE script has not worked, you could also get 0 for this component.
   Understand how to model data and spatial data for storage in a relational database
  SQL – INSERT DATA
  5
 0 if the script does not run as an entire script OR you do not use the correct schema. This means that if your CREATE TABLE or CONSTAINTS scripts have not worked, you could also get 0 for this component.
The data does not need to be complex – e.g. you can create simple boxes for the geometry.
You MUST have at least three tables that contain spatial data, matching the levels of your pyramid.
 Be able to write SQL to create and modify spatial data in a relational database
  4 Decision Queries
    16
   Maximum of 5 marks per decision query depending on complexity.
Queries that don’t work will be awarded 0 marks.
Queries where the answers don’t meet the required decision format will score 0 marks.
   Be able to write SQL to undertake spatial and non- spatial data analysis
  Advanced Decision Queries: 3 view-based decisions showing aggregation
  12
 Meeting the same criteria as the 4 decision queries above but corresponding to the three assets in the hierarchy and aggregating data at each level.
The SQL for decisions should be included in the decisions script but the query should take this form
select * from ucxxxxx.viewname;
i.e. the query in the decisions.txt file should be very
  Be able to write SQL to undertake spatial and non- spatial data analysis
 Page 11 of 15

    short and just query the corresponding view and nothing else – everything else should be included in the views, which should be created in the views script.
NB: the middle level view should reference the lower level view and the upper level view should reference the middle level view.
       Advanced Decision Queries: Using the Parameters Table
    14
       to select a value and then use this value in a
calculation (0 marks if the parameters table/view is not created and populated correctly or is not used). The SQL to make use of the parameter value can be part of the decision SQL or used within a view used by that decision. The resulting data should show how the parameters were used in the calculation, and what date the parameter value relates to.
During automated testing we will insert new random values into your parameters table for each of your parameters, with a future date, to make sure your queries do in fact use the latest values of the parameters. To gain marks here, the system will need to detect a change in the decision results when we do this.
You can test this out by running your parameter queries and noting the results, then inserting new values into the parameters table without deleting the old values – and making sure that your new results are different.
You are NOT required to change the threshold value in your
 Up to 2 additional marks for any
 Be able to write SQL to undertake spatial and non- spatial data analysis
  decision query that also makes
full use of the parameters table
and view
Page 12 of 15

         decision text. It is only the RESULT that will change.
    Page 13 of 15

Appendix 1 – Decisions – Some Examples
A decision should not just be 'list the total area of all the shops' or ‘which rooms should we paint next year’ (the 'what') – but should have some context – why do we need this information, what will the information be used to decide
Decisions must take this format:
We need to know the total cost/number of/description of of XXX so that, using this information, we can decide whether to do YYY or ZZZ.
You must also include this exact text in each decision text (substitute LLL, YYY, ZZZ with your own values, of course)
The threshold value for this decision is LLL. If the result is below LLL then we do YYY. If the result is LLL or above then we do ZZZ.
It is up to you to decide appropriate threshold values, based on your own topic and data.
Examples:
1. We need to make sure that there are enough security staff to cover the mall,
with a ratio of one security person per 100 sq m, so that if necessary we can decide whether to allocate budget to deploy more staff next year. The threshold value for this decision is 23 staff. If the result is below 23 staff we need to allocate more budget. If the result is 23 staff or above then we do not need to allocate more budget.
2. We need to find the largest shop so that we can decide if it is worth while speaking to the owner about splitting their space as we need to find a location to store glass for some glass repairs, or if we should leave the space as is and locate storage elsewhere. The threshold value for this decision is 100sq m. If the result is below 100sq m then we do not need to speak to the owner about splitting the space and will need to find additional storage space elsewhere. If the result is 100sq m or above, then we need to speak to the owner about splitting the space.
3. We need to find the maintenance times for our existing ovens so that we can compare that to the maintenance times of the new ovens we're planning to buy and decide which ovens are the best option for our budget – either Zanussi or Samsung. The threshold value for this decision is 20 minutes. If the existing maintenance time is less than 20 minutes we should buy Samsung ovens. If the existing maintenance time is 20 minutes or more we should buy Zanussi.
  Decisions should be binary – i.e. the decision maker should be making a decision
  between Option A and Option B.
Decision text should be clearly worded and detailed,
 in good English, so that anyone reading the text can understand exactly what is being
 decided and the context in which the decision is being made.
   Page 14 of 15

4. We need to find the total cost to refurbish the largest building in the university, so that we can see if it is within budget and decide whether to go ahead with the works in the next financial year or in the year after. The threshold value for this decision is £200,205. If the refurbishment cost is below £200,205 then we can go ahead with the works in the coming year. If the refurbishment cost is £200,205 or above then we cannot go ahead with the works in the coming year, but need to wait until the year after.
Page 15 of 15

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
