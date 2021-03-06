.. _element-pub-date:

<pub-date>
==========

Mandatory attributes:

  1. ``@date-type``

+------------------------------+--------------------+
| Appears in                   | Frequency          |
+==============================+====================+
| :ref:`element-article-meta`  | one or more times  |
+------------------------------+--------------------+


The publication date of an article and it's issue uses the element ``<pub-date>`` which may contain the elements :ref:`element-day`, :ref:`element-month`, :ref:`element-season` and must contain :ref:`element-year`. ``<pub-date>`` may be accompanied by the attribute ``@publication-format`` and ``@date-type`` where:

``@publication-format`` can be **ppub** if there is a publication date for a print version of the article, and **epub** to identify the electronic publication date.

``@date-type`` can be **collection** or **pub** where:

    * **pub** represents the article publication date in it's print and/or electronic versions,

        .. note::
            Only complete dates are accepted wich means the pub-date element must have the elements :ref:`element-day`, :ref:`element-month` and :ref:`element-year`. The element :ref:`element-season` it not accepted here.

    * **collection** represents the publication date defined by the journal periodicity.

        .. note::

            It is not necessary to have the attribute ``@publication-format`` when the attribute ``@date-type`` has the value **collection**. See the examples bellow.

For Érudit PS will be mandatory to have at least one ``<pub-date>`` element inside :ref:`element-article-meta` with the publication date defined by the journal periodicity and expressed by the attribute ``@date-type=collection``. The article and journal publishing dates may differs for many reasons.

.. note::

    The use of the attribute ``@pub-type`` is deprecated in :term:`NISO JATS Journal Archiving DTD` specifications, and consequently it is not accepted in :term:`Érudit PS`.

Examples:

    * :ref:`pubdate-example-1`
    * :ref:`pubdate-example-2`


.. _pubdate-example-1:

Example of ``<pub-date>`` of a document in a print and electronic versions:
---------------------------------------------------------------------------

.. code-block:: xml

    ...
    <article-meta>
        ...
        <pub-date publication-format="epub" date-type="pub">
            <day>10</day>
            <month>01</month>
            <year>2014</year>
        </pub-date>
        <pub-date publication-format="ppub" date-type="pub">
            <day>21</day>
            <month>02</month>
            <year>2014</year>
        </pub-date>
        <pub-date date-type="collection">
            <season>Jan-Feb</season>
            <year>2014</year>
        </pub-date>
        ...
    </article-meta>
    ...


.. _pubdate-example-2:

Example of ``<pub-date>`` of a document available only in electronic version:
-----------------------------------------------------------------------------

.. code-block:: xml

    ...
    <article-meta>
        ...
        <pub-date publication-format="epub" date-type="pub">
            <day>17</day>
            <month>03</month>
            <year>2014</year>
        </pub-date>
        <pub-date date-type="collection">
            <year>2015</year>
        </pub-date>
        ...
    </article-meta>
    ...


.. {"reviewed_on": "2019-10-11", "by": "mathieu.pigeon@erudit.org"}
