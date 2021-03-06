Org Dashboard provides a visual summary of progress on projects and
tasks.

For example, if an org file (known by `org-agenda-files`) contains
the following:

    * Project: Better Health
    :PROPERTIES:
    :CATEGORY: health
    :END:
    ** Milestones
    *** [66%] run 10 km/week
    **** TODO learn proper warmup
    **** DONE look for a jogging partner
    **** DONE run 10 minutes on monday
    
    * Project: Super Widget
    :PROPERTIES:
    :CATEGORY: widget
    :END:
    ** Milestones
    *** [1/6] release 0.1
    **** DONE git import
    **** TODO create github project
    **** TODO add readme
    **** TODO publish

Then <kbd>M-x org-dashboard-display</kbd> generates the following report and
displays it in a new buffer:

    health                run 10 km/week [██████████████████████           ]  66%
    widget                   0.1 release [██████                           ]  18%

A dynamic block form is also supported. Writing the following in an
org file and then running `org-dblock-update`, or placing the
cursor on the first line of the block and then typing <kbd>C-c C-c</kbd>,
will insert the same report shown above into the block:

    #+BEGIN: block-dashboard
    #+END:

## Notes

Labels link back to the trees where they were found.

The color of the progress bar is (naively, for now) chosen based on
the progress value, from dark red to bright green.

The first column displays categories. You can turn this off by
customizing the `org-dashboard-display-category` option. Note that,
if not set per-tree through a property or per-file through a
keyword, the category defaults to the file name without extension.

## Related work

This module was inspired by Zach Peter's [A Dashboard for your
Life](http://thehelpfulhacker.net/2014/07/19/a-dashboard-for-your-life-a-minimal-goal-tracker-using-org-mode-go-and-git/).


