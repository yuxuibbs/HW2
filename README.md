# Homework 2 - SI 364 W18

### Deadline: January 28, 2018 at 11:59 PM

## To submit

Fork and clone this repository. Make edits, following the directions, commit them all, and then push your changes to your fork. Submit the link to your fork of the repository on GitHub to the Canvas assignment.

**Do not** change any file names. Make **sure** all your file names and label text are exactly as directed for grading.

If you have completed 100% of the homework, your application should have the following routes, each of which should render the template listed here:

* `http://localhost:5000/artistform` -> `artistform.html`
* `http://localhost:5000/artistinfo` -> `artist_info.html`
* `http://localhost:5000/artistlinks` -> `artist_links.html`
* `http://localhost:5000/specific/song/<artist_name>` -> `specific_artist.html`
* `http://localhost:5000/album_entry` -> `album_entry.html`
* `http://localhost:5000/album_result` -> `album_data.html`


## Instructions

This HW assignment comes in three parts, which build on one another.

They involve: using templates, debugging templates and view function decisions in a Flask application, using WTForms, and writing form validator functions.

### Part 1 (500 points)

Edit the `SI364_HW3.py` file inside the `HW3Part1` directory to add routes to the basic Flask application that will match the templates in the `templates` subdirectory inside the `HW3Part1` folder. (**Do not** change the name of this file.)

When you are done with this part of the HW, you should have the following four routes which render each of the corresponding templates with reasonable data:

* `http://localhost:5000/artistform` -> `artistform.html`
* `http://localhost:5000/artistinfo` -> `artist_info.html`
* `http://localhost:5000/artistlinks` -> `artist_links.html`
* `http://localhost:5000/specific/song/<artist_name>` -> `specific_artist.html`

Each of the templates should be rendered with actual data when those routes are reached when the Flask application runs.

Check out the action on forms, and the end-locations of links, in order to ensure that you send the correct data to templates and that the templates get the correct data!

You may edit the templates (only slightly): you may not edit their structure, but depending on your choices in the process of making this work, you may need to edit small details. However, you should *not* need to do so in any significant way.

### Part 2

**Add a form to the application in `SI364W18_HW2.py`, using `WTForms` syntax. The class name should be `AlbumEntryForm`.**

The `AlbumEntryForm` should have the following fields:

* Text entry for an album name, whose label should be `Enter the name of an album:`
* Radio buttons with options: 1,2,3 -- representing how much the user likes the album, whose label should be: `How much do you like this album? (1 low, 3 high)`
* A submit button

**Then, add 2 more routes to the application:**

* `/album_entry`, which should render the WTForm you just created (note that there is a raw HTML form in the `artistform.html` template, but THIS should rely on your WTForms form). It should send data to a template called `album_entry.html` (see Part 3).

* `/album_result`, which should render the results of what was submitted to the `AlbumEntryForm`, [like this](www.fakelink.com). It should send data to a template called `album_data.html` (see Part 3).

### Part 3

Add templates to the application, in the provided `templates/` directory, for those two routes. You should be creating 2 template files:

* `album_entry.html`, which should use the data sent from the `/album_entry` route's view function
* `album_data.html`, which should use the data sent from the `/album_result` route's view function
