MultiMedia
==========

uses the "raw" directive that introduces a potential security hole it indicates non-reStructuredText data that is to be passed untouched to the document
to use the directive the conf.py file setting raw_enabled needs to be activated

Youtube can be inserted (should be create a GTS YouTube channel)

..
    .. raw:: html

        <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; height: auto;">
            <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 50%; height: 50%;"></iframe>
        </div>


.. raw:: html

   <iframe width="560" height="315" src="https://www.youtube.com/embed/kPL71DZt9GY"></iframe>

.. raw:: html

   <iframe width="560" height="315" src="https://www.youtube.com/embed/kPL71DZt9GY" title="YouTube video player" 
   frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

It is also possible to embed mp4 files

Second try

.. video:: content/_images/test.mp4
   :width: 500
   :height: 300
   :autoplay:
   :nocontrols:







