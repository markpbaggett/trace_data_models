=========
A Journal
=========

-----
About
-----

This document describes the structure of our journals in Digital Commons.

There is no structural metadata.  An object is organized simply according to directory structure as seen below:


.. code-block:: text

    |-- Journal Title
        |-- volume number
            |-- issue number
                |-- article
                    |-- a_pdf.pdf
                    |-- metadata.xml
                |-- article
                    |-- a_pdf.pdf
                    |-- metadata.xml
            |-- issue number
                |-- article
                    |-- a_pdf.pdf
                    |-- metadata.xml
        |-- volume number
            |-- issue number
                |-- article
                    |-- a_pdf.pdf
                    |-- metadata.xml

--------
Metadata
--------

As you can see in the image above, there is no metadata about the journal or issue.  All metadata is article level only.

.. code-block:: xml

    <?xml version='1.0' encoding='iso-8859-1' ?>
    <documents><document>
    <title>The Roles of Invariance and Analogy in the Linear Design of Stravinsky’s “Musick to heare”</title>
    <publication-date>2008-01-01T00:00:00-08:00</publication-date>
    <authors>
    <author>
    <email>trace@utk.edu</email>
    <institution>College-Conservatory of Music, University of Cincinnati</institution>
    <lname>Berry</lname>
    <fname>David Carson</fname>
    </author>
    </authors>
    <disciplines><discipline>Music</discipline>
    </disciplines><abstract>&lt;p&gt;A list of contributing author biographies&lt;/p&gt;</abstract>
    <coverpage-url>http://trace.tennessee.edu/gamut/vol1/iss1/1</coverpage-url>
    <fulltext-url>http://trace.tennessee.edu/cgi/viewcontent.cgi?article=1002&amp;amp;context=gamut&amp;amp;unstamped=1</fulltext-url>
    <label>1</label>
    <document-type>article</document-type>
    <type>article</type>
    <articleid>1002</articleid>
    <submission-date>2010-12-07T09:27:31-08:00</submission-date>
    <publication-title>Gamut: Online Journal of the Music Theory Society of the Mid-Atlantic</publication-title>
    <context-key>1674511</context-key>
    <submission-path>gamut/vol1/iss1/1</submission-path>
    <fields>
    <field name="embargo_date" type="date">
    <value>2010-12-07T00:00:00-08:00</value>
    </field>
    <field name="peer_reviewed" type="boolean">
    <value>true</value>
    </field>
    <field name="publication_date" type="date">
    <value>2008-01-01T00:00:00-08:00</value>
    </field>
    <field name="short_title" type="string">
    <value>Invariance and Analogy in Stravinsky’s “Musick to heare”</value>
    </field>
    </fields>
    </document>
    </documents>
