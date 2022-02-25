# Master Task List

- [ ] Sign USAD Charter
- [ ] [Contact USAD to confirm access to online testing](#requesting-access-to-online-testing)
- [ ] Create [registration form](Registration.md)
- [ ] Set Registration Deadline
- [ ] Order [plaques](Awards.md#plaques)
- [ ] Order ribbons
- [ ] Import participating schools into USAD online testing system
- [ ] Registration reminder email
- [ ] Import registered students into USAD online testing system
- [ ] Edit test instructions from USAD to include state director contact information
- [ ] Send out test instructions with activation keys to coaches
- [ ] [Download Objective Answers & Keys](#download-objective-answers-and-keys)
- [ ] [Download Essays](#download-essays)
- [ ] [Score Essays](#scoring-essays)
- [ ] [Set up a contest in the scoring software](ScoringSoftware.md#setting-up-a-contest)
- [ ] [Generate and send out reports](ScoringSoftware.md#generating-reports)
- [ ] Send checks to Bruce
- [ ] Missing payment follow up
- [ ] Send out awards
- [ ] Reimbursement Request for shipping

## State only

- [ ] Conduct & Release forms
- [ ] Board Meeting Agenda
- [ ] Coaches Meeting Agenda
- [ ] Fill out Nationals Intent to Participate & State Competition Results Form
- [ ] Send out [scholarships](Scholarships.md)

## USAD Online Testing

### Requesting access to online testing

Contact the current USAD Testing Director.
See <https://usad.org/About/Contact-Us.aspx> for contact information.
Ask to set up Kansas object tests and essays online
for the day of the competition.
Ask for a practice round the week before the competition.
Determine if the students are testing together in a room with a proctor or
testing independently and remotely.
If students are not testing with a proctor,
the Testing Director replaces the listening questions with non-listening questions.

A few weeks before the competition, USAD will email Word documents with instructions.
The instructions contain activation keys for the objective tests and the essay.

### School Information File

See <https://usad.enlyght.com/School%20Import%20File%20Example.csv> for an example.
Some schools use a district-wide domain for email (e.g., smsd.org).
For those districts, create a subdomain using the school name (e.g., @north.smsd.org).

When creating CSV file using Excel, do not save as `CSV UTF8 (Comma delimitated) (*.csv)`.
Use `CSV (Comma delimitated) (*.csv)` instead.

The website importer errors out if a school already exists.
Remove the existing schools from the CSV to import.

### Student Team Information File

See <https://usad.enlyght.com/Student%20Import%20File%20Example.csv> for an example.
When creating the CSV file using Excel, save it as `CSV (Comma delimitated) (*.csv)`.
After importing the Student Team Information File, the scoring website will immediately display the [School Access Information](#school-access-information).
The website importer errors out if a student already exists.
Remove those students from the CSV to import.
Passwords should not change after importing more students.

### School Access Information

Print to PDF the list of usernames and passwords shown after importing the Student Team Information File.
Click *Export Usernames and Passwords* to download CSV file with the information displayed on the page.

Compose an email to each coach with their respective list of names, usernames, and passwords.
Edit the Essay, Practice Test Online, and Object instructions to add your name and phone number where highlighted.
Attach the *KS-Regional Essay Instructions.docx*, *KS-Practice Test Online Instructions.docx*, and *KS-Regional Objective Instructions.docx* to the email.
Suggest to the coaches they arrange a time to practice with their students the week of the competition.

### Download Objective Answers and Keys

- From the USAD Testing website, click on *Test Export SS*.
- Enter the activation key from the *Objective Test Online Instructions* Word document for USAD.
- From the popup windows, click *Export Answer Key* and *Export Student Answers*.

These files are imported into the scoring software.

### Download Essays

- From the USAD Testing website, click on *Essay Menu*.
- Enter the activation key from the *Online Essay Instructions* Word document from USAD.
- Click on *Essay List*.
- Click the *Print All Essays* button.
- The downloaded text file contains all the essays.
- Open the text file in Word.
- Insert page breaks between each essay.
- Add page numbers in the header and footer.
The page number ensures multi-page essays stay together.
- Print the essays single sided for grading.

### Scoring Essays

The essay judges can use the official USAD Essay Evaluation form and the results collected via the Apperson scanner software.

The other option is to manually record scores on a sheet of paper and transcribe them into the format expected by the Scoring Software.

```CSV
E,StudentID,filler,Judge Number,Score1,Score2,filler,filler
```

Example

```CSV
E,0101,,2,55,79,0,0
E,1402,,2,83,45,0,0
E,0409,,1,77,82,0,0
```

Ensure that each score has a unique StudentID and Judge Number combination.
It is easy to reuse the same Judge Number for two different scores.
Remember that some IDs have leading zeros.
