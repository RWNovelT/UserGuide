Images and Admonitions
======================

Images
******
To include an image use the ``..image::`` directive and the relative path to the image file, width, alignment and alternative text are optional properties.

::

    .. image:: /content/_images/jetdeau.jpg
        :width: 400
        :align: center

.. image:: /content/_images/jetdeau.jpg
    :width: 400
    :align: center

Admonitions
***********
Attention can be drawn to text in the user guide by including admonitions, the colour of the admonition is defined by the keyword used

.. csv-table:: Admonition Key Words
    :header: Green,Blue,Orange,Red
    :widths: 15 15 15 15

    Important,Note,Attention,Danger
    Hint,*Custom*,Caution,Error
    Tip,,Warning,

   
.. important::
    Use the ``.. <keyword>::`` syntax to create admonitions

    ::

        .. important::
        Use the ``.. <keyword>::`` syntax to create admonitions
    
----------------------------------------

With the *custom* admonition a user defined title may be used rather than the keyword as admonition title

::

    .. admonition:: 12 Steps to writing a User Manual

    1. Define Your Audience
    2. Describe the Problem
    3. Break it Down
    ...


.. admonition:: 12 Steps to writing a User Manual

    1. Define Your Audience
    2. Describe the Problem
    3. Break it Down
    4. Be Descriptive
    5. Stick to the Topic at Hand
    6. Use Diagrams, Photos and Videos
    7. Don't Use Passive Voice
    8. Avoid Using the First Person
    9. Use a Template
    10. Minimize Background Info
    11. Use Pictures to Orient Your Reader
    12. Be Simple, Not Loquacious

