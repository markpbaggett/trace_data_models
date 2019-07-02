=================================
ETD that started in Trace Deposit
=================================

-----
About
-----

Beginning in December 2017, ETDs were approved by the graduate school in `Trace Deposit <https://trace.utk.edu>`_.
The ETDs here were approved in this system and later migrated to our `production Trace instance <https://trace.tennesse.edu>`_.
Because of this, these objects have a complicated model where pertinent parts of the ETD are maintained in two
systems.  This document describes this in great detail with emphasis on what's important, why, and how to relate the
objects in each system.

----------
Data Model
----------

.. image:: ../images/etd_from_islandora.png
   :width: 1200
   :alt: Image of the Data Model of an ETD that started in Islandora

ETDs that started in Trace Deposit have pieces that are pertinent to the migration in 3 separate systems:

* `Trace Deposit <https://trace.utk.edu>`_
* `Trace <https://trace.tennesse.edu>`_
* `GitHub <https://github.com/utkdigitalinitiatives/trace_deposit_htaccess_config>`_

The objects in each system are represented by the objects in blue above.  The bitstreams that are pertinent to the
migration are displayed in green.

A description of the overall object in each system is detailed in the following sections.

-----------------------------------------------
GitHub Relationships and Redirection Repository
-----------------------------------------------

An ETD in Trace is maintained in more than one system.  This is due to our `public interace system <https://trace.teneessee.edu>`_
being unable to support all parts of an originating ETD.  Because of this, a `GitHub repository <https://github.com/utkdigitalinitiatives/trace_deposit_htaccess_config>`_
is maintained that shows the relationship between the object in `Digital Commons <https://trace.tennessee.edu>`_  and
`Islandora <https://trace.utk.edu>`_.

The key piece of the repo is a file called `migrated_etds.config <https://github.com/utkdigitalinitiatives/trace_deposit_htaccess_config/blob/master/migrated_etds.config>`_.
This file is an Apache config file that lives in `Trace Deposit <https://trace.utk.edu>` and redirects access to the
object to the same object in digital commons.  Because of this, the path listed directly after Redirect 301 implies that
https://trace.utk.edu/ should be prepended to the address.

Here is a sample set of redirected objects between the two systems:

.. code-block:: text

    Redirect 301 /islandora/object/utk.ir.td:133 http://trace.tennessee.edu/utk_gradthes/4983
    Redirect 301 /islandora/object/utk.ir.td:283 http://trace.tennessee.edu/utk_gradthes/4984
    Redirect 301 /islandora/object/utk.ir.td:299 http://trace.tennessee.edu/utk_gradthes/4985
    Redirect 301 /islandora/object/utk.ir.td:417 http://trace.tennessee.edu/utk_gradthes/4986
    Redirect 301 /islandora/object/utk.ir.td:419 http://trace.tennessee.edu/utk_gradthes/4987
    Redirect 301 /islandora/object/utk.ir.td:104 http://trace.tennessee.edu/utk_gradthes/4988
    Redirect 301 /islandora/object/utk.ir.td:230 http://trace.tennessee.edu/utk_gradthes/4989
    Redirect 301 /islandora/object/utk.ir.td:68 http://trace.tennessee.edu/utk_gradthes/4990
    Redirect 301 /islandora/object/utk.ir.td:139 http://trace.tennessee.edu/utk_gradthes/4991
    Redirect 301 /islandora/object/utk.ir.td:134 https://trace.tennessee.edu/utk_gradthes/4992/

----------------------------------------------------
The Preservation Object in Trace Deposit (Islandora)
----------------------------------------------------

We consider the preservation object to be made up of most of bitstreams that are part of the object in
`Trace Deposit <https://trace.utk.edu>`_.  This section describes each of the bitstreams that are pertinent to migration
with examples.

PDF (the ETD accepted by the graduate school)
=============

Each ETD is contained in a bitstream called PDF.

The ETD includes a cover page followed by a recommendation for acceptance from the graduate school.

Here is an `example ETD <http://trace.utk.edu/islandora/object/utk.ir.td:136/datastream/PDF>`_.

MODS (Descriptive Metadata)
===========================

Each ETD has a descriptive metadata record produced by the student and the graduate school.  Here is a sample:

.. code-block:: xml

    <?xml version="1.0" encoding="UTF-8"?>
    <mods:mods xmlns:mods="http://www.loc.gov/mods/v3" xmlns="http://www.loc.gov/mods/v3" xmlns:etd="http://www.ndltd.org/standards/metadata/etdms/1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xs="http://www.w3.org/2001/XMLSchema" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd" version="3.5">
      <mods:titleInfo>
        <mods:title>Design and Implementation of EEG-Based Brain Computer Interfaces for Neuroprosthetics and Neurorehabilitation</mods:title>
      </mods:titleInfo>
      <mods:name valueURI="http://orcid.org/0000-0001-8975-8210" type="personal" authority="orcid" authorityURI="http://id.loc.gov/vocabulary/identifiers/orcid.html">
        <mods:namePart type="given">Reza</mods:namePart>
        <mods:namePart type="family">Abiri</mods:namePart>
        <mods:role>
          <mods:roleTerm authority="marcrelator" type="text" valueURI="http://id.loc.gov/vocabulary/relators/aut">Author</mods:roleTerm>
        </mods:role>
      </mods:name>
      <mods:originInfo>
        <mods:dateCreated encoding="w3cdtf">2018-09-19T16:03:31-04:00</mods:dateCreated>
        <mods:dateIssued keyDate="yes" encoding="edtf">2017-12</mods:dateIssued>
      </mods:originInfo>
      <mods:recordInfo displayLabel="Submission">
        <mods:recordCreationDate encoding="w3cdtf">2017-10-04T19:51:22-04:00</mods:recordCreationDate>
        <mods:recordChangeDate keyDate="yes" encoding="w3cdtf">2017-10-04T19:51:22-04:00</mods:recordChangeDate>
        <mods:recordChangeDate keyDate="yes" encoding="w3cdtf">2017-10-31T13:00:22-04:00</mods:recordChangeDate>
        <mods:recordChangeDate keyDate="yes" encoding="w3cdtf">2017-11-14T15:10:23-05:00</mods:recordChangeDate>
        <mods:recordChangeDate keyDate="yes" encoding="w3cdtf">2018-09-19T16:03:31-04:00</mods:recordChangeDate>
      </mods:recordInfo>
      <mods:extension>
        <etd:degree>
          <etd:level>Doctoral (includes post-doctoral)</etd:level>
          <etd:name>Doctor of Philosophy</etd:name>
          <etd:discipline>Mechanical Engineering</etd:discipline>
          <etd:grantor>University of Tennessee</etd:grantor>
        </etd:degree>
      </mods:extension>
      <mods:name type="personal">
        <mods:displayForm>Xiaopeng Zhao</mods:displayForm>
        <mods:role>
          <mods:roleTerm authority="marcrelator" type="text" valueURI="http://id.loc.gov/vocabulary/relators/ths">Thesis advisor</mods:roleTerm>
        </mods:role>
        <mods:namePart type="given">Xiaopeng</mods:namePart>
        <mods:namePart type="family">Zhao</mods:namePart>
      </mods:name>
      <mods:name>
        <mods:displayForm/>
        <mods:role>
          <mods:roleTerm type="text">Committee member</mods:roleTerm>
        </mods:role>
        <mods:namePart type="given">Anahita</mods:namePart>
        <mods:namePart type="family">Khojandi</mods:namePart>
        <mods:namePart type="termsOfAddress"/>
      </mods:name>
      <mods:typeOfResource>text</mods:typeOfResource>
      <mods:genre authority="lcgft" valueURI="http://id.loc.gov/authorities/genreForms/gf2014026039">Academic theses</mods:genre>
      <mods:genre authority="coar" valueURI="http://purl.org/coar/resource_type/c_db06">doctoral thesis</mods:genre>
      <mods:genre authority="COAR" valueURI="http://purl.org/coar/resource_type/c_46ec">thesis</mods:genre>
      <mods:language>
        <mods:languageTerm authority="iso639-2b" type="code">eng</mods:languageTerm>
      </mods:language>
      <mods:abstract>Brain Computer Interface (BCI) technology motivates interesting and promising results in forward/feedback control consistent with human intention. It holds great promise for advancements in patient care and applications to neuroprosthetics and neurorehabilitation. Here, as forward control in BCI neuroprosthetics, a fundamental testbed for controlling a computer cursor was designed using noninvasive Electroencephalography (EEG) technology. In order to reduce the training time for subjects, a new paradigm called “Imagined Body Kinematics” was adopted in designed experimental protocols. Twenty-eight subjects were trained (about 10 minutes) to perform the cursor control task. The subjects were asked to answer a pre- and a post-questionnaire before and after the experiment, respectively. Several confounding variables were investigated to evaluate their correlation with subjects’ performance in training and control task. Thereafter, the developed cursor control platform was applied in Brain Machine Interfaces to control different robotic devices to confirm the potential application of investigated paradigm in neuroprosthetics control. As another interesting area in BCI, a new EEG-based BCI platform was developed to evaluate attentional states in six subjects (as pilot study) and in thirty-eight subjects (as extended study) for feedback control in neurorehabilitation. For the first time, the features from whole brain were employed in two-class classification of attentional states. By introducing a new experimental paradigm for stimuli and neurofeedback, it was discussed how the platform could have the potential application in attention training of people with cognitive deficit.</mods:abstract>
      <mods:note displayLabel="Submitted Comment"/>
      <mods:relatedItem type="series">
        <mods:titleInfo>
          <mods:title>Graduate Theses and Dissertations</mods:title>
        </mods:titleInfo>
      </mods:relatedItem>
      <mods:note displayLabel="Keywords Submitted by Author"/>
      <mods:accessCondition type="local rights statement">Unless otherwise noted, (c) 2017 The Author(s).</mods:accessCondition>
      <mods:note displayLabel="Copyright holder">author</mods:note>
      <mods:physicalDescription>
        <mods:note displayLabel="Publication Status">PUBLISHED</mods:note>
      </mods:physicalDescription>
      <mods:name>
        <mods:displayForm/>
        <mods:namePart type="given">Jindong</mods:namePart>
        <mods:namePart type="family">Tan</mods:namePart>
        <mods:namePart type="termsOfAddress"/>
        <mods:role>
          <mods:roleTerm type="text">Committee member</mods:roleTerm>
        </mods:role>
      </mods:name>
      <mods:name>
        <mods:displayForm/>
        <mods:namePart type="given">Eric R.</mods:namePart>
        <mods:namePart type="family">Wade</mods:namePart>
        <mods:namePart type="termsOfAddress"/>
        <mods:role>
          <mods:roleTerm type="text">Committee member</mods:roleTerm>
        </mods:role>
      </mods:name>
    </mods:mods>

MESSAGES (Messaging from the graduate school to the student)
============================================================

Each ETD has a MESSAGES file that contains all correspondence from the graduate school to the student prior to the ETD
being accepted.

.. code-block:: text

    -------------------------------------------------FROM: Thesis Manager
    TO: rabiri@vols.utk.edu  CC: thesis@utk.edu
    Revise and resubmit: DESIGN AND IMPLEMENTATION OF EEG-BASED BRAIN COMPUTER INTERFACES FOR NEUROREHABILITATION AND NEUROPROSTHETICS
    Date: 2017-10-25 14:07:33
    Hi Reza,

    I have reviewed your dissertation for formatting. Please make the changes listed below and see the instructions at the end of this message for how to upload a revised version. Please upload your next draft as soon as you fix all of the below issues (which should be done as soon as possible).

    Please note that I need the signed, hard copy of your Dissertation Approval Form (http://gradschool.utk.edu/forms/thesis-dissertation-approval.shtml) delivered to the Graduate School office absolutely no later than November 17 if you are meeting the regular fall 2017 deadline. THIS IS DIFFERENT FROM THE PASS/FAIL FORM THAT IS DUE TO YOUR GRADUATION SPECIALIST BY NOVEMBER 17. Photocopied forms or forms submitted electronically will not be accepted -- the paper hard copy with original signatures from ALL committee members is what needs to be submitted. You should bring the form to your defense and turn it in to me as soon as possible afterward.

    After I have this form, and after you have uploaded the final version of your dissertation (that meets all of our formatting requirements), I will be able to mark your dissertation as "accepted." When I mark it as accepted, you will receive an email. You must have that email confirmation BEFORE November 17 at 5PM EST. At that point, once I have marked it as accepted, you will not be able to make any further changes or upload any new versions of your file (even if a typo or other error is found) – so make sure you are completely done with all final edits before informing me that you have submitted your final version and want it to be accepted.

    Additionally, you will need to complete the Survey of Earned Doctorate (http://gradschool.utk.edu/thesesdissertations/submission/survey-of-earned-doctorates/). This can be done at any time, before or after you turn in your final document and approval form. However, it must also be done before November 17, as I cannot accept your dissertation until I have confirmation that you completed this. Working on the below formatting issues should of course take precedence, but I strongly recommend getting this survey out of the way after you have submitted your next draft.

    If you are not meeting the regular fall deadline, including if you are meeting the 2nd fall deadline, you can view all future deadline dates here: http://gradschool.utk.edu/graduation/graduation-deadlines/. The requirements for all deadlines are the same, so only the actual final deadline date will change -- the rest of this email will apply no matter when you graduate.

    Formatting notes:

    -Please note that title case (where the first letter of every word except "and", "of", and "for" is capitalized) is recommended and preferred over all caps for the title on your title page.

    -The middle section of your title page should look exactly like this (wording, spacing/layout, and capitalization), except it should of course still be centered:

    A Dissertation Presented for the
    Doctor of Philosophy
    Degree
    The University of Tennessee, Knoxville

    So just move the word "Degree" down to its own (3rd) line.

    -Change the date on your title page from October 2017 to December 2017. It needs to be the month and year of graduation, regardless of when you submit or defend.

    -Each chapter should only have one heading, and should only be numbered once. So only "Chapter One: Introduction" should be the heading at the top of page 1 -- then "This chapter will cover..." should appear below that one heading. You should not have "CHAPTER One" AND "1 Chapter one: Introduction" above this line. Do the same for the other chapters as well.

    -All tables/figures must be referenced by number in the text. Then, you have three options for table/figure placement (and you can either choose to use the same option for every table/figure, or a combination of 2-3 options throughout the document):

    1. On the same page that the table/figure is first referred to (this can only be used if all tables/figures on the page take up less than half of the page, and all non-caption text takes up more than half of the page)

    2. On an otherwise blank page directly after the page on which the table/figure is first referred to (this CAN be used if the table/figure takes up less than half of the page, but MUST be used if it takes up more than half -- unless you are using #3)

    3. In a labeled Appendix after the References section

    Please note that tables and figures are not considered part of the flow of the text, but rather are treated as artifacts that support the text. For this reason, it is not acceptable to “break” the text after a table/figure is first mentioned and leave white space on a page in order to wait to show a table or figure. Instead, simply continue the text (even if it is a new paragraph or new section). The only time there should be a significant amount of white space on a text page is when it is the last page of the chapter.

    Also, there must be 1-2 blank lines separating each table/figure from other text or tables/figures on the same page (above and below). The caption is considered part of the table/figure, and so while the caption should be as close to the table/figure as possible, there should also be 1-2 blank lines between the caption and any other text, tables, or figures on the same page.

    If you need further clarification about table/figure requirements, please see pages 11-16 of the Guide to Preparation of ETDs: http://gradschool.utk.edu/documents/2016/03/guide-to-thesesdissertations.pdf

    -If a table/figure isn't so large that it cannot fit on one page, the *entire* table/figure (caption included) must be on the same page. Currently, for example, Table 2.2 is split between two pages (25-26) when it could easily fit on one page.

    For Figure 2.15, it looks like it may be able to fit on the same page if you make the images SLIGHTLY smaller.

    However, if a figure is so large that the entire figure (title/legend included) cannot fit on one page while being contained in the margins, the title/legend must go on an otherwise blank page directly BEFORE the figure (even though figure captions normally go beneath the figure). In these cases, the title should be the only thing on its page, and the figure should be the only thing on its page(s) -- except for "Figure #. Continued", which must be beneath the figure on each page it appears.

    So, using Figure 2.15 as an example: "Fig. 2.15. Chronological history of...from [164])." should be on an otherwise blank page all by itself. Then, if both images will fit on the same page, they should both be on 2nd page, with "Fig. 2.15. continued" below part b. However, if they cannot fit on the same page, part a should be on the next/2nd page, and part b should be on the next/3rd page (and both images should have "Fig. 2.15. continued" below them). Do this for any other figures that span 2+ pages as well.

    -Text should always start at the very top of the page. Most of your pages are fine, but some -- like pages 30, 36, 45, etc. -- have a blank line or two at the very top of the page. Make sure to check for this issue AFTER making all other edits, as changing even one word can make this issue appear (or disappear) on another page.

    If you need help seeing where this issue occurs, you can turn on the Pilcrow button (¶) in the Home tab in MS Word. Doing this will show a ¶ wherever there is a blank line -- if this is at the very top of the page, above the first row of text, remove it so that text is on the very first line.

    -All tables must be typed directly into the document, not pasted in as images (like Table 4.1 was). Text inside tables must be in the same font as the rest of the document's text -- although it can be a smaller font size than normal text if necessary.

    -Although it is a major division, the bibliography is not a chapter and therefore should not be labeled as such nor should it be assigned a number. So instead of "7 Bibliography", the heading on page 103 should just be "Bibliography". Fix this both in the heading itself, and on the table of contents.

    -Your list of references should be preceded by a title page. This is an otherwise blank page with the title (Bibliography) at the top or center of the page. This page is assigned a page number, and your table of contents should refer to this page number. Your actual references should start at the top of the page directly after this title page.

    -Headings/subheadings/text of equal value should be formatted consistently throughout the document. Formatting includes all attributes that can possibly be applied to text (bold vs. not bold, centered vs. left-aligned, same font size, etc.). It also includes spacing (above/below headings/subheadings, between each paragraph, and between each line of text).

    Here are some examples of formatting inconsistencies I noticed:

    *The first line of your chapter titles (such as "Chapter One" on page 1) is a much larger font size than normal text, and is centered. The second line of your chapter titles (such as "1 Chapter one: Introduction" on page 1) are only a slightly larger font size than normal text and is left-aligned. The bibliography heading is left-aligned and the same font size as normal text, but is in all caps. And the vita heading is centered and a slightly larger font size than normal text, but is in all caps as well.

    It doesn't matter how you format these headings (although, as stated above, you shouldn't have two separate headings for your chapters) -- but all 8 of them are major division headings, and therefore you should pick one overall style and apply it to all 8 of these headings. Make sure they are formatted consistently in the headings themselves AS WELL AS on the table of contents.

    *Most of your first-level subheadings (such as "2.5 Closed-Loop EEG-Based BCI" on page 26) are a slightly larger font size than normal text. However, in a few (such as "2.6 Gaps and Research Objectives" on page 34), the section number ("2.6" in this example) is a slightly larger font size than normal text, but the section title ("Gaps and Research Objectives") is the same font size as normal text.

    It doesn't matter how you format them, but all first-level subheadings (1.1-1.4, 2.1-2.7, 3.1-3.5, etc.) must be formatted consistently throughout all chapters.

    *Most of your second-level subheadings (such as "2.5.1 Computer Cursor as a Virtual Neuroprosthetic Device") are bold and italicized, but others (such as "2.5.2 Neurofeedback for Neurorehabilitation" on page 30) are only bold but not italicized. And a few (such as "3.3.1 Training Phase Evaluation" on page 43) have the section tittle italicized, but the section number is not.

    It doesn't matter how you format them, but all second-level subheadings (2.3.1-2.3.9, 2.5.1-2.5.2, 3.2.1-3.2.4, etc.) must be formatted consistently throughout all chapters.

    *Most of your figure captions have a period after the figure number.  However, a few (such as the captions for Figures 4.1 and 4.2 on page 64) have a colon after the figure number, and a few others (such as the caption for Figure 3.18 on page 55) have neither a colon nor a chapter after the figure number.

    It doesn't matter whether you have a colon, period, or neither after your figure numbers, but all figure captions throughout all chapters must be consistent. Make sure they are formatted consistently in the captions themselves AS WELL AS on the list of figures.

    Again, these are just some examples. Make sure you identify all "groups" in your document, pick a style for each group, and then check all members of each group to ensure there are no formatting inconsistencies. Examples of groups include each level of headings/subheadings, table captions, figure captions, equations, etc.

    ***********************************************

    In order to submit a new version, please log in to Trace (www.trace.utk.edu) with your netID and password. On your account page, click the title of this submission, then click the "manage files" tab on the resulting page. Click "replace" next to your PDF, and then you will be able to upload a new version. Make sure to send me an email any time you have uploaded a new version so I know to review it. IF YOU DO NOT SEND THIS EMAIL, YOUR DRAFT MAY NOT BE REVIEWED.

    ***********************************************

    If you have any questions, please email me at
    thesis@utk.edu.

    Thanks,

    Sarah Stone
    Thesis/Dissertation Consultant
    The Graduate School
    111 Student Services Bldg
    1331 Circle Park
    Knoxville, TN 37996-0211
    thesis@utk.edu
    -------------------------------------------------FROM: Thesis Manager
    TO: rabiri@vols.utk.edu  CC: thesis@utk.edu
    Revise and resubmit: Design and Implementation of EEG-Based Brain Computer Interfaces for Neuroprosthetics and Neurorehabilitation
    Date: 2017-11-09 14:05:41
    Hi Reza,

    I have reviewed your dissertation for formatting. Please make the changes listed below and see the instructions at the end of this message for how to upload a revised version. Please upload your next draft as soon as you fix all of the below issues (which should be done as soon as possible).

    I have your approval form and SED certificate of completion, so all I need now is your final draft that is free of formatting issues (uploaded to Trace ***in PDF format*** as a revision to your original submission, which is the same way you uploaded this draft), and an email (to thesis@utk.edu) confirming that you are completely done and want me to accept your dissertation. When it is accepted, it will be locked and you will be unable to edit it further or upload any new drafts, **even if you notice a typo or other error**, so please be sure you are completely done before giving me permission to accept your dissertation.

    The deadline for having your dissertation accepted is Thursday, November 17 at 5PM EST if you are meeting the regular fall 2017 deadline -- but I can accept it shortly after I receive the two above things (final PDF that is free of formatting issues, and email confirmation that you are completely done) from you. When it has been accepted, you will get an email confirmation. You must have this email confirmation BEFORE 5:00 on November 17 in order to be eligible to graduate this semester.

    Formatting notes:

    -Headings/subheadings/text of equal value should be formatted consistently throughout the document. Formatting includes all attributes that can possibly be applied to text (bold vs. not bold, centered vs. left-aligned, same font size, etc.). It also includes spacing (above/below headings/subheadings, between each paragraph, and between each line of text).

    Currently the dedication, acknowledgements, and abstract headings are a slightly larger font size than the table of contents, list of tables, and list of figures headings. Either size is fine, but all 6 should be the same size.

    -Each chapter should only be numbered once -- so the first heading should either be "1 Introduction", or "Chapter One: Introduction" (but not "1 Chapter One: Introduction"). However you decide to fix this heading, make sure to do the same for Chapters 2-6.

    -If a table/figure shares a page with text, it should only be above or below complete paragraphs. Currently, for example, Figure 4.14 is in the middle of a sentence/paragraph on page 80 -- "These join angles is are an example of a run" is above it and "with optimized steps of control and it took about one minute to complete the manipulation task." is below it.

    It looks like most of your other pages that have both tables/figures nd text don't have this issue, but make sure this is still the case after making all final edits.

    -Text should always start at the very top of the page. Most of your pages are fine, but some -- like pages 89, 103, etc. -- have a blank line or two at the very top of the page. Make sure to check for this issue AFTER making all other edits, as changing even one word can make this issue appear (or disappear) on another page.

    If you need help seeing where this issue occurs, you can turn on the Pilcrow button (¶) in the Home tab in MS Word. Doing this will show a ¶ wherever there is a blank line -- if this is at the very top of the page, above the first row of text, remove it so that text is on the very first line.

    -Only one font should be used throughout the entire document. The only exception to this rule is text INSIDE an image that obviously cannot be changed, and mathematical equations. But all text typed into the document (including preliminary pages, headings/subheadings, table/figure captions, text inside tables, references, appendix material, etc.) must be in the same font.

    Currently, for example, the text inside Table 5.7 and Figure 5.6 is a different font than the rest of the document's text. If the figure is an image, it can be a different font -- but because the text inside Figure 5.6 was typed directly into the document, it should be in the same font. Text inside tables (and typed-in figures) can be a smaller/larger font size than normal text, but it should still be in the same actual font.

    Fix these, then make sure to check the rest of the document to ensure there are no other font inconsistencies elsewhere.

    ***********************************************

    In order to submit a new draft of your dissertation, please log in to Trace (https://trace.utk.edu) with your netID and password. After you have logged in, click "My account" on the top right corner of the page. On your account page, you should click the title of this submission, then click the "manage files" tab on the resulting page. Click "replace" next to your PDF, and then you will be able to upload a new file. Make sure to send me an email (thesis@utk.edu) any time you have uploaded a new version so I know to review it. IF YOU DO NOT SEND THIS EMAIL, YOUR DRAFT MAY NOT BE REVIEWED.

    If you need to change your title, abstract, or any other information you entered when making your first submission, follow the same instructions as listed above (go to your account, click the title of this submission, and click "manage files"). Then, instead of clicking "replace" next to your PDF, click "edit" next to the submission data and abstract field. If you ONLY edit this metadata, you do not need to notify me.

    ***********************************************

    If you have any questions, please email me at
    thesis@utk.edu.

    Thanks,

    Sarah Stone
    Thesis/Dissertation Consultant
    The Graduate School
    111 Student Services Bldg
    1331 Circle Park
    Knoxville, TN 37996-0211
    thesis@utk.edu
    -------------------------------------------------FROM: Thesis Manager
    TO: rabiri@vols.utk.edu  CC: thesis@utk.edu
    Congratulations! "Design and Implementation of EEG-Based Brain Computer Interfaces for Neuroprosthetics and Neurorehabilitation" has been accepted
    Date: 2017-11-14 15:12:47
    Dear Reza Abiri,

    I have accepted your dissertation on behalf of the Graduate School. Congratulations!

    This email message is notification to your graduation specialist (Sylvia Miller) that you have completed the dissertation portion of your degree requirements.

    If you have questions about all other (non-dissertation) graduation requirements, please contact Sylvia (sylvia@utk.edu).

    I wish you luck with your future endeavors.

    Best wishes,

    Sarah Stone
    Thesis/Dissertation Consultant
    The Graduate School
    111 Student Services Bldg
    1331 Circle Park
    Knoxville, TN 37996-0211
    thesis@utk.edu

Supplemental Files (SUPPL_0 - SUPPL_n)
======================================

Each ETD has zero to **n** supplemental files. The files are named SUPPL_# starting at zero.

**NEED TO DESCRIBE HOW TO DETERMINE IF THE SUPPLEMENTAL FILE EXISTS**

-------------------------------------
The Object in Trace (Digital Commons)
-------------------------------------

For objects that started in Islandora, we only consider two elements to be pertinent to the migration:

* an embargo date
* a withdrawn date

Embargo Dates
=============

Since the embargo of an ETD can be extended at any time at the request of the author, the embargo is managed in Digital
Commons after it is initially published.  The embargo (if one exists) is available in Digital Commons in the metadata at
/documents/document/fields/field[@name="embargo date"]/value.

.. code-block:: xml
    :emphasize-lines: 50-52

    <?xml version='1.0' encoding='iso-8859-1' ?>
    <documents><document>
    <title>Live Ghosts</title>
    <publication-date>2010-05-01T00:00:00-07:00</publication-date>
    <authors>
    <author>
    <email>pireland@utk.edu</email>
    <institution>University of Tennessee - Knoxville</institution>
    <lname>Ireland</lname>
    <fname>Patricia</fname>
    <mname>Anne</mname>
    </author>
    </authors>
    <keywords>
    <keyword>Creative writing</keyword>
    <keyword>Southern</keyword>
    <keyword>Patty Ireland</keyword>
    <keyword>Knoxville TN</keyword>
    <keyword>Master&#39;s thesis</keyword>
    <keyword>Short stories</keyword>
    </keywords>
    <disciplines><discipline>Arts and Humanities</discipline>
    <discipline>English Language and Literature</discipline>
    </disciplines><abstract>&lt;p&gt;In Live Ghosts, Patricia (Patty) Ireland offers a gathering of short stories based upon real life characters she encountered while growing up in the South. Exploring the diversity, complexity and moral ambiguity of those we might normally perceive as being stereotypically “Southern,” Ireland’s tales encompass a variety of time periods, settings, and characters, including: a modern-day family struggling to reconcile the reality of death, interracial lovers in the early 1950’s who are descended from masters and slaves, and an insane killer locked for life in a mental institution of the 1990’s. Live Ghosts is infused with tales of fear, love, loss, regret, madness, and self discovery, themes intrinsic not only to Southern culture, but to the universal vulnerability in all of us.&lt;/p&gt;</abstract>
    <coverpage-url>http://trace.tennessee.edu/utk_gradthes/634</coverpage-url>
    <fulltext-url>http://trace.tennessee.edu/cgi/viewcontent.cgi?article=1631&amp;amp;context=utk_gradthes&amp;amp;unstamped=1</fulltext-url>
    <label>634</label>
    <document-type>thesis</document-type>
    <type>article</type>
    <articleid>1631</articleid>
    <submission-date>2010-04-02T13:02:57-07:00</submission-date>
    <native-url>http://trace.tennessee.edu/context/utk_gradthes/article/1631/type/native/viewcontent</native-url>
    <publication-title>Masters Theses</publication-title>
    <context-key>1260069</context-key>
    <submission-path>utk_gradthes/634</submission-path>
    <fields>
    <field name="advisor1" type="string">
    <value>Michael Knight</value>
    </field>
    <field name="advisor2" type="string" list="true">
    <value>Marilyn Kallet</value>
    <value>Allen Wier</value>
    </field>
    <field name="degree_name" type="string">
    <value>Master of Arts</value>
    </field>
    <field name="department" type="string">
    <value>English</value>
    </field>
    <field name="embargo_date" type="date">
    <value>2019-12-01T00:00:00-08:00</value>
    </field>
    <field name="publication_date" type="date">
    <value>2010-05-01T00:00:00-07:00</value>
    </field>
    </fields>
    </document>
    </documents>

Withdrawn Status
================

If an ETD that was published had to be taken down for any reason, a unique XPATH is added to the descriptive metadata
signifying the object was withdrawn from the system on a given date.  While the date is not important to us, the fact
that the object should be restricted from all users besides admins is.  These objects should be migrated but should not
be public in the system.  The withdrawn status can be found at /documents/document/withdrawn.

.. code-block:: xml
    :emphasize-lines: 27

    <?xml version='1.0' encoding='iso-8859-1' ?>
    <documents><document>
    <title>Modeling of Unreinforced Construction Joints in Plain Concrete Using GT STRUDL</title>
    <publication-date>2005-05-01T00:00:00-07:00</publication-date>
    <authors>
    <author>
    <institution>University of Tennessee - Knoxville</institution>
    <lname>Carroll</lname>
    <fname>James</fname>
    <mname>Christopher</mname>
    </author>
    </authors>
    <disciplines><discipline>Civil Engineering</discipline>
    </disciplines><abstract>&lt;p&gt;The purpose of this study was to develop a method to predict the behavior of unreinforced concrete construction joints using the computer program GT STRUDL. Two three-dimensional finite element models of a navigation lock wall were constructed. The wall was subjected to eccentric prestress forces, which brought about concern for lift-off within the lock wall.&lt;/p&gt;
    &lt;p&gt;Eleven loading combinations were evaluated, which were created from seven independent loading conditions. Stresses for each loading combination were compared to nominal strength values as detennined by ACI 318-02, Chapter 22, for plain concrete. Results show the stresses to be acceptable throughout the wall and displacements to be negligible; thus, the structural integrity of the lock wall is adequate for continued operation.&lt;/p&gt;
    &lt;p&gt;A detailed description of the study including the computer modeling, results, and recommendations are discussed in this thesis.&lt;/p&gt;</abstract>
    <coverpage-url>http://trace.tennessee.edu/utk_gradthes/586</coverpage-url>
    <fulltext-url>http://trace.tennessee.edu/cgi/viewcontent.cgi?article=1734&amp;amp;context=utk_gradthes&amp;amp;unstamped=1</fulltext-url>
    <label>586</label>
    <document-type>thesis</document-type>
    <type>article</type>
    <articleid>1734</articleid>
    <submission-date>2010-06-03T09:29:55-07:00</submission-date>
    <publication-title>Masters Theses</publication-title>
    <context-key>1342358</context-key>
    <withdrawn>2011-06-02</withdrawn>
    <submission-path>utk_gradthes/586</submission-path>
    <fields>
    <field name="advisor1" type="string">
    <value>Edwin G. Burdette</value>
    </field>
    <field name="advisor2" type="string" list="true">
    <value>Richard M. Bennett</value>
    <value>J. Hal Deatherage</value>
    </field>
    <field name="degree_name" type="string">
    <value>Master of Science</value>
    </field>
    <field name="department" type="string">
    <value>Civil Engineering</value>
    </field>
    <field name="embargo_date" type="date">
    <value>2010-06-03T00:00:00-07:00</value>
    </field>
    <field name="publication_date" type="date">
    <value>2005-05-01T00:00:00-07:00</value>
    </field>
    </fields>
    </document>
    </documents>
