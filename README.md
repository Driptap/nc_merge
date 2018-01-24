# nc_merge
Interface to merge multiple NC files in a specific order. This helps create auto printable 3d print files.

A single html file, load it into a browser.
Relies on some CDN content, internet access is required.

### Incrementing values in the NC files

*Then read this:*

The files increment `y` between 10 and 210 in increments of 10 and `x` between 10 and 210 in increments of 10 for each increment of `y`.
You need to place Mustache delimiters at every place you want the incremented number to appear, ie:

```
;Purge
G1 X{{x_value}} Y{{y_value}} F4000 ;move X/Y to min endstops
G1 Z0.3 F9000 ;Move the platform down 1mm
```

Notice the `{{x_value}}`, yea thats the one that gets turned into the number that you want incremented.

1. Name the files you want incremented `increment_file_n.gcode` - where n is the number of the file. For example: `increment_file_1.gcode, increment_file_2.gcode`

1. Upload your start and end files

1. Arrange the files in the interface with the *start* file at the *top* of the file arranging panel and the *end* file at the *end* of the panel.

1. You can only place incremental files in-between the start and the end, any other files will be ignored.

1. Click the `Make and increment file` button, do a little dance and it'll download the gcode file all wrapped up.

If you have problems, prayer to the sky and hope.



`WTFPL – Do What the Fuck You Want to Public License.`
