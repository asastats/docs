# ASA Stats Community Rewards Process

The following steps should be used to administer the ASA Stats Community rewards process each cycle using [Github](https://github.com/asastats) and the [ASA Stats Contribution Rewards spreadsheet](https://docs.google.com/spreadsheets/d/1UJ9ZyvV0fdcXAfpUNOsRa1aCmJko-QhF-BU4Wcu6Xog/edit#gid=238932857): 

a) From a web browser: 
* Navigate to the [Ongoing Contributions](https://docs.google.com/spreadsheets/d/1UJ9ZyvV0fdcXAfpUNOsRa1aCmJko-QhF-BU4Wcu6Xog/edit#gid=238932857) tab of the ASA Stats Contribution Rewards spreadsheet. 
* Enter a new "Period below" header by cutting/pasting an entry from the previous cycle, then adjust the date range and name of community member tabulating rewards.

b) From a 2nd web browser tab, navigate to the [ASA Stats Github Channel Issues page](
https://github.com/asastats/channel/issues) in Github:
* Use a filter to search for all closed issues w/ the "addressed" tag.
* Example syntax for a cycle with end date of April 29th: [is:issue is:closed closed:<2022-04-30 label:addressed](https://github.com/asastats/channel/issues?q=is%3Aissue+is%3Aclosed+closed%3A%3C2022-04-30+label%3Aaddressed) - where YYYY-MM-DD is one day afer cycle close.
* click on each issue to review details. Use the linkage in the description to determine the related recipient/s. Use the [Contributions Types and Levels chart](https://docs.google.com/spreadsheets/d/1UJ9ZyvV0fdcXAfpUNOsRa1aCmJko-QhF-BU4Wcu6Xog/edit#gid=1316088791) to determine the reward type and impact value to add to the spreadsheet.

c) Return to the spreadsheet tab from step a): 
* Enter in one line of data per reward recipient. 
* Fill in the appropriate field values in columns A through I for:
     * Person:
        * for Discord user, use syntax: name 
        * for Reddit user, use syntax: u/name
        * for Twitter handle, use syntax: @name  
     * Period begins/ends:
        * use syntax: YYYY-MM-DD for the beginning and end dates in columns B and C.
     * Platform:
        * specify the platform the community member submitted from: Discord, Twitter, Reddit or Github.
     * Channel:
        * add Discord or Gitchub channel (if applicable).
     * Contribution:
        * use the Reddit, Discord, Twitter or Github link to the details that describe the contribution.
     * Contribution Type:
        * select from the pick list of contribution types.
     * Impact level:
        * select impact level per the [Contributions Types and Levels chart](https://docs.google.com/spreadsheets/d/1UJ9ZyvV0fdcXAfpUNOsRa1aCmJko-QhF-BU4Wcu6Xog/edit#gid=1316088791).
     * % of reward to receive:
        * specify the percentage that the recipient should recieve.  By default, this is 100% if there is only one recipient.
* For columns I and J: drag formula down from previous rows to adjust formatting.

d) From the Github tab from step b): as each issue is added into the spreadsheet - remove the "addressed" label, and add the “archived” label.

e) From a 3rd web browser tab, navigate to the [ASA Stats static-pages Issues page](
https://github.com/asastats/static-pages/issues) in Github:
* Use a filter to search for all closed issues w/ the "addressed" tag.
* Example syntax for a cycle with end date of April 29th: [is:issue is:closed closed:<2022-04-30 label:addressed](https://github.com/asastats/static-pages/issues?q=is%3Aissue+is%3Aclosed+closed%3A%3C2022-04-30+label%3Aaddressed) - where YYYY-MM-DD is one day afer cycle close.
* Click on each issue to review details to understand if it was already counted in step b)
    * If an issue was already counted, remove the "addressed" label, and add the “archived” label.
    * If an issue was not already counted, complete remaining steps from b) and c) to enter and categorize, then remove the "addressed" label, and add the “archived” label.

f) From the spreadsheet tab: enter one additional entry w/ your own Reddit, Discord, or Twitter user as an \[AT2] or \[AT3] task to track time spent administering the rewards process for the cycle.

g) From the spreadsheet tab:  
* Navigate to the "Rewards by Period" tab, and locate the related period end date in column A
* If there is some adjustment to the rewards coefficient (currently 2x in this cycle), adjust the \*2 portion of the column D formula to the new multiplier.
* From column D, drag the formatting down from prior rows.
* Copy the list of column D rows into a text file
    * add a single-line comment at the top formatted like: \# NOTE ASA Stats Community rewards 3/26 - 4/29
    * add the total damo for the cycle to the bottom like: TOTAL 1.03 damo
Example list:
```
# NOTE ASA Stats Community rewards 3/26 - 4/29
@Emzeed01 0.02 damo
@fredestante 0.02 damo
@TylerOlthoff 0.06 damo
AlgoRhythMatic 0.06 damo
Babbexx22 0.04 damo
bear1bear2bear3 0.02 damo
Damo 0.04 damo
DragMZ 0.08 damo
iMpacToFTrees 0.02 damo
kerrilija 0.1 damo
Mikeyy 0.02 damo
moloch10 0.02 damo
motuwagon 0.02 damo
mynameis47 0.02 damo
Papa Noff 0.04 damo
petled 0.02 damo
Pill-Popper-OG 0.02 damo
pitofsuccess 0.02 damo
RandomTask 0.06 damo
Sammyspeed 0.08 damo
SCN9A 0.2 damo
u/Aromatic-Ad3922 0.02 damo
u/DellEnableUnderClock 0.01 damo
UncleDooom 0.02 damo
TOTAL 1.03 damo
```

h) From a 4th browser tab:
* Open a new [Github discussion](https://github.com/asastats/channel/discussions) w/ a descriptive title like: Discuss and review the rewards cycle from 3/26 - 4/29. 
* Add the list from step g) using \`\`\` to open/close formating w/ block quotes.
* Post links to the discussion in Reddit, Twitter, and Discord announcement channels.
* Moderate the discussion, and make adjustments to the spreadsheet as needed based on feedback.
* Allow up to 1 day for the community to have sufficient time to review, discuss and finalize all reward impact levels.
* Once all adjustments are confirmed, output the final list from step g) into a comment using the < > button to format, and notify the sender of the rewards (currently Ipaleka).
