Initial Setup
+++++++++++++
The setup method will provide a standard theme, permit branding by adding the logo, favicon and background colour associated 
with user guide, and provide the mechanism for a dynamic table of contents in the sidebar.

----------------------------

Create and populate target directory
************************************
Select or create a local directory within which the Sphinx files for the user guide will be stored.

From within the target directory run **sphinx-quickstart** in the command prompt.

.. image:: /content/_images/cmd_su1.jpg
    :align: center

Accept default values and provide values for:
    * Project name: *Name of the User Guide it can contain spaces*
    * Author name(s): *Novel-T*
    * Project release []: *Optional*

The target directory will be populated with the basic files and folders required by Sphinx.

.. image:: /content/_images/img_su1.jpg
    :align: center

----------------------------

Create TOC folders 
*******************
The table of contents sections (blue in the sidebar) should each have a 
dedicated sub-folder within a content folder. Create a folder called 'content' in the
target directory and add the section sub-folders within.

.. image:: /content/_images/img_su2.jpg
    :align: center

Future table of contents sections will require the creation of subfolders and the editing of the index.rst file toctree directive.

----------------------------

Edit the conf.py file
*********************
Certain standard edits are required to the conf.py file in the target directory to enable basic 
branding and user guide standards. Open the configuration file and make the following changes:

#. Change the Sphinx theme from 'alabaster' to 'sphinx_rtd_theme' (Read the Docs) in the configuration value 'html_theme'
    *html_theme = 'sphinx_rtd_theme'*
#. Add the configuration value 'html_logo' and related options
    | *html_logo = ' ./content/_images/logo.jpg'*
    | *html_theme_options = {*
    |     *'logo_only': True,*
    |     *'display_version': False,*
    |     *'style_nav_header_background': 'white',*
    | *}*
#. Add the configuration value 'html_favicon' to ensure icons displayed in the browser tab align with the user guide requirements
    *html_favicon = './content/_images/favicon.ico'*
#. Add the configuration value 'html_show_sourcelink ' to remove link to view source page
    *html_show_sourcelink = False*

Actual configuration values entered will depend on user guide details, the configuration file should contain lines similar to:

.. code-block ::
   :caption: conf.py excerpt

    # -- Options for HTML output -------------------------------------------------

    # The theme to use for HTML and HTML Help pages.  See the documentation for
    # a list of builtin themes.
    #
    html_theme = 'sphinx_rtd_theme'
    html_logo = './content/_images/logo.jpg'
    html_theme_options = {
        'logo_only': True,
        'display_version': False,
        'style_nav_header_background': 'white',
    }
    html_favicon = './content/_images/favicon.ico'
    html_show_sourcelink = False


----------------------------

Edit the index.rst file
***********************
Certain standard edits are required to the index.rst file in the target directory to enable basic 
user guide standards and provide for dynamic table of contents section population. 
Open the index.rst file and make the following changes:

#. **By default the title is “Welcome to “ <project name> ”’s documentation!” this should be changed to something more meaningful.**
#. **A short text under the title should be added to describe the user guide and the product it supports.**
#. **Edit the toctree directives to support dynamic population of the sidebar.**

    The 'glob' option of the toctree directive instructs Sphinx to populate table of contents sections with designated pages sorted alphabetically by .rst file name. Edit the index.rst file toctree directives as such:

            | *.. toctree::*
            |    *:glob:*
            |    *:caption: Getting Started:*
            |    *:hidden:*
            |
            |    *content/start/**
 
    * **toctree** is the Sphinx directive to build the table of contents section in the sidebar
    * **glob** is the flag that instructs Sphinx to dynamically change the table of contents
    * **caption** is the table of contents section label (in uppercase blue in the table of contents)
    * **hidden** is the flag that instructs Sphinx to not display contents on the landing page
    * The path, after a blank line, instructs Sphinx where to find the pages to include in the table of contents
  
    The page headings will appear in the table of contents sections, as pages are added or removed from the designated path
    the table of contents will be automatically adjusted after each build command. No changes to the index.rst file will be 
    required unless sections are edited. The user guide can be updated by only running a 'make' command following any editing, 
    adding or removing content files.

#. **Remove or comment-out the default section that display Indices and Tables**

        | *Indices and tables*
        | *==================*
            
        | *:ref:`genindex`*
        | *:ref:`modindex`*
        | *:ref:`search`*

The index.rst file should now be similar to this:

.. code-block ::
   :caption: sample index.rst file

    Model Online User Guide
    =======================

    This document suggests a standard for online documentation that uses Sphinx with 
    the Read the Docs theme.

    This document was created using the standard and acts as both a model and a guide 
    to creating online user guides.


    .. toctree::
    :glob:
    :caption: Getting Started:
    :hidden:
    
    content/start/*

    .. toctree::
    :glob:
    :caption: Creating content in ReST:
    :hidden:

    content/rest/*

    .. toctree::
    :glob:
    :caption: GitHub Workflows:
    :hidden:

    content/github/*

----------------------------

Change content pane width
**************************
The default width of the content pane is rather narrow, as evident in the 
`ODK collect user guide <https://docs.getodk.org/>`_ which is also based upon Sphinx and Read the Docs. 
There are no configuration settings to adjust this therefore a basic custom style sheet is required. 
Add the following files in the locations indicated:

.. _Style.css:

.. code-block ::
   :caption: **style.css** file in the **_staic** directory

   .wy-nav-content {
    max-width: 1300px !important;
    }

.. code-block ::
   :caption: **layout.html** file in the **_templates** directory

   {% extends "!layout.html" %}
   {% block extrahead %}
       <link href="{{ pathto("_static/style.css", True) }}" rel="stylesheet" type="text/css">
   {% endblock %}

----------------------------

Update build files
******************
Following any changes to the conf.py, index.rst or content files the html files in the _build folder need to be updated. 
Use the make.bat file with the html option to update html files.

.. image:: /content/_images/cmd_su2.jpg
    :align: center

.. note:: 
   It is best practice to run ``make clean`` prior to ``make html`` to ensure the html files are properly created.

Open the _build/html/index.html file to view changes made to the document.

.. image:: /content/_images/cmd_su3.jpg
    :align: center