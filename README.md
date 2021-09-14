# ATAG Quick Reference as JSON
This is meant to be be a mix of the portability of [WCAG as JSON](https://github.com/tenon-io/wcag-as-json) and usefulness of [How to Meet WCAG (Quickref Reference)](https://www.w3.org/WAI/WCAG21/quickref/), but for ATAG.

## Important Links
See the [ATAG Quick Reference](https://andrewnordlund.github.io/atag/atagscs.html) in action.

[ATAG Quick Reference GitHub repo](https://github.com/andrewnordlund/atag/)


## Structure

The structure of the JSON file closely mirrors the ATAG Standard itself:

* There are 2 Parts of ATAG
* Each Part has Principles of ATAG
* Each Principle has Guidelines
* Each Guideline has Success Criteria

In this JSON format the Success Criteria have been broken down further:

* Special Cases - additional considerations on the applicability of the SC. There are 3 types of special cases
  * `exception` - the special case, if satisfied, creates an exception whereby the SC does not apply
  * `at_least_one` - at least one of the special cases must apply 
  * `all_true` - all of the special cases must apply 
* Notes - any other notes that accompany the Success Criterion

A full ATAG SC Entry looks like this:

```
{
	"ref_id" : "A.4.2.1",
	"title" : "Describe Accessibility Features",
	"description" : "For each authoring tool feature that is used to meet Part A of ATAG 2.0, at least one of the following is true:",
	"level" : "A",
	"url_fragment" : "sc_a421",
	"notes": [{"content" : "The accessibility of the documentation is covered by Guideline A.1.1 and Guideline A.1.2."}],
	"special_cases" : 
	[
		{
		       	"type": "at_least_one",
       			"title": "Described in the Documentation",
	       		"description": "Use of the feature is explained in the authoring tool's documentation;"
		},
		{
		      	"type": "at_least_one",
			"title": "Described in the Interface",
			"description": "Use of the feature is explained in the authoring tool user interface;"
		},
		{
			"type": "at_least_one",
			"title": "Platform Service",
			"description": "The feature is a service provided by an underlying platform;"
		},
		{
			"type": "at_least_one",
			"title": "Not Used by Authors",
			"description": "The feature is not used directly by authors (e.g. passing information to a platform accessibility service)."
		}
	]
},
```

## License
The JSON formatted document has an MIT license.

This software or document includes material copied from or derived from Authoring Tool Accessibility Guidelines (ATAG) 2.0 https://www.w3.org/TR/ATAG20/. Copyright © 2015 W3C® (MIT, ERCIM, Keio, Beihang).
