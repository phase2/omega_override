Author: David Coffey
Sponsored by Phase2 Technology
http://www.phase2technology.com

https://github.com/phase2/omega_override

An issue many people have had with Omega and Delta layouts is the inability
to stack regions within a zone. Word on the street is a better solution for
this is coming in Omega 4, but currently this is an issue for many Omega
users, and has been an issue for us here at Phase2 on a few projects now.

To get around this in the past, we have used preprocess hooks to force
regions into zones. (Technique described here: http://drupal.org/node/1230110)
This approach was less than ideal for a number of reasons. It broke off from
what the user saw in the zone configuration UI, it was difficult to maintain
or make changes to, and it didn’t allow us to take advantage of Delta templates.

The main issue is that Omega will not allow you to add regions to a zone if
the sum of the number of columns in all the regions in that zone exceed the
maximum number of columns allowed in that zone. This is a quick and dirty
little module to disable the form validation that checks for this.

Use this at your own risk! Omega validates this for a reason, and if you start
cramming more regions into a zone than will fit, you might start to see some
funky or unexpected layouts. But if you understand how CSS floats work, you can
use this to your advantage.

If I get time in the future, I’d like to add the ability for this to also
disable the auto-expansion of region widths when the surrounding regions are
empty. This would complete power to the themer to control region placement.
Also it would be nice to add these as checkboxes in the settings form so this
can be easily enabled/disabled for Delta templates.