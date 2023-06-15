---
layout: workshop      # DON'T CHANGE THIS.
# More detailed instructions (including how to fill these variables for an
# online workshop) are available at
# https://carpentries.github.io/workshop-template/customization/index.html
venue: "FIXME"        # brief name of the institution that hosts the workshop without address (e.g., "Euphoric State University")
address: "FIXME"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria"), videoconferencing URL, or 'online'
country: "FIXME"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes) for the institution that hosts the workshop
language: "FIXME"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for the
latitude: "45"        # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "-1"       # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "FIXME"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "FIXME"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: FIXME      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: FIXME        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["instructor one", "instructor two"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["helper one", "helper two"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["training@esciencecenter.nl"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:  # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
HEADER

Edit the values in the block above to be appropriate for your workshop.
If the value is not 'true', 'false', 'null', or a number, please use
double quotation marks around the value, unless specified otherwise.
And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}


{% comment %}
8< ============= For a workshop delete from here =============
For a workshop please delete the following block until the next dashed-line
{% endcomment %}

{% comment %}
  Assign first row in data file as info to access workshop data
{% endcomment %}
{% assign info = site.data.data[0] %}

{% comment %}
  Assign value in eventbrite file as eventbrite to access the code
{% endcomment %}
{% assign eventbrite = site.data.eventbrite %}

{% comment %}
<div class="alert alert-danger">
This is the workshop template. Delete these lines and use it to
<a href="https://carpentries.github.io/workshop-template/customization/index.html">customize</a>
your own website. If you are running a self-organized workshop or have not put
in a workshop request yet, please also fill in
<a href="{{site.amy_site}}/forms/self-organised/">this workshop request form</a>
to let us know about your workshop and our administrator may contact you if we
need any extra information.
If this is a pilot workshop for a new lesson,
remember to uncomment the `pilot_lesson_site` field in `_config.yml`
</div>
{% endcomment %}

<h2 id="general">General Information</h2>

{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
{% endcomment %}
The key objective of this workshop is to grow researchers' ability to collaborate using Git and GitLab.

{% comment %}
AUDIENCE

Explain who your audience is.  (In particular, tell readers if the
workshop is only open to people from a particular institution.
{% endcomment %}
This workshop is only open to people from Wageningen Data Competence Center

{% comment %}
DATE

This block displays the date and time.
{% endcomment %}
{% if info.humandate %}
<p id="when">
  <strong>When:</strong>
  {% if info.humantime %}
    {{info.humandate}}, {{info.humantime}}.
  {% else %}
    {{info.humandate}}.
  {% endif %}
</p>
{% endif %}

<p id="where">
  <strong>Where:</strong>
  Wageningen University, Forum building, room B0217
</p>

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong>
  {% if online == "false" %}
    Participants must bring a laptop with a
    Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on.
  {% else %}
    Participants must have access to a computer with a
    Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on.
  {% endif %}
  They should have a few specific software packages installed (listed <a href="#setup">below</a>).
</p>

<p id="prerequisites">
<strong>Prerequisites:</strong>
It is assumed that participants already write code for their research, but no expertise is required. 
Some experience in navigating file trees and editing files in a terminal session is recommended.
</p>

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact:</strong>
  Please email
  {% if site.email %}
  {% for email in site.email %}
  {% if forloop.last and site.email.size > 1 %}
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

{% comment %}
WHO CAN ATTEND?

If you would like to specify who can attend the workshop,
you can use the section below.

Move the 'endcomment' tag above the beginning of the following
<p> tag to make this section visible.

Edit the text to match who can attend the workshop. For instance:
- This workshop is open to affiliates to ABC university.
- This workshop is open to the public.
- If you are interested in attending this workshop, contact me@example.com
  for more information

<p id="who-can-attend">
    <strong>Who can attend?:</strong>
    This workshop is open to ....
</p>
{% endcomment %}

<hr/>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<h2 id="code-of-conduct">Code of Conduct</h2>

{% if info.carpentry == "ds" %}
<p>
Participants are expected to follow these guidelines:
<ul>
  <li>Use welcoming and inclusive language</li>
  <li>Be respectful of different viewpoints and experiences</li>
  <li>Gracefully accept constructive criticism</li>
  <li>Focus on what is best for the community</li>
  <li>Show courtesy and respect towards other community members</li>
</ul>
</p>
{% else %}
<p>
Everyone who participates in Carpentries activities is required to conform to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>. This document also outlines how to report an incident if needed.
</p>

<p class="text-center">
  <a href="https://goo.gl/forms/KoUfO53Za3apOuOK2">
    <button type="button" class="btn btn-info">Report a Code of Conduct Incident</button>
  </a>
</p>
<hr/>
{% endif %}


{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

https://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.

Note we also have a CodiMD (the open-source version of HackMD)
available at https://codimd.carpentries.org
{% endcomment %}
{% if page.collaborative_notes %}
<h2 id="collaborative_notes">Collaborative Notes</h2>

<p>
We will use this <a href="{{ page.collaborative_notes }}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
<hr/>
{% endif %}


{% comment %}
SCHEDULE

Show the workshop's schedule.

Small changes to the schedule can be made by modifying the
`schedule.html` found in the `_includes` folder for your
workshop type (`swc`, `lc`, or `dc`). Edit the items and
times in the table to match your plans. You may also want to
change 'Day 1' and 'Day 2' to be actual dates or days of the
week.

For larger changes, a blank template for a 4-day workshop
(useful for online teaching for instance) can be found in
`_includes/custom-schedule.html`. Add the times, and what
you will be teaching to this file. You may also want to add
rows to the table if you wish to break down the schedule
further. To use this custom schedule here, replace the block
of code below the Schedule `<h2>` header below with
`{% include custom-schedule.html %}`.
{% endcomment %}

<h2 id="syllabus">Syllabus</h2>
* Introduction to version control with Git
* Tracking changes
* Exploring history
* Ignoring things
* GitLab remotes
* Conflicts
* Centralized workflow with Git and GitLab
* Distributed workflow with Git and GitLab

<h2 id="schedule">Schedule</h2>

<div class="row">    
  <div class="col-md-6">
    <table class="table table-striped">
      <tbody>
      <tr> <td>09:00</td> <td>Welcome and icebreaker </td> </tr>
      <tr> <td>09:15</td>  <td>Introduction to version control with Git </td> </tr>
      <tr> <td>10:20</td>  <td>Coffee break</td> </tr>
      <tr> <td>10:30</td>  <td>Tracking changes and exploring history </td> </tr>
      <tr> <td>11:30</td>  <td>Coffee break</td> </tr>
      <tr> <td>11:40</td>  <td>Ignoring things, remotes, and conflicts </td> </tr>
      <tr> <td>12:30</td>  <td>Lunch</td> </tr>
      <tr> <td>13:30</td>  <td>Centralized workflow with Git and GitLab</td> </tr>
      <tr> <td>14:30</td>  <td>Coffee break</td> </tr>
      <tr> <td>14:40</td>  <td>Distributed workflow with Git and GitLab</td> </tr>
      <tr> <td>15:30</td>  <td>Coffee break</td> </tr>
      <tr> <td>15:40</td>  <td>Distributed workflow with Git and GitLab</td> </tr>
      <tr> <td>16:15</td>  <td>Wrap-up</td> </tr>
      <tr> <td>16:30</td>  <td>END</td> </tr>
    </tbody></table>
  </div>
</div>



<hr/>


{% comment %}
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>

<p>
  To participate in
  {% if info.carpentry == "swc" %}
  a Software Carpentry
  {% elsif info.carpentry == "dc" %}
  a Data Carpentry
  {% elsif info.carpentry == "lc" %}
  a Library Carpentry
  {% else %}
  this
  {% endif %}
  workshop,
  you will need access to software as described below.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

{% comment %}
These are the installation instructions for the tools used
during the workshop.
{% endcomment %}
<h3 id="computer">Computer</h3>
  <p>Participants must work on a computer with a Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) on which they have administrative privileges.</p>
  
<h3 id="software-setup">Software setup</h3>
<p>To participate in this workshop, you will need to prepare the following (if you haven’t already):</p>
<ul>
  <li>Install Shell and Git. Please refer to <a href="https://coderefinery.github.io/installation/shell-and-git/">this page</a> for installation instructions.</li>
  <li>Create a GitLab account. Please refer to <a href="https://gitlab.com/users/sign_up">this page</a> for instructions.</li>
  <li>Set up an SSH connection to GitLab. First <a href="https://docs.gitlab.com/ee/user/ssh.html#see-if-you-have-an-existing-ssh-key-pair">check if you have an ssh key</a>. Then create an SSH key pair if you don't have one, please refer to <a href="https://docs.gitlab.com/ee/user/ssh.html#generate-an-ssh-key-pair">this page</a> for instructions. Then add the SSH key to your GitLab account following <a href="https://docs.gitlab.com/ee/user/ssh.html#add-an-ssh-key-to-your-gitlab-account">these instructions</a>.</li>
  <li> You can then verify the SSH connection by running `ssh -T git@git.wur.nl` inside your terminal (for example Git Bash). The terminal will ask: 'Are you sure you want to continue connecting'. Respond with 'yes'.</li>
  <li> If you see 'Welcome to GitLab, username' you are succesfully setup! Otherwise send an email to s.vanderburg@esciencecenter.nl and s.vanrijn@esciencecenter.nl and we will help you with your setup.</li>
</ul>
