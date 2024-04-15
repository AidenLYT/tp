---
  layout: default.md
  title: "User Guide"
  pageNav: 3
---

# LookMeUp User Guide

Greetings! Students from the Halls of NUS, are you tired of the hassle of managing your contacts? 

Welcome to LookMeUp, your one-stop desktop app that revolutionizes contacts management for NUS students like YOU, with 
multiple commitments and multiple groups of friends to keep track of! 
Liking the speed and effectiveness of Command Line Interface (CLI) or visual simplicity of Graphical User 
Interface (GUI)? LookMeUp caters to your needs, it ensures that managing your contacts is quicker and more efficient 
than ever before.

So say goodbye to traditional address book applications and say hello to the future of contact management with LookMeUp!

<!-- * Table of Contents -->
<page-nav-print />

--------------------------------------------------------------------------------------------------------------------

## Quick start

1. Ensure you have Java `11` or above installed in your Computer.

1. Download the latest `LookMeUp.jar` from [here](https://github.com/AY2324S2-CS2103T-T12-2/tp/releases).

1. Copy the file to the folder you want to use as the _home folder_ for the LookMeUp app.

1. Open a command terminal, `cd` into the folder you put the jar file in, and use the `java -jar LookMeUp.jar` command 
   to run the application.<br>
   A GUI similar to the below should appear in a few seconds. Note how the app contains some sample data.<br>
    <p align = "center">
        <img src="images/Ui.png" width="50%"/>
    </p>   

1. Type the command in the command box and press Enter to execute it. e.g. typing **`help`** and pressing Enter will 
   open the help window.<br>

1. For users who are familiar with our app, or simply wish to get a quick reference to our commands, feel free to refer
   to the [Command Summary](#command-summary) below! Else, you can refer to the [Features](#features) section for a
   detailed explanation of each command.

<box type="tip" seamless>

**TIP:**
* If you’re unfamiliar with  using the command terminal, fret not! [Here](https://www.git-tower.com/blog/command-line-cheat-sheet/) is a condensed cheat sheet for your reference. 

</box>


--------------------------------------------------------------------------------------------------------------------

## Features


<box type="info" seamless>

**Syntax of Commands:**<br>

* Words in `UPPER_CASE` are the parameters to be supplied by the user.<br>
  e.g. in `add n/NAME`, `NAME` is a parameter which can be used as `add n/John Doe`.

* Items in square brackets are optional.<br>
  e.g `n/NAME [t/TAG]` can be used as `n/John Doe t/friend` or as `n/John Doe`.

* Items with `…`​ after them can be used multiple times including zero times.<br>
  e.g. `[t/TAG]…​` can be used as ` ` (i.e. 0 times), `t/friend`, `t/friend t/family` etc.

* Parameters can be in any order.<br>
  e.g. if the command specifies `n/NAME p/PHONE_NUMBER`, `p/PHONE_NUMBER n/NAME` is also acceptable.

* Extraneous parameters for commands that do not take in parameters (such as `addbystep`, `help`, `list`, `exit` and `clear`) will be ignored.<br>
  e.g. if the command specifies `help 123`, it will be interpreted as `help`.

* If you are using a PDF version of this document, be careful when copying and pasting commands that span multiple lines as space characters surrounding line-breaks may be omitted when copied over to the application.
</box>

<box type="tip" seamless>

**TIP:** 
* LookMeUp supports **fuzzy commands** with a maximum allowance of 1 misspelled letter,
    preventing users from needing to retype the entire command due to a single spelling mistake.
     * Examples:
       * `swot` will be interpreted as `sort`
    * `addystep` will be interpreted as `addbystep`
 * LookMeUp text field supports **command history** accessibility.
       * You can make use of your `Up` and `Down` arrow keys to navigate through the commands that you have previously entered.
</box>

<box type="warning" seamless>
  
**WARNING:**
 * Command prefixes (n/…​ a/…​ p/…​ e/…​ t/…​) only accepts lower case characters.
   * Examples like N/…​ A/…​ P/…​ E/…​ T/…​ where prefixes are capital letters will not be accepted.
</box>


### Viewing Help : `help`

<p align = "center">
    <img src="images/Ui-help.png" width="50%"/>
</p>

Shows a message explaining how to access the help page.

<p align = "center"> 
    <img src="images/helpMessage.png" width="50%"/>
</p>

Format: `help`

### Adding a Person (Full Command): `add`

Adds a person to the address book.

Format: `add n/NAME p/PHONE_NUMBER e/EMAIL a/ADDRESS [t/TAG]…​`

Examples:
* `add n/Taylor Sheesh p/98765432 e/taytay@taylor.com a/Rhode Island`
* `add n/Ariana Grenade t/friend e/Arianator@ari.com a/Washington D.C. p/88883333 t/EternalSunshine`

<box type="tip" seamless>
  
**Tip:**
* Suffix need not be in order.
* A person can have any number of tags **(including 0)**.
* There are no character limit restrictions for each input. 
* However, it is advisable to keep each field under **100 characters** to ensure compatibility with your device's resolution.
</box>

<box type="important" seamless>

**Important:**
* Phone numbers should only contain numbers **(min 3 numbers)**.
* LookMeUp only supports **alphanumeric characters** for name, email and tag inputs
   * (with email accepting a single `@`).
</box>

<box type="info" seamless>

**Note:**

**Why are there alphanumeric restrictions on the Email and Tag inputs, and how does it help YOU?**

All NUS student emails are restricted to alphanumeric characters as with both the default NUSNET email
and the FriendlyMail guidelines. This restriction ensures additional safety that the email entered is an NUS student
email, catching any accidental typos of non-alphanumeric characters.

Similarly, tags (in the context of classifying by interest groups, committees etc.) are
expected to be alphanumeric, thus serves as another safety net.
</box>

<box type="warning" seamless>

**Warning:**
* Do be careful when you are adding a new contact, as extra spacing could lead to a similar or identical name
being recognized as a new, unique name. e.g. John Doe is not the same as JohnDoe
* Similarly, names are also case-sensitive, so do be careful when entering your contact's name as well. 
e.g. John Doe is treated differently from John doe
</box>

### Adding a Person (With System Prompts): `addbystep`

<p align = "center">
    <img src="images/AddByStep.png" width="40%"/>
</p>

To streamline the process of adding contacts, `addbystep` command offers user-friendly interface that prompts you for each required field
in the address book entry.<br/>

While this simplifies the data entry process, you will still need to manually copy `cp` and paste the final result into the command box.

Format: `addbystep`

<box type="info" seamless>

**Note:**

* Currently, `addbystep` does not support the filling of tags when adding a new contact.
* Once you have added all the details, you have to close the window and paste the result in the command box to create an `add` command.
* Since this is an accessory window, **maximising of the window is not supported**.
* `addbystep` only helps you to format the command correctly, it does not help to check if the person that you are 
adding is a duplicate. You have to copy the command to your clipboard and paste it into LookMeUp to verify if the 
person is non-duplicate.
* If you enter an invalid input for one of the fields (e.g. you left the name blank), an error message will be 
displayed, and you will have to enter the same field again.
</box>


### Listing all Persons : `list`

Shows a list of all persons in the address book.

Format: `list`

### Editing a Person : `edit`

Edits an existing person in the address book.

Format: `edit INDEX [n/NAME] [p/PHONE] [e/EMAIL] [a/ADDRESS] [t/TAG]…​`

* Edits the person at the specified `INDEX`. The index refers to the index number shown in the displayed person list. The index **must be a positive number** 1, 2, 3, …​
* The index provided must be within the range of available contacts in the address book.
* At least one of the optional fields must be provided.
* Existing values will be updated to the input values.
* When editing tags, the existing tags of the person will be removed i.e adding of tags is not cumulative.
* You can remove all the person’s tags by typing `t/` without
    specifying any tags after it.

Examples:
*  `edit 1 p/83838383 e/Arianana@nana.com` Edits the phone number and email address of the 1st person to be `83838383` and `Arianana@nana.com` respectively.
*  `edit 2 n/Billie Eyelashes t/` Edits the name of the 2nd person to be `Billie Eyelashes` and clears all existing tags.

<box type="info" seamless>
  
**Note:**
 
Editing a contact with the same value will still be considered a successful edit, and LookMeUp will prompt a "successful" message.
 
LookMeUp will display the entire contact fields in the "successful" message (shown below).
 
<img src="images/successEdit.png" width="100%"/>
</box>


### Locating Persons by Name: `find`

Finds persons whose names contain any of the given keywords.

Format: `find KEYWORD [MORE_KEYWORDS]`

* The search is case-insensitive. e.g `ariana` will match `Ariana`
* The order of the keywords does not matter. e.g. `Ariana Eyelash` will match `Eyelash Ariana`
* Only the name is searched.
* Only full words will be matched e.g. `Aria` will not match `Ariana`
* Persons matching at least one keyword will be returned (i.e. `OR` search).
  e.g. `Ariana Sheesh` will return `Ariana Grenade`, `Taylor Sheesh`

Examples:
* `find Taylor` returns `Taylor Sheesh` and `Taylor Laundry`
* `find Billie Sheesh` returns `Billie Eyelash`, `Taylor Sheesh`<br>
<p align = "center">
    <img src="images/findBillieSheesh.png" width="50%"/> <br>
</p>

### Removing a Person (Safe Removal): `remove`

Removes a person based on index, and confirms removal of the spotlighted contact before actual removal.

Format in 2 steps:

1. `remove INDEX`<br>
   example: `remove 3`<br>
    <p align = "center">
        <img src="images/index-remove.png" width="50%"/><br>
    </p>

   * Removes the contact from the specified index.
   * The `INDEX` refers to the index number shown in the displayed person list.
   * The index must be a `positive number` 1, 2, 3, … and can only be as large as the index of the last contact in 
   the current list (be it the default or filtered).
     * LookMeUp then "spotlights" (only shows) this one contact, and prompts a confirmation message to confirm removal<br>
        <p align = "center">
            <img src="images/confirmation.png" width="50%"/><br>
        </p>
    <box type="info" seamless>
     
      **Note:**
      
     If you'd like to remove a different contact, e.g. at index 2 of the original list, you **cannot** enter
   `remove 2` since the current list is shortlisted to only the single contact at the original index 3 to prepare for safe removal. 
   You should abort the removal process directly with a `no` confirmation first, then proceed with `remove 2` to remove.
    </box>
2. Confirmation: `yes/no`<br>
   1. If `yes`:<br>
      
      Expected result: <br>
      <p align = "center">
         <img src="images/yes-result.png" width="50%"/><br> 
      </p>
   2. If `no`:<br>
   
      Expected result: <br>
      <p align = "center">
         <img src="images/no-result.png" width="50%"/><br>
      </p>
<box type="important" seamless>

  **Important:** 

 **How to deal with wrong/unknown command(s) entered in between the workflow of `remove INDEX` and `yes`/`no` 
 confirmation?**
 
<box type="info" seamless> 
 
  **NOTE:**
  LookMeUp will **NOT** return to the default list upon this invalid command entry, due to uncertainty of whether
    user wishes to continue with removal process or change to perform another command!

_Some common scenarios:_ <br>
 1. **If it was a mere mistake, and you still wish to continue on with the contact removal process:**<br>
   simply enter `remove 1` again, it serves as a __safety check__ telling LookMeUp that you ***still*** wish to remove 
 the current shortlisted contact, and then proceed with `yes` / `no` confirmation
 2. **If you wish to stop the removal process and return to the default list:**<br>
   simply enter `list` to return to the default list, and then proceed with your next desired command
</box>
</box>

<box type="tip" seamless>
  
**Tip:** 
 
 **What if you wish to execute a _different command_ after the `remove INDEX`, before `yes` / `no` confirmation?**

 You may enter another **VALID** command in between the `remove INDEX` and the `yes` / `no` confirmation 
 (e.g. after `remove 2`, you can enter `add n/John p/98765432 e/j@gmail.com a/677405`)
 then the `add` command will be executed, while the removal will be aborted.

 However, it is **ADVISED** to abort the removal process directly with a `no` confirmation first, as that 
 would return you the full default list of contacts, where you may then proceed with your desired command(s).
</box>

<box type="tip" seamless>
  
**Tip:**

 **How to potentially _SPEED UP_ the contact removal process, especially when LookMeUp gets populated with MANY 
 contacts?**
 
 Make use of the contact filtering feature of `find` and use it together with the `remove` commands! 
 
 For example: `find rachel` (which shortlists all contact(s) matching "rachel") followed by `remove 1` will prompt a 
 confirmation message to confirm the removal of the 1st contact in the filtered results of the `find` command. 
 
 This is especially useful if you wish to remove a contact without having to scroll for its index, or if you have
 multiple contacts with the same part(s) of a name and wish to shortlist e.g. all "rachel"s first before deciding which
 to remove by the index of the filtered list. 
</box>

### Undo Previous Command : `undo`

For any command that changes the universal list of contacts _e.g. `add`, `remove`, `clear`, `overwrite`, `duplicate` 
and `edit`_, the `undo` command will revert the state of the contact list prior to the execution of a command.<br>

Format: `undo`
For example, referring to the previous command, assuming you have removed a contact, you can type `undo` to recover the 
removed contact:<br>
<p align = "center">
    <img src="images/undo.png" width="50%"/><br>
</p>

The removed contact will then be restored, **even to its original index**.<br>
<p align = "center">
    <img src="images/recovered.png" width="50%"/><br>
</p>

Similarly, `undoing` after adding a contact would mean reverting the contact list's state back to before the contact 
was added.

<box type="important" seamless>
  
**Important:**
 Once you closed the application, all your changes will be saved and all your past command history will be **erased**.
   * That is, when you launch the app again, you will not be able to undo any commands from the previous time you launched it.
</box>

###  Redo Undid Command : `redo`

Redo the most recent `undo` command.

Format: `redo`

For example, entering `redo` after previous `undo` example will revert the contacts to before `undo` was being executed.

<box type="important" seamless>
  
**Important:**
 `redo` only works when `undo` was called.
 If there were no commands undone, entering `redo` will prompt an **error**.
</box>

### Copies a Person Information to Clipboard : `copy`

Copies a person’s information such as name, phone number, address and email into your OS clipboard. 
This feature allows you to copy **more than one** piece of a contact’s information, and allows you to specify the order of a person’s information to be copied. 
If multiple fields are provided, results are separated by a single whitespace.

<box type="info" seamless>

**Note:**
 Duplicated fields that are specified are safely process and copied 
 * Refer to the table below
</box>

Format: `copy INDEX FIELD(s)`

Example:<br>
<p align = "center">
    <img src="images/example.png" width="50%"/><br>
</p>

Based on the sample contact above:

| Sample Commands       | Details                                                                    | Results                      |
|-----------------------|----------------------------------------------------------------------------|------------------------------|
| `copy 4 name`         | Copies the name of contact indexed 4                                       | `Taylor Sheesh`              |
| `copy 4 name address` | Copies the name and address of contact indexed 4                           | `Taylor Sheesh Rhode Island` |
| `copy 4 phone email`  | Copies the phone and email of contact indexed 4                            | `98765432 taytay@taylor.com` |
| `copy 4 email email`  | Copies the email of contact indexed 4  **(Duplicated fields are ignored)** | `taytay@taylor.com`          |
| `copy 4 nnamee phone` | Incorrect field detected                                                   | `N.A.`                       |

### Sorting the Contacts : `sort`

Sorts the entries in the address book based on the given condition.

Format: `sort KEYWORD`

* LookMeUp supports the following `KEYWORDs` : `name`, `tag`
    * `Name`: Sorts the entries based on lexicographical order of names.
    * `Tag`: Sorts the entries based on lexicographical order of tags.

<box type="info" seamless>

**Note:**
 When `sort tag` is executed, LookMeUp sorts tags by 
**numbering**, followed by contacts **without tags**, and finally **alphabetically**
 
<img src="images/savetag.png" height="380"/><br>
</box>

### Filtering by Tag : `filter`

Shows a list of persons in the address book, filtered by `specified tag(s)`.

Format: `filter TAGNAME`

Example: `filter 13`
<p align = "center">
    <img src="images/filtered.png" height="260" width="238"/><br>
</p>

### Adding a Contact with Duplicate Identity : `duplicate`

Adds the new contact to the address book, **assuming that a contact with an identical name already exists**.

Format: `duplicate n/NAME p/PHONE_NUMBER e/EMAIL a/ADDRESS [t/TAG]…​`

Example:
Say you have a list of contacts like the following, and you wish to add a contact with an **identical name** to the first entry `Taylor Sheesh`<br>
<p align = "center">
    <img src="images/Ui.png" width="50%"/><br>
</p>

You will encounter the following error using the `add` command<br>
<p align = "center">
    <img src="images/error.png" width="50%"/><br>
</p>

To duplicate the contact, run the following `duplicate` command and enter to see the results.<br>
<p align = "center">
    <img src="images/duplicate-command.png" width="50%"/><br>
</p>
<p align = "center">
    <img src="images/duplicate-success.png" width="50%"/><br>
</p>

### Overwriting an Existing Contact : `overwrite`

Overwrites an existing contact in the address book, provided that a contact with an identical identity already exists in the address book.

Format: `overwrite INDEX n/NAME p/PHONE_NUMBER e/EMAIL a/ADDRESS [t/TAG]…​`
* `INDEX` refers to the index number shown in the displayed person list, that represents the target contact to be overwrite.
* The index **must be positive number** 1, 2, 3, …​
* The index provided must be within the range of available contacts in the address book.


Example:
Say you tried to add a contact with an **identical name** to the first entry `Taylor Sheesh`<br>
<p align = "center">
    <img src="images/Ui.png" width="50%"/><br>
</p>

You will encounter the following error using the `add` command<br>
<p align = "center">
    <img src="images/error.png" width="50%"/><br>
</p>

In the case where you actually intended to overwrite the contact instead, run the following `overwrite` command and enter to see the results.<br>
<p align = "center">
    <img src="images/overwrite-example.png" width="50%"/><br>
</p>
<p align = "center">
    <img src="images/overwrite-success.png" width="50%"/><br>
</p>

### Clearing all Entries : `clear`

Clears all entries from the address book.

Format: `clear`

### Exiting the Program : `exit`

A pop-up would be shown that prompts you for **confirmation** to exit the address book.

<box type="info" seamless>

**Note:**

Windows users, you may press ENTER/SPACE to confirm your choice.
 
MacOS users, please press only SPACE to confirm your choice.
 
For more info, kindly refer to [here](https://openjfx.io/javadoc/11/javafx.controls/javafx/scene/control/Button.html).
</box>

Format: `exit`

### Saving the Data

AddressBook data are saved in the hard disk automatically after any command that changes the data. There is no need to save manually.

### Editing the Data File

AddressBook data are saved automatically as a JSON file `[JAR file location]/data/addressbook.json`. Advanced users are welcome to update data directly by editing that data file.

<box type="warning" seamless>

**Caution:**
If your changes to the data file makes its format invalid, AddressBook will discard all data and start with an empty data file at the next run.  Hence, it is recommended to take a backup of the file before editing it.<br>
Furthermore, certain edits can cause the AddressBook to behave in unexpected ways (e.g., if a value entered is outside the acceptable range). Therefore, edit the data file only if you are confident that you can update it correctly.
</box>


--------------------------------------------------------------------------------------------------------------------

## FAQ

**Q**: How do I transfer my data to another Computer?<br>
**A**: Install the app in the other computer and overwrite the empty data file it creates with the file that contains the data of your previous AddressBook home folder.

--------------------------------------------------------------------------------------------------------------------

## Known Issues

1. **When using multiple screens**, if you move the application to a secondary screen, and later switch to using only the primary screen, the GUI will open off-screen. The remedy is to delete the `preferences.json` file created by the application before running the application again.

--------------------------------------------------------------------------------------------------------------------

## Command Summary

| Command                                            | Details                                                                                                                                                                                                                                  |
|----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `add n/…​ p/…​ e/…​ a/…​ [t/TAG]…​`                | Adds a contact into the Address Book.<br/>**Example:**<br/>`add n/John Doe p/98765432 e/johnd@example.com a/John street, block 123, #01-01`                                                                                              |
| `addbystep`                                        | Prompts each required field in the address book entry                                                                                                                                                                                    |
| `list`                                             | List all contacts                                                                                                                                                                                                                        |
| `filter TAGNAME(s)`                                | Shows a list of persons in the address book, filtered by specified tags.<br/>**Example:**<br/>`filter friends family`                                                                                                                    |
| `find KEYWORD(s)`                                  | Finds persons whose names contain any of the given keywords.<br/>**Example:**<br/>`find John`                                                                                                                                            |
| `sort KEYWORD`                                     | Sorts contacts based on the input condition.<br/>**KEYWORDS:**<br/>`NAME`,`TAG`                                                                                                                                                          |
| `remove INDEX`<br/>`yes/no`                        | Safe removal of contact based on the index of the contact keyed in, followed by confirmation step before actual removal.<br/>**Example:**<br/>`remove 3 name`                                                                            |
| `edit INDEX [n/…​] [p/…​] [e/…​] [a/…​] [t/TAG]…​` | Adds a contact into the Address Book.<br/>**Example:**<br/>`add n/John Doe p/98765432 e/johnd@example.com a/John street, block 123, #01-01`                                                                                              |
| `duplicate n/…​ p/…​ e/…​ a/…​`                    | Adds the new contact to the address book, **assuming that a contact with identical identity already exists**.<br/>**Example:**<br/>`duplicate n/John Doe p/98765432 e/johnd@example.com a/John street, block 123, #01-01`                |
| `overwrite INDEX n/…​ p/…​ e/…​ a/…​ [tTAG]…​`     | Overwrites an existing contact in the address book, **assuming that a contact with an identical identity already exists**.<br/>**Example:**<br/>`overwrite 2 n/John Doe p/98765432 e/johnd@example.com a/John street, block 123, #01-01` |
| `copy INDEX FIELD(s)`                              | Copies a contact's information e.g. name, phone, email and address into OS clipboard.<br/>**Example:**<br/>`copy 4 name`                                                                                                                 |
| `undo`                                             | Undo the previous command entered.                                                                                                                                                                                                       |
| `redo`                                             | Reverses the previous `undo` command.                                                                                                                                                                                                    |
| `clear`                                            | Deletes all contacts                                                                                                                                                                                                                     |
| `exit`                                             | Exits and closes the program.                                                                                                                                                                                                            |

--------------------------------------------------------------------------------------------------------------------

## Glossary

### Lexicographical
* Order of words based on the alphabetical order of their letters.

### Operating System (OS) clipboard
* Temporary storage area in your computer's memory that stores data that has been copied from LookMeUp.
