Hyperlinks and Code Blocks
==========================

Hyperlinks
**********
Hyperlinks can be used to link to web sites, pages within the user guide, or a specific 
spot on a page in the user guide.

The Sphinx parser will recognise a URL and create the associated hyperlink, URLS may be
placed on their own line or within text

https://www.novel-t.ch/

To assign a hyperlink to a specific text backticks, angle brackets and a trailing underscore
are used ```Text <URL>`_``

::

    `Novel-T <https://www.novel-t.ch/>`_

Renders: `Novel-T <https://www.novel-t.ch/>`_

--------------------------------------------

To link to a document in the user guide use the ``:doc:`relative path without suffix``` construct

:doc:`/content/start/20intialsetup`
::

    :doc:`/content/start/20intialsetup`

Internal links may also be assigned to text in a similar same manner to external link assignment:
::

    :doc:`How to setup a user guide </content/start/20intialsetup>`

:doc:`How to setup a user guide </content/start/20intialsetup>`

--------------------------------------------

To link to a specific spot within a document by creating a reference tag using the ``.. _LocationName`` syntax
then referring to the tag with the ``:ref:`tag name``` syntax.

.. code-block:: rst
    :caption: Create the tag Style.css
        
        .. _Style.css:

        .. code-block ::
        :caption: **style.css** file in the **_staic** directory

        .wy-nav-content {
        max-width: 1300px !important;
        }

.. code-block:: rst
    :caption: Create reference link to the tag Style.css

        :ref:`Style File <style.css>`

:ref:`Style File <style.css>`

------------------------------------------------

Code Blocks
***********
Code samples are designated by a double colon at the end of a line follwed by the indented code sample that
remains indented.

::

    ::

        XmlDocument xml = new XmlDocument();
        xml.LoadXml(myXmlString); // suppose that myXmlString contains "<Names>...</Names>"
        
        XmlNodeList xnList = xml.SelectNodes("/Names/Name");
        foreach (XmlNode xn in xnList)
        {
        string firstName = xn["FirstName"].InnerText;
        string lastName = xn["LastName"].InnerText;
        Console.WriteLine("Name: {0} {1}", firstName, lastName);
        }

To add sytax highlighting use the code-block derective with the languare specified

.. code-block:: csharp

    .. code-block:: csharp

        XmlDocument xml = new XmlDocument();
        xml.LoadXml(myXmlString); // suppose that myXmlString contains "<Names>...</Names>"

        XmlNodeList xnList = xml.SelectNodes("/Names/Name");
        foreach (XmlNode xn in xnList)
        {
        string firstName = xn["FirstName"].InnerText;
        string lastName = xn["LastName"].InnerText;
        Console.WriteLine("Name: {0} {1}", firstName, lastName);
        }

Default code block language highlighting can be set in the conf.oy file using the 'highlight_language' property.