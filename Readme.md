# jekyll-course-site -- Host syllabuses on GitHub Pages with Ease!

## Getting Started

To get started with your first syllabus website, you need to [fork this repository](https://help.github.com/en/github/getting-started-with-github/fork-a-repo#fork-an-example-repository).

Once your fork has been created, you need to [set the publishing source for GitHub Pages](https://help.github.com/en/github/working-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site). You will want to set it to the `master` branch.

Once those two steps are done, you can edit `index.md` to add content to your syllabus. Also see ["Editing the Schedule"](#editing-the-schedule) for instructions on setting daily course activities and configuring other aspects of your course.

## Editing the Schedule

The only file you need to actually edit is `_data/schedule.yml`. It contains all of the information for the schedule grid and has comments explaining how to use it.

### YAML Contents

The file contains a series of keys, optional ones are marked as such. A couple of notes, dates must be written in the form `YYYY-MM-DD` ('1924-03-21' or '2000-12-14') and you must use two digits for months and days, even if they are less than 10. Days of the week must be written in lower case ('monday' or 'saturday').

The keys are as follows:

* `start` -- a string containing the date on which the semester starts.
* `end` -- a string containing the date on which the semester ends.
* `meets` -- a sequence (list) containing days of the week on which your course meets.
* `classes` -- a sequence (list) of strings or blocks that describe the activities of each class in order. Each item in the sequence will be formatted using Markdown.
* `holidays` -- *optional* a sequence (list) of mappings (hashes) that define holidays. Each entry has two keys:
	* `date` -- a string containing the date of the holiday.
	* `name` -- a string containing the name or description of the holiday.
* `redefined` -- *optional* a sequence (list) of mappings (hashes) that define redefined days. Each entry has two keys:
	* `date` -- a string containing the date being redefined.
	* `is_a` -- a day of the week string containing what the redefined day functions as.
* `weeks` -- *optional* a mapping (hash) of strings. Each key in the mapping must be a week number represented as a string (`1` becomes `"1"`, etc.) that maps to the title for a given week of instruction.
* `units` -- *optional* a sequence (list) of mappings (hashes) that defines information about any units your course is divided into. Each entry has three keys:
	* `start` -- a number representing the week of the semester on which a given unit starts.
	* `title` -- *optional* a string providing a unit title.
	* `description` -- *optional* a string or block containing a description of the unit. Will be formatted as Markdown.

Read more about YAML here: [YAML](https://yaml.org/)

## Hosting Multiple Syllabuses on GitHub

While you forked your first syllabus from this repository, if you want to use this site for multiple syllabuses, you will have to fork your own fork, which requires some command line usage.

[Here are some instructions that can help with that](https://deanmalone.net/post/how-to-fork-your-own-repo-on-github/).