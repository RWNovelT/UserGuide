Text and Headings
+++++++++++++++++

Text Formats
************
The rst syntax provides for *italic*, **bold**, ``verbatum``, and `hyperlink <https://en.wikipedia.org/wiki/Hyperlink>`_ formats as detailed in the below table.

.. csv-table:: Font syntax
   :header: format, syntax, rendering
   :widths: 15 45 30

   italic, ``*italic*`` (single asterisk before and after), *italic*
   bold, ``**bold**`` (double asterisk before and after), **bold**
   verbatim, ````verbatum```` (double backtick before and after ), ``verbatum``
   link, ```hyperlink <https://en.wikipedia.org/wiki/Hyperlink>`_`` (backticks angle brackets and trailing underscore), `hyperlink <https://en.wikipedia.org/wiki/Hyperlink>`_

----------------------------

Headings
********
The following symbols underline text to format headings, underlines must be at least as long 
as the heading text.

  #. The top level with a plus sign ``+`` 
  #. The next level with an asterisk ``*`` 
  #. The next level with an equals sign ``=``
  #. The next level with an hyphen ``-``
  #. The next level with an caret symbol ``^``

For example:

.. image:: /content/_images/img_rest20_1.jpg

Was written in .rts as:

.. code-block:: rst
    :caption: Formating headers in rst

    Level 1 Heading
    +++++++++++++++
    Level 2 Heading
    ***************
    Level 3 Heading
    ===============
    Level 4 Heading
    ---------------
    Level 5 Heading
    ^^^^^^^^^^^^^^^

Headings will appear nested in the table of contents in the sidebar to four levels.

.. image:: /content/_images/img_rest20_2.jpg
   :align: left