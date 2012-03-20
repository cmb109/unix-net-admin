##########
Homework 4
##########

:Author: Doug Stanley <dstanle@uakron.edu>
:Date: 3/20/2012
:Due Date: **3/22/2012**


Assignment
==========

For this assignment, you will send me a "spoofed" email. That is, an email
that appears to be coming from some one else.

To do this, you will use telnet or netcat to type raw SMTP commands and
manually communicate with an email server. I also want you to fake the
X-Mailer and X-Sender headers.

As for whom you will be spoofing, I'd like you to select something that's
obviously fake, but not me. Don't send me email from myself. Use something
else, like Abraham Lincoln or Kermit The Frog. Make sure and use the From mail
header so that you can specify a fake name AND fake email address.

In the body of the email, you will specify the following:

    Homework #4 submission for YOUR NAME <your_Email@provider.tld>

Also, make sure to specify a subject line header. Be creative. Also, feel
free to fake any other header.


What to Submit
--------------

* An email sent using telnet or netcat

* The following email headers should be specified:

  * X-Mailer:

  * X-Sender:

  * From:

  * To:

  * Subject:

* Specify an obviously fake name and email address in the From and X-Sender
  header.

* Specify a made up mail user agent, or just specify telnet for X-Mailer

* Make sure the body of the email has the appropriate information.

Questions
---------

Any questions, comments, or concerns about this assignment, please email me
(dstanle@uakron.edu) or see me before or after class.


Submission
----------

Please submit your homework as a plain ASCII text file, preferably formatted
in reStructuredText markup (see syllabus for references to rst syntax). Please
**DO NOT** submit any microsoft word documents!! Plain ASCII text only (UTF8 
plain text is ok too)! If you're stuck with windows, the old notepad program
will work. There are many others as well.

To submit, upload your plain text file to the dropbox on springboard labeled for
this homework assignment.

References
----------

* http://rst.ninjs.org/

  * An online restructured text editor/parser you can use.

* http://www.dokuwiki.org/dokuwiki

  * The home page of the Dokuwiki wiki project.
