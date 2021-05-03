Lists and Tables
================

Lists
*****
To start a new line, or create a non-bulleted list insert a bar and a space at the beginning of the line ``|``, this construct
provides a list that has neither bullets not numbers, and can be used to format paragraphs without inserting blank lines.

    | First line
    | Second line
    | Third Line

.. code-block ::
  :caption: syntax for bulleted list show above

        | First line
        | Second line
        | Third Line

| A bullet list can be created by inserting either an asterisk ``*`` or a dash ``-`` at the beginning of the line.
| Lists may be indented to one level only and the bullet changes form when indented.
| Text formatting *italic*, **bold**, ``verbatim`` and `hyperlinks <https://www.novel-t.ch/>`_ can be used in lists.

    * list 1 item 1
    * list 1 *item 2*
    * list 1 **item 3**

-----------------------------

    * **List 2 item 1**
    * List 2 item 2
        * List 2 item 2.1
    * **List 2 item 3**

-----------------------------

            - List 3 item 1
            - List 3 `item 2 <https://www.novel-t.ch/>`_ 


.. code-block ::
  :caption: syntax for bulleted lists show above

        * list 1 item 1
        * list 1 *item 2*
        * list 1 **item 3**

    -----------------------------

        * **List 2 item 1**
        * List 2 item 2
            * List 2 item 2.1
        * **List 2 item 3**

    -----------------------------

                - List 3 item 1
                - List 3 `item 2 <https://www.novel-t.ch/>`_

| A numbered list can be created by inserting a hash symbol followed by a dot ``#.`` at the begining of the line.
| A list number can be forced and then continued by entering a number value in the first list item and beginning the next line with ``#.``

    #. First line
    #. Second line
    #. Third line

-----------------------------

    10. Start at line 10
    #. The number scheme continues
    #. With sequential numbers

.. code-block ::
  :caption: syntax for numerated list show above

        #. First line
        #. Second line
        #. Third line

        -----------------------------

        10. Start at line 10
        #. The number scheme continues
        #. With sequential numbers


Tables
******
There are four methods to create tables available in .rst

1. Outlining the table with ``=`` signs above and below headers and at the bottom of the table, the tables may be given an optional title by using the ``..table::`` directive 
    
    .. table:: Table 1)

        ================ ===================== ========================
        Field One        Field Two             Field There
        ================ ===================== ========================
        Line one F1      Line one F2           Line one F3
        Line two F1      Line two F2           Line two F3
        Line three F1    Line three F2         Line three F3
        ================ ===================== ========================

.. code-block ::
  :caption: syntax for table 1) show above

    .. table:: Table 1)

    ================ ===================== ========================
    Field One        Field Two             Field There
    ================ ===================== ========================
    Line one F1      Line one F2           Line one F3
    Line two F1      Line two F2           Line two F3
    Line three F1    Line three F2         Line three F3
    ================ ===================== ========================

-----------------------------------

2. Drawing the table, makes the markup more readable yet also more difficult to maintain. This method allows controlling of column widths and high in the markup.

    .. table:: Table 2)

        +----------------+----------+------------------------+
        | Field One      | Field    |   Field There          |
        |                | Two      |                        |
        +================+==========+========================+
        | Line one F1    | Line     | Line one F3            |
        |                | one F2   |                        |
        +----------------+----------+------------------------+
        | Line two F1    | Line     | Line two F3            |
        |                | two F2   |                        |
        +----------------+----------+------------------------+
        | Line three F1  | Line     | Line three F3          |
        |                | three F2 |                        |
        +----------------+----------+------------------------+
 

.. code-block ::
  :caption: syntax for table 2) show above

  +----------------+----------+------------------------+
  | Field One      | Field    |   Field There          |
  |                | Two      |                        |
  +================+==========+========================+
  | Line one F1    | Line     | Line one F3            |
  |                | one F2   |                        |
  +----------------+----------+------------------------+
  | Line two F1    | Line     | Line two F3            |
  |                | two F2   |                        |
  +----------------+----------+------------------------+
  | Line three F1  | Line     | Line three F3          |
  |                | three F2 |                        |
  +----------------+----------+------------------------+

-----------------------------------

3. Creating a list table with the ``.. list-table::`` directive and listing each entry designating line with an asterisk.
   
    .. list-table:: Table 3)
        :widths: 25 15 30
        :header-rows: 1

        * - Field One
          - Field Two
          - Field Three
        * - Line one F1
          - Line one F2
          - Line one F3
        * - Line two F1
          - Line two F2
          - Line two F3
        * - Line three F1
          - Line three F2
          - Line three F3

.. code-block ::
    :caption: syntax for table 3) show above

        .. list-table:: Table 3)
        :widths: 25 15 30
        :header-row: 1

        * - Field One
          - Field Two
          - Field Three
        * - Line one F1
          - Line one F2
          - Line one F3
        * - Line two F1
          - Line two F2
          - Line two F3
        * - Line three F1
          - Line three F2
          - Line three F3

-----------------------------------

4. Creating a CSV table with the ``.. csv-table::`` directive and listing each row as comma separated values. Such a lis is the easiest to maintain but is not bery ledgible in markup.

    .. csv-table:: Table 4)
       :header: Field One,Field Two,Field Three
       :widths: 25 15 30
    
       Line one F1,Line one F2,Line one F3
       Line two F1,Line two F2,Line two F3
       Line three F1,Line three F2,Line three F3

.. code-block ::
    :caption: syntax for table 4) show above

        .. csv-table:: Table 4)
        :header: Field One,Field Two,Field Three
        :widths: 25 15 30
    
        Line one F1,Line one F2,Line one F3
        Line two F1,Line two F2,Line two F3
        Line three F1,Line three F2,Line three F3