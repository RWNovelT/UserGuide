Content Overview
++++++++++++++++
Content is added to online user guides in the form of restructured text (.rst) files or markdown (.md) files, 
this document will focus on .rst files and provide an overview of the .rst syntax used when creating user guide 
content.

Each content file will appear as an item in the table of contents when the html files are update with 
the ``make html`` command.

    * The order of appearance in the contents is based on the alphabetical order of content file names
    * The name in the contents is that of the content files main header
  
In this example, the table of contents has two entries in the "GETTING STARTED" section, these section do not 
appear in alphabetical order as it is deemed that the "Prerequisites" section should logically come before the 
"Initial Setup" section. To accomplish this content files names have numeric prefixes in multiples of ten to 
permit the insertion of future content files between existing files.

.. image:: /content/_images/img_rest10_1.jpg
    :align: center

To update the user guide, changes need only to be made to the content files, saved, and then processed by running 
the ``make html`` from the root directory at the command prompt in a terminal. Content files can be edited, change 
their titles, be removed or new files added; and Sphinx will automatically update the table of contents in the left
sidebar.

If a new section (upper case and in blue ex. "GETTING STARTED") is to be added to the table of contents, then 
changes will also need to be made to the directory structure and the index.rst file (see Initial Setup for details). 
It is expected that most changes will involve content files only once the initial user guide is created.

The following topics in this section provide a basic overview of content creation in the rst syntax supported by 
Sphinx. Further functionality can be added by using custom style sheet (.css) files which is beyond the scope of 
this document.
