|image0| ICA Group

**P**

**Mambo User Manual**

+----------------------+---------------+---------------+----------------+------------------+--------------------------------------+-------------+
| **Diffusion date**   | **Writer**    | **Auditor**   | **Approver**   | **Approver’s**   | **Modifications**                    | **Index**   |
|                      |               |               |                |                  |                                      |             |
|                      |               |               |                | **stamp**        |                                      |             |
+======================+===============+===============+================+==================+======================================+=============+
| 2005/10/26           | L.Claisse     | M.Ounsy       | A.Buteau       | A.B.             | Creation                             | 1.0         |
+----------------------+---------------+---------------+----------------+------------------+--------------------------------------+-------------+
| 2005/11/17           | L.Claisse     | M.Ounsy       | A.Buteau       | A.B.             | Added multi-AC/VC and file system    | 1.1         |
+----------------------+---------------+---------------+----------------+------------------+--------------------------------------+-------------+
| 2006/11/17           | R.Girardot    | M.Ounsy       | A.Buteau       | A.B.             | Screenshots updated                  | 1.2         |
+----------------------+---------------+---------------+----------------+------------------+--------------------------------------+-------------+
| 2012/02/15           | A. Fourneau   | G.Abeillé     | A.Buteau       | A.B.             | Added tdb long term                  | 2.1         |
+----------------------+---------------+---------------+----------------+------------------+--------------------------------------+-------------+
| 2018/02/08           | M.Thiam       | R.Girardot    | A.Buteau       | A.B.             | -  Document template updated         | 3.0         |
|                      |               |               |                |                  |                                      |             |
|                      |               |               |                |                  | -  Screenshots updated               |             |
|                      |               |               |                |                  |                                      |             |
|                      |               |               |                |                  | -  Added some missing descriptions   |             |
+----------------------+---------------+---------------+----------------+------------------+--------------------------------------+-------------+
|                      |               |               |                |                  |                                      |             |
+----------------------+---------------+---------------+----------------+------------------+--------------------------------------+-------------+

Diffusion: for information

Receivers: Any archiving User

| 
| **Index**

`*1.* *Introduction* 4 <#_Toc505844906>`__

`*2.* *Application’s context: Historic and Temporary archiving*
4 <#_Toc505844907>`__

`*3.* *Application’s description and goals* 5 <#_Toc505844908>`__

`*3.1* *Application’s goals* 5 <#_Toc505844909>`__

`*3.2* *A first look at Mambo* 6 <#a-first-look-at-mambo>`__

`*4* *Account manager* 7 <#account-manager>`__

`*4.1* *Creating a new account* 7 <#creating-a-new-account>`__

`*4.2* *Deleting an existing Account* 8 <#_Toc505844913>`__

`*4.3* *Launching application with an existing account*
8 <#_Toc505844914>`__

`*5* *Control archiving* 9 <#_Toc505844915>`__

`*5.1* *Creating/modifying an AC* 10 <#_Toc505844916>`__

`*5.2* *The opened ACs menu* 16 <#_Toc505844917>`__

`*5.3* *Starting/Stopping archiving on an AC*
17 <#startingstopping-archiving-on-an-ac>`__

`*5.3.1* *The Current Archiving Configuration detail panel*
17 <#the-current-archiving-configuration-detail-panel>`__

`*5.3.2* *Starting/Stopping archiving on an AC* 17 <#_Toc505844920>`__

`*5.4* *Displaying an AC* 18 <#displaying-an-ac>`__

`*5.4.1* *The Current Archiving Configuration detail panel*
18 <#the-current-archiving-configuration-detail-panel-1>`__

`*5.4.2* *The Archiving assessment window*
19 <#the-archiving-assessment-window>`__

`*5.5* *Saving/Loading an AC* 19 <#_Toc505844924>`__

`*5.5.1* *Saving an individual AC* 19 <#saving-an-individual-ac>`__

`*5.5.2* *Saving all opened ACs* 20 <#saving-all-opened-acs>`__

`*5.6* *Transfer to VC* 20 <#_Toc505844927>`__

`*6* *Exploit archived data* 21 <#exploit-archived-data>`__

`*6.1* *Creating/modifying a VC* 22 <#creatingmodifying-a-vc>`__

`*6.2* *The opened VCs menu* 26 <#the-opened-vcs-menu>`__

`*6.3* *Displaying a VC* 27 <#_Toc505844931>`__

`*6.4* *Saving/Loading a VC* 30 <#savingloading-a-vc>`__

`*6.5* *Using the Variations functionality* 30 <#_Toc505844933>`__

`*7* *Options* 32 <#_Toc505844934>`__

`*7.1* *Application’s history save/load options* 32 <#_Toc505844935>`__

`*7.2* *AC options* 33 <#ac-options>`__

`*7.3* *VC options* 34 <#vc-options>`__

`*7.4* *General options* 35 <#general-options>`__

`*8* *The Mambo toolbar* 36 <#the-mambo-toolbar>`__

\ *Introduction*
================

This document is an end-user guide to using the Mambo application, and a
brief developer-oriented presentation of the application’s architecture.

\ *Application’s context: Historic and Temporary archiving *
============================================================

    The goal is the automatic archiving of the values of a set of Tango
    Attributes, in a given time range.

    In this time range, the value of an attribute is archived:

-  Every [*given time interval*]

    ***AND***

-  When the attribute’s value meets [*given condition on attribute’s
       value*],

    where [*given time interval*] and [*given condition on attribute’s
    value*] are user-defined for each attribute (individually or for a
    group of attributes).

    Each attribute value is associated with a time stamp, representing
    the time when the attribute value was read. This time stamp is
    archived as well.

    Attributes can be archived in two distinct databases:

-  The Historical Data Base (***HDB*** henceforth): attributes values
       are stored forever.

-  The Temporary Data Base (***TDB*** henceforth): every [*given
       deletion time*], the oldest attributes values records are
       deleted. The TDB is regularly purged. The Interval of this purge
       is defined by the data base administrator and the system
       administrator.

    When an attribute is “being ***archived***\ ”, it means that every
    [*base time unit*], the archiving device tests whether the current
    value of the attribute has to be stored in HDB (resp. TDB).

    If the test is positive, a record is added in the table for this
    attribute.

    Later, those values can be ***exploited***. It can be selected from
    HDB/TDB to be displayed and saved in a file

\ *Application’s description and goals*
=======================================

\ *Application’s goals*
-----------------------

    Mambo allows the user to define *configurations* that describe the
    archiving and exploitation for a group of attributes. Those
    *configurations* can be saved as files and modified.

    Mambo is thus naturally divided (both in functionalities and
    display) in two parts:

-  The archiving control part.

-  The archived data exploitation part.

\ **
**

*A first look at Mambo*
-----------------------

    |image1|

    Figure 1: General view of Mambo

-  The Archiving Control panel is where the user controls the archiving
       of Tango attributes in HDB/TDB.

    To do so, the user can create/modify archiving configurations, and
    Start/Stop those configurations.

    An ***Archiving Configuration*** is a list of attributes to be
    archived, with a list of archiving parameters for each attribute.

    Users can also start/stop the archiving of some attributes in the
    configuration, (see 5.3.2 *Starting/Stopping archiving on an AC*).

-  The Data Exploitation panel is where the user exploits the previously
       stored data, mainly displaying curves and extracting raw data
       from HDB/TDB.

    He does so by creating/modifying ***View Configurations***, and
    calling **View** **Stop** on those configurations.

    A ***View Configuration*** is a list of attributes to be displayed,
    with a list of displaying parameters for each attribute.

-  The Menu and the Tool bar are for actions shortcuts and application’s
       options.

    Each panel will be detailed in its own subsection.

    **
    **

*Account manager*
=================

    The Mambo Account Manager is here to manage accounts, which means:

-  Creating a new account.

-  Deleting an existing account.

-  Launching application with an account chosen in a list.

An account is associated with a directory, in which are stored
application setup and history. Having various accounts allows different
users to have their own application configuration and history.

    |image2|

    Figure 2: Mambo Account Manager

    The above figure presents the account Manager Interface, at
    application start. With this manager, user can create a new account,
    or delete or use an existing one.

    To quit the application, simply click on |image3| or |image4|
    button.

    Existing accounts are listed in the account Selection Combo Box,
    which you can be reloaded by clicking on |image5| button (if you
    think that someone could have modified it by creating a new account
    or deleting an existing one, for example).

*Creating a new account*
------------------------

    To create a new account, click on the |image6| button (at the bottom
    left of the panel). A new dialog will appear, as following.

    |image7|

    Figure 3: Creating a new account

    In this new dialog, you will have to enter the name of your new
    account and the path of the application working directory for this
    account. If you prefer, you can browse for the path by clicking on
    the |image8| button. Then, a classic browsing dialog will be
    displayed, in which you can choose the directory. When both fields
    (“Name” and “Path”) are fulfilled, click on |image9| button to
    validate your new account, which will be automatically added in the
    list of existing accounts. If you click on |image10| or |image11|
    button, you go back to the first dialog, as presented in, and
    nothing is done.

\ *Deleting an existing Account*
--------------------------------

    To delete an existing account, first select the account in the
    account Selection Combo Box, as following:

    |image12|

    Figure 4: Account selection

    When the account is selected, click on |image13| button to delete
    it. If you do it, you won’t be able to use this account any more
    (and no other user either), because the account is definitely
    removed from list. The account deletion doesn’t involve the
    corresponding directory (neither its content) deletion.

    If you want to see your account path, you can check “Show account
    path”.

    |image14|

    Figure :Show account path

\ *Launching application with an existing account*
--------------------------------------------------

    To launch application with an existing account, first select the
    account in the account Selection Combo Box, as presented in *Figure
    4: Account selection*.

    Then, click on |image15| button, and you will reach the application
    main panel configured with this account (the account name is
    displayed in frame title).

    \ **
    **

\ *Control archiving*
=====================

    This section deals with controlling archiving of Tango attributes
    through **Archiving Configurations** (henceforth **AC**).

    An AC describes which attributes to archive and how, and consists
    of:

-  General information (when the AC was created …).

-  A list of attributes to archive.

-  For each attribute, a set of HDB/TDB archiving modes.

    ACs is accessed/used in the AC panel:

    |image16|

    Figure 6: The AC panel

    **
    **

\ *Creating/modifying an AC*
----------------------------

    The creation or modification of an AC is done the same way, using
    the New/Modify button respectively. We will see how to load an AC
    later.

    *Step 1: AC general properties*

-  Click the New/Modify button in the AC actions panel

-  The following dialog appears

    |image17|

    Figure : Step1, general properties

-  You can choose a name for the AC. This field isn’t mandatory but it
       is recommended to fill it, to better identify your different ACs
       later.

-  The creation and update dates are filled or modified automatically
       upon saving an AC. Click next

    *Step 2: Select the AC attributes*

    There are 2 ways to select the AC attributes. The user can choose a
    selection method in the Options.

    *Step 2, method 1:*

    |image18|

    Figure 8: Step 2, select AC attributes (standard method)

-  The left tree lists the Tango attributes. The right tree represents
       the current attributes of the edited AC. Both trees have the same
       structure of TANGO\_HOST/Domains/Families/Members/Attributes.

    *WARNING* The left tree listing the Tango attributes is initially
    only loaded up to Members level to avoid overloading. The attributes
    are loaded upon user selection of a Member (device) node.

-  Adding attributes to the current AC:

   -  Select a tree node to expand it.

   -  Select attributes in the left tree then press the right arrow to
          add them to the current AC.

   -  Select a node in the left tree then press the right arrow to add
          all attributes under this node to the current AC (only works
          if those attributes were loaded).

-  Removing attributes from the current AC:

   -  Select attributes in the right tree then press the red X to remove
          them from the current AC.

   -  Select a node in the right tree then press the red X to remove all
          attributes under this node from the current AC.

-  Using “Match” to filter attributes:

    The user can enter an expression of the form D/F/M and click match
    to filter attributes in the left and right trees.

    D represents the Domains; F represents the Families, and M the
    Members. All trees can contain the joker character ‘\*’.

    Since the tree loading is initially only up to Member level, it’s
    not possible to filter up to Attributes level.

    *Step 2, method 2:*

    |image19|

    Figure 9: Step 2, select AC attributes (alternate method)

-  Attribute selection and automatic attributes adding:

   -  Choose a Domain. This refreshes the list of possible Device
          classes for this Domain.

   -  Choose a Device class. This refreshes the list of possible
          Attributes for this Domain and Device class.

   -  Choose an Attribute and press Add attribute:

   -  All Attributes

      -  with the selected name

    ***AND***

-  belonging to any Device of the selected Class and Domain are added to
       the current AC’s list of attributes.

    All new attributes are red until the AC is saved.

-  Line level sub-selection of loaded attributes:

    Each attribute is initially checked, but this check can be removed
    by the user. When the user clicks on next, all unchecked attributes
    will be removed from the current AC.

-  Click “Select All” to select all lines.

-  Click “Select None” to select no line.

-  Select lines in the list (CTRL and SHIFT are usable), then click
       “Reverse for selected lines” to reverse the checked/unchecked
       status of all selected lines.

    *Step 3: Set the AC attributes properties*

    |image20|

    Figure 10: Step 3, selecting archiving modes

-  A general description of the properties setting process:

    The way you set up archiving modes for each attribute is as follows:

-  Select a group of attributes.

-  Edit HDB/TDB modes.

-  Call “Set” for the current group of attributes: the currently
       displayed modes are applied to all attributes of the selection.

-  Repeat with next group of attributes.

-  End edition by clicking “Finish”.

-  Attributes selection

    The setting up of archiving modes can be “factorized” for a
    selection of attributes. All attributes of the selection will be set
    up with the currently displayed properties when the user presses
    “Set”.

    The multiple selections can consist of:

-  A manual select at Attributes level (CTRL and SHIFT are usable).

-  Selection of an upper node level: all Attributes nodes under this
       node will be set up.

-  A combination of the two.

-  Unset attributes and default values

    Attributes which haven’t received any Mode yet (unset) are displayed
    in *Italic*. Attributes which have (set) are displayed in **Bold. **

    Clicking on a set attribute displays its archiving modes.

    Clicking on an unset attribute displays default archiving modes.

-  Controls upon AC validation.

    The user can not choose any and all combination of modes, nor any
    and all numeric values for each mode. Thus, controls are performed
    upon call to “Finish”:

-  If any HDB (resp. TDB) mode is chosen for a given attribute, it must
       also have the basic HDB (resp. TDB) Periodic mode.

-  Any unset attribute will be removed from the AC; the user is prompted
       to continue editing the AC, or ignore them.

-  Numeric values are controlled for each mode.

    When the validation is over, the AC is displayed in the
    application’s AC panel.

\ *
*

\ *The opened ACs menu*
-----------------------

    Mambo can have several opened ACs at once, even if only one is
    displayed on screen at a time. A drop-down menu allows the user to
    choose an AC in the list of opened ACs:

-  Each time the user loads an AC, it’s added to the top of the opened
       ACs list (the older ACs are shifted downwards in the opened ACs
       list)

-  The list identifies ACs by their name and date of last update. When
       the user selects an AC, it becomes the current AC, and its
       general information and attributes are displayed.

-  To remove an AC from the list, push the red X button (this will do
       nothing if the list is empty or only has 1 element). The next AC
       in the reduced list (i.e. the one that was added to the list the
       most recently) is automatically displayed.

-  The list can hold no more than *[MAX\_NUMBER]* ACs, this number can
       be defined in the AC tab of the options panel (default=5). If the
       list’s length reaches *MAX\_NUMBER,* the oldest AC will be
       removed from the list when needed.

-  ACs that have unsaved modifications are identified by a red star.

    If Mambo has the “History save” option turned on, the list of opened
    ACs will be saved at shutdown, and loaded at startup.

    |image21|

    Figure 11: Acs menu

\ *
*

1. .. rubric:: *Starting/Stopping archiving on an AC*
      :name: startingstopping-archiving-on-an-ac

   1. .. rubric:: *The Current Archiving Configuration detail panel*
         :name: the-current-archiving-configuration-detail-panel

    Attributes are displayed differently in selection trees, with
    respect to their current archiving status. The display shows their
    current status in DB, not their archiving modes in the current AC.

-  Attributes which aren’t being archived are displayed as off bulbs:
       |image22|

-  Attributes which are being archived only in HDB are displayed as on,
       yellow bulbs: |image23|

-  Attributes which are being archived only in TDB are displayed as on,
       brown bulbs: |image24|

-  Attributes which are being archived in HDB and TDB are displayed as
       on, bicolor bulbs:\ |image25|

   1. .. rubric:: \ *Starting/Stopping archiving on an AC*
         :name: startingstopping-archiving-on-an-ac-1

    *Starting archiving*:

-  Create/Load an AC or just use the current AC. The AC that will be
       used is the one displayed in the application’s AC panel.

-  Call Start to start archiving each attribute by all its modes.

    *Stopping archiving: *

-  Create/Load an AC or just use the current AC. The AC that will be
       used is the one displayed in the application’s AC panel.

-  Call Stop to stop archiving of each attribute. All archiving modes
       will be stopped.

    In both cases, a success/failure message confirms the action.

\ **
**

1. .. rubric:: *Displaying an AC*
      :name: displaying-an-ac

   1. .. rubric:: *The Current Archiving Configuration detail panel*
         :name: the-current-archiving-configuration-detail-panel-1

|image26|

Figure 12: Detail of the current AC

    This panel represents the current Archiving Configuration.

    On the left, a tree lists all of the AC’s attributes.

    When the user selects a given attribute on this tree, its HDB and
    TDB modes are displayed on the right sub-panel.

    This displays the attributes modes individually. To get a global
    view of the AC’s Archiving Modes, use the “Archiving assessment”
    command.

*The Archiving assessment window*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

|image27|

Figure 13: Global view of all the modes of an AC

    This window sums up the current Archiving Configuration in two tabs
    (one for HDB, one for TDB).

    For each attribute contained in the current AC, its archiving modes
    are detailed, and if the attribute is being archived, can be
    compared to the modes values found in HDB (resp. TDB).

1. .. rubric:: \ *Saving/Loading an AC*
      :name: savingloading-an-ac

   1. .. rubric:: *Saving an individual AC*
         :name: saving-an-individual-ac

    Archiving Configurations are saved /loaded as XML files, with the
    .ac file extension.

    In the menu, select “ACs/Save” or “File/Save/Archiving
    configuration”:

    Saved operations work like they do with Word (for example):

-  The first time a file is saved, the user is prompted to choose a path
       and file name. Initially the file chooser dialog is in the “ac”
       subdirectory of the Mambo working directory. The “.ac” file
       extension is automatically added if the user doesn’t.

-  If a file was already saved, it will automatically be saved in the
       same file the next time the “Save” menu is selected.

-  The user can still specify a different file, by using the “ACs /Save
       as” menu (or “File/Save As/Archiving configuration”).

    When an AC is loaded, it becomes the current Archiving Configuration
    and it is added to the list of opened ACs.

    In both cases, a success/failure message confirms the action in the
    log panel.

*Saving all opened ACs*
~~~~~~~~~~~~~~~~~~~~~~~

    It is possible to save all opened ACs. Only modified ACs will be
    saved (i.e. the ACs that has a “red star”).

    In the menu, select “ACs/Save All”:

    For each modified AC, the save operation will follow the same rules
    as an individual save:

-  If the file has already been saved before, it will be saved silently.

-  Otherwise, the user will be prompted to choose a directory and file.

    In this case, the ACs that are being saved are successively selected
    before each file chooser prompt (so that the user knows which AC
    he’s choosing a path for).

    The generic “Save All” menu item in “File/ Save All” does this and
    the same thing for opened VCs.

\ *Transfer to VC*
------------------

    This functionality is used to quickly create a VC on the same
    attributes as a given AC (for example, when the user wants to
    monitor the values of attributes after starting archiving on an AC).

    It will create a VC automatically, with the following properties:

-  Its attributes list is the same as the AC the “Transfer to VC”
       functionality is used on

-  The attributes values are all extracted from HDB, even if some of the
       AC’s attributes were only archived in TDB (obviously, the display
       for such an attribute will be empty).

-  The date range of a one-hour range ends when the VC is created

-  Every Attribute has an automatically determined color (if there are
       more attributes than colors to choose from, different attributes
       will have the same color).

\ **
**

*Exploit archived data*
=======================

    This section deals with controlling exploitation of archived
    attributes (HDB/TDB) through **View Configurations** (henceforth
    **VC**).

    A VC describes which attributes to display and how, and consists of:

-  General information (when the VC was created, the date range to
       extract …).

-  A list of attributes to display.

-  For each attribute, a set of display properties.

    The archived attributes of a VC either all come from HDB or all come
    from TDB, since it wouldn’t make sense to display HDB and TDB
    attributes in a common plot,

    VCs are accessed and used in the VC panel:

|image28|

Figure 14: The VC panel

\ **
**

*Creating/modifying a VC*
-------------------------

    Creation or modification of a VC is done the same way, using the
    New/Modify button respectively. We will see how to load a VC later.

    *Step 1: VC general properties*

    Those properties don’t depend on a specific attribute. They are
    common to all VC attributes or describe the VC.

    Click the New/Modify button in the VC actions panel, the following
    dialog appears:

|image29|

Figure 15: Step 1, general properties

*Step 1.1: VC properties*

-  You can choose a name for the VC. This field isn’t mandatory but it
   is recommended to fill it.

-  The creation and update dates are filled automatically upon saving
   the VC.

-  The user must define a date *range* (Start/End dates\ *)* to extract
   data from. This can be done either manually, or by selecting a “Since
   xxx” item in the “Date range” drop-down menu.

    In the latter case, the user can check the “Dynamic date range”.
    What this option does is recalculate the Start/End dates at each
    edition or refreshing the VC (see 6.3 *Displaying a VC*).

    Example: At 09:00 the user chose “Last 1 hour” as the “since
    option”.

    The date range will be [08:00-09:00].

    If the VC is then edited at 11:00, and “Dynamic date range” was
    checked, the date range will be [10:00-11:00]; otherwise it will
    still be [08:00-09:00].

-  If the “Historic” checkbox is checked, VC attributes will be chosen
   among HDB attributes (otherwise, TDB).

-  If the “History” checkbox is not checked, you are in TDB mode so you
   can import long term snapshot. In this case you can’t modify start
   and end date because the snapshot configures it himself.

*Step 1.2: General chart properties*

-  The user can define global chart properties (title, background …).

    |image30|

Figure 16: Step 1, general chart properties

*Step 1.3: Y1 axis properties*

|image31|

Figure 17: Step 1, Y1 axis properties

-  The user can define the left vertical axis properties (title, scale,
   …).

*Step 1.4: Y2 axis properties*

|image32|

Figure : Step 1, Y2 axis properties

-  The user can define the right vertical axis properties (title, scale,
   …).

    *Step 2: Select the VC attributes*

    The attributes selection works the same way as an AC attributes
    selection, except for two differences:

-  The only available selection mechanism is the tree selection

    The trees are initially loaded to the attributes level.

|image33|

Figure : Step 2, selecting attributes

-  The left tree lists the HDB (resp. TDB) attributes. The right tree
   represents the current attributes of the edited VC. Both trees have
   the same structure of HDB (resp.
   TDB)/Domains/Families/Members/Attributes.

    *WARNING* Unlike AC trees, VC trees are initially loaded to the
    Attributes level since archived attributes are a small subset of all
    Tango attributes.

-  Consequently, the match functionality works up to attributes names:
   one can use a D/F/M/A criterion.

*Step 3: Set the VC attributes properties*

-  General flow

    To set the VC attributes, user can refer to the ACs, it’s the same
    process.

    |image34|

Figure 20: Set the vc attributes

*Step 4: Controls upon VC validation *

-  Any unset attribute will be removed from the VC; the user is prompted
   to continue editing the VC, or ignore them.

-  The VC’s date range is controlled

When the validation is over, the VC is displayed in the application’s VC
panel.

*The opened VCs menu*
---------------------

    The VCs menu opens in the same way as the ACs menu.

    See 5.2 *The opened ACs menu*

\ *
*

*Displaying a VC*
-----------------

|image35|

Figure 21: The current VC panel

    This panel represents the current View Configuration; a tree lists
    all the VC’s attributes.

    To view specific parameters, the user must use the “Modify” button.

    Thanks to the docking, users can see two generals information.

|image36|

Figure 22: Extraction of Number and Boolean Scalars

    This panel shows the attribute’s extractions.

    If the user wants to extract attributes, he must select his time
    range then press to the button refresh\ |image37|.

    If he wants to stop the refreshing he will press to the button
    cancel\ |image38|.

|image39|

Figure 23: Extraction of String and State Scalars

This panel gives Extraction of the string and state scalars.

|image40|

Figure 24: Extraction of Boolean Spectra

This panel shows the results of the Extraction of Boolean spectra.

\ *
*

*Saving/Loading a VC*
---------------------

    The user does the same thing as in ACs to save or load VC.

    See 5.5 *Saving/Loading an AC*.

\ *Using the Variations functionality*
--------------------------------------

    The Variations functionality is a filter which comes between a VC
    and the final plot display.

|image41|

Figure 25: The "variations" attributes selection window

    The Variations window lists the VC attributes and their “variation”,
    which is defined as the difference between the min and max values in
    the VC’s date range.

    The user can then select attributes which variations that seem
    abnormal or interesting, and only plot those attributes.

    The Variations window is made of two different tables:

-  The first one shows for every attribute its minimum and maximum
       values, and its variation.

-  The second one gives every attribute and its balanced variation.

    Select lines in the left table, and press “View Selected Attributes”
    to display the filtered plot.

|image42|

Figure 26: The View selected attributes

\ *Options*
===========

Mambo manages global options. Those options are saved on application
shutdown, and loaded on startup.

The Options menu is located in the Menu bar: ToolsOptions.

\ *Application’s history save/load options*
-------------------------------------------

    These options define whether Mambo has a history, i.e. a persistent
    state when closed/reopened.

    If “Yes” is checked, a XML History file will be saved in Mambo’s
    workspace, and on next start up the current AC and VC will be
    loaded.

    |image43|

Figure : The history options

\ **
**

*AC options*
------------

    Options for all Archiving Configurations, the user can define:

-  An attribute selection mechanism for AC edition (see 5 *Control
       archiving*).

-  Default modes selection and values for HDB and TDB archiving (see 5.1
       *Creating/modifying an AC*).

   -  The selected modes and values will be preset for all unset
          attributes.

   -  The default values can be saved to /loaded from an Archiving
          Configurations Defaults file (.acd extension).

   -  The “Restore defaults” button reloads the defaults with non
          user-modifiable predefined values.

-  The size of the “AC stack”, that is the maximum number of opened ACs.

|image44|

Figure : The AC options

\ 

*VC options*
------------

    These are the options for all View Configurations. The user can
    define:

-  Whether he wants to display the Read value of attributes only, the
       Write value only, or both.

-  The size of the “VC stack”, that is the maximum number of opened VCs.

-  The chart properties.

-  The spectrum view (spectrum view type).

|image45|

Figure : The VC options

**
**

*General options*
-----------------

    The user can define:

-  The column separator for the tables

-  The buffering of Tango attributes.

|image46|

Figure : General options

\ 

*The Mambo toolbar*
===================

    The toolbar is located under the menu bar, and consists mainly of a
    set of shortcuts to often used functionalities.

    |image47|

Figure 31: The Mambo toolbar

-  |image48| is a shortcut to create a new Archiving configuration or a
   new View configuration.

-  |image49| is a shortcut to load an Archiving configuration or a View
   configuration.

-  |image50| is a shortcut to save an Archiving configuration or a View
   configuration.

-  |image51| is a shortcut to save quickly all Archiving configurations
   or View configurations.

-  |image52| is a shortcut to print Archiving configuration or View
   configuration.

-  |image53| is a shortcut to reset Archiving configuration or View
   configuration.

**
**

\ **Appendices**

**
**

\ **Lexicon**

*Archiving*

The action of storing in database the values of Tango attributes in a
time range, each value being associated with a time stamp.

*Archiving mode*

An archiving mode is a rule defining when an attribute has to be
archived.

The most basic archiving mode is the Periodic archiving mode, where an
attribute is archived every N milliseconds.

More elaborate archiving modes like the Threshold archiving mode ask for
archiving when the attribute’s value meets certain conditions, but they
can only be used in association with the Periodic archiving mode.

*AC*

Short for an Archiving Configuration

Describes archiving for a set of attributes, by associating a set of
archiving modes to each of its attributes.

*VC*

Short for a View Configuration.

Describes plot properties for a set of attributes, by associating a set
of plot properties to each of its attributes.

*HDB*

Short for the Historic Database.

Attributes values archived in HDB are stored forever.

*TDB*

Short for the Temporary Database.

Attributes values archived in TDB are deleted every [given deletion
time].

The TDB is regularly purged and the Interval of the purge is defined by
the data base administrator and the system administrator.

*Quick Save/Quick load*

The action of saving (resp. loading) to a default file is Called “quick”
because no user interaction to choose a directory/file name is required.

.. |image0| image:: media/image5.png
   :width: 1.68750in
   :height: 0.84375in
.. |image1| image:: media/image6.png
   :width: 6.30000in
   :height: 4.38125in
.. |image2| image:: media/image7.png
   :width: 4.30268in
   :height: 2.00028in
.. |image3| image:: media/image8.png
   :width: 1.56272in
   :height: 0.22920in
.. |image4| image:: media/image9.png
   :width: 0.50007in
   :height: 0.22920in
.. |image5| image:: media/image7.png
   :width: 1.28788in
   :height: 0.22727in
.. |image6| image:: media/image7.png
   :width: 0.99242in
   :height: 0.21970in
.. |image7| image:: media/image10.png
   :width: 3.11502in
   :height: 1.41686in
.. |image8| image:: media/image10.png
   :width: 0.74400in
   :height: 0.23200in
.. |image9| image:: media/image10.png
   :width: 0.41600in
   :height: 0.23200in
.. |image10| image:: media/image11.png
   :width: 0.63551in
   :height: 0.22920in
.. |image11| image:: media/image9.png
   :width: 0.50007in
   :height: 0.22920in
.. |image12| image:: media/image12.png
   :width: 4.30268in
   :height: 2.00028in
.. |image13| image:: media/image13.png
   :width: 1.51433in
   :height: 0.25072in
.. |image14| image:: media/image14.PNG
   :width: 4.30268in
   :height: 2.00028in
.. |image15| image:: media/image14.PNG
   :width: 1.00000in
   :height: 0.24800in
.. |image16| image:: media/image15.png
   :width: 6.30000in
   :height: 5.89514in
.. |image17| image:: media/image16.png
   :width: 6.30000in
   :height: 6.12569in
.. |image18| image:: media/image17.png
   :width: 6.64770in
   :height: 7.24638in
.. |image19| image:: media/image18.png
   :width: 5.02273in
   :height: 4.88376in
.. |image20| image:: media/image19.png
   :width: 6.30000in
   :height: 4.66736in
.. |image21| image:: media/image20.png
   :width: 5.79304in
   :height: 5.06061in
.. |image22| image:: media/image21.png
   :width: 0.19722in
   :height: 0.16875in
.. |image23| image:: media/image22.png
   :width: 0.19722in
   :height: 0.18333in
.. |image24| image:: media/image23.png
   :width: 0.19722in
   :height: 0.18333in
.. |image25| image:: media/image24.png
   :width: 0.19722in
   :height: 0.18333in
.. |image26| image:: media/image25.png
   :width: 6.11062in
   :height: 5.05244in
.. |image27| image:: media/image26.png
   :width: 6.56818in
   :height: 3.94077in
.. |image28| image:: media/image27.png
   :width: 6.30000in
   :height: 4.87153in
.. |image29| image:: media/image28.png
   :width: 5.33071in
   :height: 7.67728in
.. |image30| image:: media/image29.png
   :width: 3.34252in
   :height: 4.40551in
.. |image31| image:: media/image30.png
   :width: 3.21920in
   :height: 3.62551in
.. |image32| image:: media/image31.png
   :width: 3.36505in
   :height: 4.00056in
.. |image33| image:: media/image32.png
   :width: 5.22737in
   :height: 7.68432in
.. |image34| image:: media/image33.png
   :width: 6.30000in
   :height: 4.88681in
.. |image35| image:: media/image34.png
   :width: 6.30000in
   :height: 6.19722in
.. |image36| image:: media/image35.png
   :width: 6.49242in
   :height: 3.79226in
.. |image37| image:: media/image36.PNG
   :width: 0.65973in
   :height: 0.24963in
.. |image38| image:: media/image37.PNG
   :width: 0.59118in
   :height: 0.21420in
.. |image39| image:: media/image38.png
   :width: 6.30000in
   :height: 3.41250in
.. |image40| image:: media/image39.png
   :width: 6.10236in
   :height: 3.30545in
.. |image41| image:: media/image40.png
   :width: 5.94795in
   :height: 3.31818in
.. |image42| image:: media/image41.png
   :width: 6.30000in
   :height: 6.30000in
.. |image43| image:: media/image42.png
   :width: 6.30000in
   :height: 6.79167in
.. |image44| image:: media/image43.png
   :width: 6.30000in
   :height: 6.79167in
.. |image45| image:: media/image44.png
   :width: 6.30000in
   :height: 6.79167in
.. |image46| image:: media/image45.png
   :width: 6.02731in
   :height: 5.17424in
.. |image47| image:: media/image25.png
   :width: 6.30000in
   :height: 5.20903in
.. |image48| image:: media/image1.png
.. |image49| image:: media/image46.png
   :width: 0.18753in
   :height: 0.16669in
.. |image50| image:: media/image47.png
   :width: 0.20833in
   :height: 0.20833in
.. |image51| image:: media/image48.png
   :width: 0.26045in
   :height: 0.22920in
.. |image52| image:: media/image3.png
.. |image53| image:: media/image4.png

