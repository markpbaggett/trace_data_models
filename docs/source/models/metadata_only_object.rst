====================
Metadata Only Object
====================

-----
About
-----

Some objects in Digital Commons are simply metadata only records that point at external resources.

.. code-block:: text

    |-- collection
        |-- 1
            |-- metadata.xml
        |-- 2
            |-- metadata.xml

--------
Metadata
--------

The externally referenced object can be found at an xpath like /documents/document/fields/field[@name="source_fulltext_url"][@type="string"]/value


.. code-block:: xml
    :emphasize-lines: 63

    <?xml version='1.0' encoding='iso-8859-1' ?>
    <documents><document>
    <title>Data from Public Progress, Data Management and the Land Grant Mission</title>
    <publication-date>2016-01-25T00:00:00-08:00</publication-date>
    <authors>
    <author>
    <email>pfernand@utk.edu</email>
    <institution>University of Tennessee - Knoxville</institution>
    <lname>Fernandez</lname>
    <fname>Peter</fname>
    </author>
    <author>
    <email>ceaker@utk.edu</email>
    <institution>University of Tennessee - Knoxville</institution>
    <lname>Eaker</lname>
    <fname>Chris</fname>
    </author>
    <author>
    <email>shea.swauger@ucdenver.edu</email>
    <institution>University of Colorado - Denver</institution>
    <lname>Swauger</lname>
    <fname>Shea</fname>
    </author>
    <author>
    <email>miriams@vols.utk.edu</email>
    <institution>Oak Ridge Associated Universities</institution>
    <lname>Davis</lname>
    <fname>Miriam</fname>
    </author>
    </authors>
    <keywords>
    <keyword>data sharing</keyword>
    <keyword>data management</keyword>
    <keyword>land-grant university</keyword>
    <keyword>agriculture researchers</keyword>
    </keywords>
    <disciplines><discipline>Agriculture</discipline>
    </disciplines><abstract>&lt;p&gt;This article reports results from a survey about data management practices and attitudes sent to agriculture researchers and extension personnel at the University of Tennessee Institute of Agriculture (UTIA) and the College of Agricultural Sciences and Warner College of Natural Resources at Colorado State University. Results confirm agriculture researchers, like many other scientists, continue to exhibit data management practices that fall short of generally accepted best practices. In addition, librarians, and others seeking to influence future behavior, may be informed by our finding of a relationship between the land-grant mission and researchers’ data management practices.&lt;/p&gt;</abstract>
    <coverpage-url>http://trace.tennessee.edu/utk_datasets/1</coverpage-url>
    <label>1</label>
    <document-type>data</document-type>
    <type>article</type>
    <articleid>1000</articleid>
    <submission-date>2016-01-25T09:47:05-08:00</submission-date>
    <publication-title>Data Sets</publication-title>
    <context-key>8044773</context-key>
    <submission-path>utk_datasets/1</submission-path>
    <fields>
    <field name="custom_citation" type="string">
    <value>Fernandez, P., Eaker, C., Swauger, S., &amp; Davis, M., &quot;Data from Public Progress, Data Management and the Land Grant Mission&quot; (2016). &lt;a href=&quot;http://dx.doi.org/10.7290/V7KS6PHQ&quot; target=&quot;_blank&quot;&gt;http://dx.doi.org/10.7290/V7KS6PHQ&lt;/a&gt;</value>
    </field>
    <field name="doi" type="string">
    <value>10.7290/V7KS6PHQ</value>
    </field>
    <field name="embargo_date" type="date">
    <value>2016-01-25T00:00:00-08:00</value>
    </field>
    <field name="publication_date" type="date">
    <value>2016-01-25T00:00:00-08:00</value>
    </field>
    <field name="source_fulltext_url" type="string">
    <value>http://dx.doi.org/10.7290/V7KS6PHQ</value>
    </field>
    </fields>
    </document>
    </documents>