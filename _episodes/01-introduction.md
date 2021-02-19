---
title: "Introduction"
teaching: 10
exercises: 0
questions:
- "None yet"
objectives:
- "Explain what we will cover in this workshop"
keypoints:
- "Something interesting about data science"
---

This is the introductory page.

## The crux of learning

Here I can put any infomation about what the course will cover.

![Forking Repositories]({{ page.root }}/fig/forking.svg)

Maybe include some images as well...

![Repository Links]({{ page.root }}/fig/repository-links.svg)

## GitHub Pages

If I want to have code-like text in the main text body I can do this `python take-over-the-world.py`

> ## Teaching Tools
>
> I can outline here some tools that may be useful, such as:
> [Jupyter Notebook][jupyter],
> Wow somehow carpentries knows how to link to jupyter without actually specifying the link. 
> I need to figure out how to include an actual link
{: .callout}

## Code presentation

I will present code as follows:

~~~
bash ./find-bsm-physics.sh
~~~
{: .language-bash}

~~~
python get-nobel-prize.py
~~~
{: .language-python}

~~~
Traceback (most recent call last):
  File "./python_assert.py", line 5, in <module>
    assert nobel_prize == True
AssertionError
~~~
{: .output}

and inserts the values of those variables into the page when formatting it.
The three dashes that start the header *must* be the first three characters in the file:
even a single space before them will make [Jekyll][jekyll] ignore the file.

The header's content must be formatted as [YAML][yaml],
and may contain Booleans, numbers, character strings, lists, and dictionaries of name/value pairs.
Values from the header are referred to in the page as `page.variable`.
For example,
this page:

~~~
---
name: Science
---
{% raw %}Today we are going to study {{page.name}}.{% endraw %}
~~~
{: .source}

is translated into:

~~~
<html>
  <body>
    <p>Today we are going to study Science.</p>
  </body>
</html>
~~~
{: .html}

> ## Back in the Day...
>
> The previous version of our template did not rely on Jekyll,
> but instead required authors to build HTML on their desktops
> and commit that to the lesson repository's `gh-pages` branch.
> This allowed us to use whatever mix of tools we wanted for creating HTML (e.g., [Pandoc][pandoc]),
> but complicated the common case for the sake of uncommon cases,
> and didn't model the workflow we want learners to use.
{: .callout}

## Configuration

[Jekyll][jekyll] also reads values from a configuration file called `_config.yml`,
which are referred to in pages as `site.variable`.
The [lesson template]({{ site.template_repo }}) does *not* include `_config.yml`,
since each lesson will change some of its value,
which would result in merge collisions each time the lesson was updated from the template.
Instead,
the [template]({{ site.template_repo }}) contains a script called `bin/lesson_initialize.py`
which should be run *once* to create an initial `_config.yml` file
(and a few other files as well).
The author should then edit the values in the top half of the file.

## Collections

If several Markdown files are stored in a directory whose name begins with an underscore,
[Jekyll][jekyll] creates a [collection][jekyll-collection] for them.
We rely on this for both lesson episodes (stored in `_episodes`)
and extra files (stored in `_extras`).
For example,
putting the extra files in `_extras` allows us to populate the "Extras" menu pulldown automatically.
To clarify what will appear where,
we store files that appear directly in the navigation bar
in the root directory of the lesson.
[The next episode]({{ page.root }}/03-organization/) describes these files.

{% include links.md %}
