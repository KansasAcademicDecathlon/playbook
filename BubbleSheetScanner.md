# Bubble Sheet Scanner

Note: Sorting is not necessary for scanning the bubble sheets. Delaying sorting allows for scanning to start sooner. Sorting can occur while scanning other tests.

## Scanner Setup

1. Connect the AC adapter to the scanner and plug it into a power outlet.
1. Connect the USB cable to the back of the scanner and the computer.

## Scanning procedure

1. Start the DataLink software.
Run the scanning software as administrator as the USAD exporting plugin writes to `C:\Program Files\USADEvents\Database`.
1. Select the `Scanner Results` menu and select `Data Collection`. Title bar should say `Data Collection Mode`. Scanner should say `Data Collection Mode`.
1. Scan tests
   * Notice that the number after the Student ID is the Test ID.
   * Verify the Test ID is correct after scanning each test; a second person can monitor the computer while someone else feeds tests.
   * Correct IDs in the scanning software by right-clicking the ID field and selecting `Change ID Number`; there is a space between the Student ID and the Test ID. Note the scanning software (as of version 3.5.4.208) does not allow editing the first row for unknown reasons.
   * Different ID formats
     * Speech\Interview `1004     1`
     * Objective `1201 06`
1. File -> Save a copy along with the other files for the competition (e.g., `KAD\2022-2023\2022 Regionals\Scanner Output\02Music.APx3`). Saving the copy in the native format of the scanning software allows easy appending or modification.
1. Click the AD button to export
1. Make a note of the total tests scanned. Use this number to determine if tests are missing or if a decathlete did not take a test (e.g. late arrival).

After scanning a test, always close and reopen the scanner software. Otherwise, the scanner may use the wrong form (switching from Interview to objective).

## Scanning Tips

If `PAPER SKEW......` occurs multiple times, try placing your nails against the bottom of the sheet while feeding.

`Multiple Marks Question ##` - use correction tape to cover all the marks if there are umambigiously multiple marks.
If the message is due to an clear erasure, then use correction take to cover the erasure.

`All Ratings Must be Completed` - Check that all bubbles are completely filled in.

## Exporting to Scoring Software

The [procedure above](#scanning-procedure) saved each event as an individual file.
The scoring software expects all the objective tests in a single file for importing.

Note: the scanner does not need to be connected for the following procedure.

1. Export Speech
   1. Start the DataLink software as administrator.
   1. From the `File` menu, select `Load Saved Data`.
   1. Select the saved speech file.
   1. Click the AD button in the toolbar.
   1. A Finished dialogue appears stating `Your USAD speech results have been saved.` Click `OK`.
   1. Copy the `C:\Program Files\USADEvents\Database\Speech.txt` file to the location for the other files for the competition (e.g., `KAD\2022-2023\2022 Regionals\Scoring Software`).
1. Export Interview
   1. Same steps as speech, but use the interview saved file.
   1. Copy the `C:\Program Files\USADEvents\Database\Intrview.txt` file with the `Speech.txt` file.
1. Export Essay
   1. Same steps as speech, but use the essay saved file.
   1. Copy the `C:\Program Files\USADEvents\Database\Intrview.txt` file with the `Essay.txt` file.
1. Export Objevtive
   1. Start the DataLink software as administrator.
   1. From the `File` menu, select `Combine Tests`.
   1. Click `Add Test`.
   1. Select all the objective tests. Select multiple files my holding down the `CTRL` key while clicking on each one.
   1. Click `Open`.
   1. Click `Load in Scanner Results Grid`.
   1. Click the AD button in the toolbar.
   1. Copy the `C:\Program Files\USADEvents\Database\Objectiv.txt` file with the `Speech.txt` file.

Now [import those results](ScoringSoftware.md#importing-results) into the scoring software.
