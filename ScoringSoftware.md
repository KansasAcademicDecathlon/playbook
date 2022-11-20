# USAD Scoring Software

## Preparing Import Files

*TeamsImportData.csv* contains information about each team's school.
See <https://scoring.usad.org/Setup/ImportTeamExample> for more details.

*CoachImport.csv* contains contact information for each coach.
See <https://scoring.usad.org/Setup/ImportCoachExample> for more details.
**Note:** The website field must contain something but is not validated (e.g. "www" is fine).

*StudentRooms.csv* contains information for each student. See <https://scoring.usad.org/Setup/ImportStudentExample> for more details.
**Note:** Speech Room, Speech Time, Interview Room,Interview Time, Testing Room, Test Seat,
Essay Room can be the same for every student. Those fields need to be unique if using the PC scoring software for generating schedules.

## Answer Key Transformation

USAD provides the answers to the objective tests in a Word document.

1. Create a new `AnswerKey.csv` file for this contest. Note that the `Essay` line is used in the state competition.

   `Art,4,50,20,1000,`
   \
   `Music,2,50,20,1000,`
   \
   `Mathematics,5,35,28.57,1000,`
   \
   `Economics,6,50,20,1000,`
   \
   `Literature,1,50,20,1000,`
   \
   `Science,11,50,20,1000,`
   \
   `Social Science,3,50,20,1000,`
   \
   `Essay,7,2,1000,1000,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,`
   \
   `Speech,8,11,1000,1000,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,`
   \
   `Interview,9,10,1000,1000,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,`

1. Open the answer key Word document.
1. Open a blank [Notepad++](https://notepad-plus-plus.org/) document.
1. For each test
   1. In Word, select the two columns containing the answers, including the Roman numerals and numbers. Copy the selection to the clipboard.
   1. Switch to Notepad++ and paste the text.
   1. Delete blank lines at question 25 (if present).
   1. From the *Search* menu, select *Replace*. The Replace dialoge appears.
   1. In the *Find what:* field paste `[0-9]{1,2}.[ \t]*([A-E]).*(?:\R|\z)`
   1. In the *Replace with:` field paste `$1,`
   1. Under *Search Mode*, select the *Regular Expression* radio button.
   1. Click the *Replace All* button.
   1. Delete the last comma.
   1. Paste the resulting line into the matching line of the `AnswerKey.csv` file.


## Setting up a contest

1. Go to the [Scoring Website](https://scoring.usad.org/) and Log in (link in the upper right).
1. Click on the competition name (e.g. 2021 State Competition) to go to the *Select Contest* page.
1. Click the *Create New Contest* button.
1. Name the contest and click *Create Contest*.
Upon completion, the page automatically goes back to the *Select Contest* page.
1. From the *Contests* list, select the newly created contest and click *Change Contest*.
1. From the *Contest Maintenance* page, fill out *Organization Name* and *Theme*.
Leave all other fields with their default values.
1. Click the *Update* button.
1. Open the USAD Scoring Software on the PC.
1. At the *Login* window, do not enter credentials yet. Click the *Download event data* button.
1. From the File Download window, enter credentials and click *Refresh Contest List from Online* button.
1. From the *Contest to Download for:* list, select the newly created contest.
1. Under the *Select Data to Download:* list of options, check *Credentials* and *Contest*.
1. Click *Import from Cloud*. If there is an error, check that the contest is updated online.
1. Click *Close*.
1. At the *Login* window, enter credentials and click *Submit*.
1. At the *Select the Contest* window, select the recently created contest and click *Submit*.
1. From the *Setup* menu, select *Import*.
1. From the *Import Changes* screen, check the *Teams* box.
1. Click the *Browse* button, select the *TeamsImportData.csv* file from the computer, and click the *Upload* button.
If the upload encounters an error, make sure the file is not open in Excel.
1. Check the *Coach* box and repeat the above step with the *CoachImport.csv* file.
1. Check the *Student* box and repeat with the *StudentRooms.csv* file.
If there is an error uploading a certain student, ensure the student has valid rooms and times.
Attempt the upload again after making corrections.
The software allows for uploading the file multiple times without creating duplicates.
1. Check the *Test* box and repeat with the *answerkeyonline.txt* file [downloaded from the USAD Testing website](./OnlineTesting.md#download-objective-answers-and-keys).
1. Close the *Import Changes* window by clicking on the icon next to the *File* menu and clicking *Close*.
1. From the *Setup menu*, select *Test*.
1. The Essay test is missing because it was not part of the *answerkeyonline.txt* file. Click *Add New* to add the test.
   * Name: Essay
   * Number: 7
   * Test Type: Essay
   * Scanner: Apperson
   * Abbreviation: Essay
   * Total Questions: 2
   * Total Points: 1000
   * Points Per Question: 1000
   * Multiplier: 1.0
1. Close the *Test Page* window by clicking on the icon next to the *File* menu and clicking *Close*.

## Importing Results

1. Open the USAD Scoring Software on the PC and login. Verify the title of the window is the current contest.
1. From the *Setup* menu, select *Import*.
1. From the *Import Changes* screen, check the *Objective Answers* box.
1. Click the *Browse* button, select the *objectiv.txt*, either [downloaded from the USAD Testing website](./OnlineTesting.md#download-objective-answers-and-keys) or [exported from the scanning software](BubbleSheetScanner.md#exporting-to-scoring-software), and click the *Upload* button.
If the scoring software reports a missing student, the student ID is probably incorrect on the bubble sheet.
Go back to the scanner software and look for incorrect student IDs in the combined data.
Sort by `ID` to quickly find IDs missing tests.
Fixing the ID in the scanner file (versus the combined file) for that test is recommended.
Then export the combined data again.
1. Check the *Speech Answers* box and repeat with the *Speech.txt* file.
1. Check the *Interview Answers* box and repeat with the *Interview.txt* file.
1. Check the *Essay Answers* box and repeat with the *Essay.txt* file. See [Scoring Online Essays](./OnlineTesting.md#scoring-essays) for details.

## Generating Reports

**Note:** All exported files are located in `<USAD Scoring Software Directory>\ReportsExport\Kansas`, with subfolders for each team.

1. Open the USAD Scoring Software on the PC and login. Verify the current contest is listed as the title of the window.
1. From the *Scoring* menu, select *Scores Maintenance*.
1. Click the *Find Divergence* button. This must be performed if any essay scores are changed.
1. Close the *Missing/Divergent Scores* window by clicking on the icon next to the *File* menu and clicking *Close*.
1. From the *Reports* menu, select *Post-Competition*.
1. From the *Team Reports* section, select *Overall Team Scores*, and click *Export By Team*.
1. From the *Individual Ranking* section, select *Top Scorers for Decathlon*, and click *Export Individual*.
1. From the *Individual Ranking* section, select *Top Scorers By Event*, and click *Export By Individual*.
1. From the *Team Comprehensive* section, select *Comprehensive Final Team Report*, and click *Export by Team*.

Review each *Comprehensive Final Team Report* for discrepancies before sending out to coaches.
