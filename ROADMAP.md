# Roadmap

Priorities: 

* [x] in-depth reference documentation of all major functionality (`authenticate`, `Account`, `CoreQuery`, `Report`) in docstrings
* [ ] fix bug in date handling of start/stop datetimes (see also: "extract date handling functionality")
* [ ] expose reference documentation by turning it into HTML with [python-inspector](https://github.com/debrouwere/python-inspector/) and pandoc.
* [ ] query subcommand in the CLI

Can wait: 

* [x] caching of queries when using the lazy-loading shortcuts
* [x] suggestions for similar keys when a KeyError is raised on a column
* [x] support for the Real Time Reporting API
* [x] clean up column serialization code
* [ ] nicer and more powerful `CoreQuery#segment` interface, perhaps using `query#users` and `query#sessions`, with a signature like `*segments, scope=None)` (where scope would refer to the inner scope, which can be more precise than the segment scope) and then use the `or`, `and` and `any` functions as well as methods on Column objects to fill out the remaining functionality
* [ ] nicer filtering interface
* [ ] drop into a Python shell, automatically log in and expose `accounts`
* [ ] wrap errors into ones that are easier to understand and test against in try/except blocks.
* [ ] example report-to-html template
* [ ] unit tests for the authentication functionality
* [ ] clean up some of the object initializations (__init__ should be clean, from_api can be dirty)
* [ ] the ability to pluck rows and/or metrics in blueprints (e.g. it often happens that you query for a single metric in aggregate, and in that case the data you want back is `query.rows[0].mymetric`, that is, a single number, not a list of dictionaries)

As part of supporting / other modules: 

* [ ] extract date handling functionality (ultimately, this is generic and needed in different contexts) -- perhaps make it a part of `hrange`
* [ ] utilities for humanized output (ratios, cognitively rounded numbers, etc.)
* [ ] verbose mode for blueprints (fetching query x...)
* [ ] better diagnostics / google-analytics-specific errors rather than generic Python ones
