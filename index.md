---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "cp"    # what kind of Carpentry (must be either "lc" or "dc" or "swc").  
                      # Be sure to update the Carpentry type in _config.yml as well.  
venue: "CHTC - HTMap Workshop"        # brief name of host site without address (e.g., "Euphoric State University")
address: "Orchard View Room, Discovery Building, 330 N. Orchard St."      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latlng: "43.0729163,-89.4102733"       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use https://www.latlong.net/)
humandate: "September 16, 2019"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "2:00pm - 5:00pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2019-09-16      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2019-09-16        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Josh Karpel"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Christina Koch", "Lauren Michael"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["ckoch5@wisc.edu"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %}
For a workshop please delete the following block
{% endcomment %}
<div class="alert alert-info" style="font-size: 150%;">
If you are a researcher using CHTC's high throughput computing (HTC) system to submit and run jobs, we welcome you to attend this 
  workshop on the HTMap package. HTMap is a tool that can help you:
 <ul>
   <li>use Python to submit jobs</li>
   <li>run Python code in CHTC</li>
  </ul>

You do not have to use Python to attend! If you have some programming experience and use the HTC system, you are welcome to come.

<h2><a href="https://docs.google.com/forms/d/e/1FAIpQLSf7L3kX_BklFyk1JhO8GlymaxsjpQrdQ_D8gvEwbx2qJqpAXw/viewform?usp=sf_link">Register Here</a></h2>
</div>

{% comment %}
EVENTBRITE

This block includes the Eventbrite registration widget if
'eventbrite' has been set in the header.  You can delete it if you
are not using Eventbrite, or leave it in, since it will not be
displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 id="general">General Information</h2>

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> If you want to follow along, see the setup instructions (listed <a href="#setup">below</a>).
</p>

{% comment %}

ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
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

<div class="row">
  <div class="col-md-6">
    <h3>Schedule</h3>
    <table class="table table-striped">
      <tr><td>2:00-2:40</td> <td>Intro and Demonstration</td></tr>
      <tr><td>2:40-3:10</td><td>Questions and Break</td></tr>
      <tr><td>3:10-4:00</td><td>Extended Example</td></tr>
			<tr> <td>4:00-5:00</td> <td>Optional Question Time with Josh</td> </tr>
    </table>
  </div>
</div>

<h3>Notes</h3>

<p>During the workshop, we will put notes and resources into this Google Doc: <a href="https://docs.google.com/document/d/1TxvPoePfi5BB-fuqB29GibRDlblotyRJLSc9iAnYY-k/edit?usp=sharing">Google Doc for Notes</a> 
  </p>

<hr/>


<h2 id="setup">Setup</h2>

### Installing Python and HTMap

This guide will walk you through installing a personal (i.e., not "system") Python on a CHTC submit machine. Once you have a personal Python, you can install any packages you'd like, including HTMap.

In particular, we will install a self-contained Python distribution called Anaconda. The particular flavor we will install is called Miniconda: it is a bare-bones Python, with just a few packages pre-installed. It comes with the conda package manager in addition to the standard pip.

**WARNING**: Following these steps will install Python in such a way that it
**prevents your ability to access the system Python**. If you rely on the system
Python in your own work, contact us so we can work out a solution.

#### Log into your submit machine

First, you should log into your submit machine by whatever your normal login mechanism is (probably something like SSH or Putty).

Go to your home directory.

#### Download the Miniconda installer

We can download the Miniconda installer from the command line. Run

```bash
$ wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```
(remember, you don't type the `$`, it's just indicating the command line prompt).

You should see some output from `wget`.
Once `wget` finishes downloading the file, run `ls -l` to check that you have a
file named `Miniconda3-latest-Linux-x86_64.sh` in your home directory.

#### Run the Miniconda installer

Start the installer by running

```bash
$ bash Miniconda3-latest-Linux-x86_64.sh
```

Follow the instructions.
- The default installation location is `/<your-home-directory>/miniconda3`.
  This is fine; you may customize it if you wish.
- You **do** want the installer to initialize Miniconda3 by running conda init.
  This is not the default; you must answer `yes`.
  
#### Check that the Miniconda installation worked

The installer has put the files in the right place, but we can't actually use
them yet.
Do **one** of the following:
1. Run `source ~/.bashrc`
1. Log off of the submit machine, then log back in.
Once you have done one of the above, there are a few tests we can do to make
sure the installation worked correctly.

First, run `conda --help`.
You should see a message like 
```
(base) [karpel@jupyter0000 ~]$ conda --help
usage: conda [-h] [-V] command ...

conda is a tool for managing and deploying applications, environments and packages.
```
`conda` is the Anaconda package manager. You can use it to install packages
distributed by Anaconda, which include various Python packages like `numpy` or
`matplotlib` that you could also install via `pip` (Python's own built-in package
manager), but also include a wide variety of other tools.

Next, run these two commands:
```
$ which python
$ which pip
```
You should get output like this:
```bash
(base) [karpel@jupyter0000 ~]$ which python
~/miniconda3/bin/python
(base) [karpel@jupyter0000 ~]$ which pip
~/miniconda3/bin/pip
```
The paths should point into the installation directory you
gave to the installer above (`~/miniconda3` being the default).

#### Install HTMap

HTMap can be installed via `pip`.
Run
```bash
$ pip install htmap
```
You should see output from `pip`.

#### Check that HTMap works

To check that HTMap installed correctly, begin a Python session by running `python`.
You are now in a Python "REPL" (read-eval-print-loop) and can run Python commands.
For now, just run the following command in the REPL:

```
>>> import htmap; print(htmap.version())
```
You should see output like `HTMap version 0.4.3` (numbers may not match).
If you did, HTMap is successfully installed, and you're ready for the workshop!
