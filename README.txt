MAKEWHATIS

This is a modified version of the MAKEWHATIS program as distributed
by Apple.  It was modified to follow symbolic links to manual page
directories.  This particular version was originally written by John
Rochester.  That version (just preceding this one) was itself inspired
by the original version by Wolfram Schneider (which was written in
Perl).

= Bug fixes

Several type mismatches were fixed, but one major bug was also fixed
(where the handle to the opening of a gz-compressed file was being
placed into an incorrect type).

= Changes from the previous version

Unlike the previous version, this version loves to follow symbolic
links.  This ability to follow symbolic (or hard) links allows it
to operate in an environment where actual MAN pages are held
separately from the distribution directory (often in a writable
filesystem) while the software distribution itself is held in a
read-only filesystem.  Several other (more legacy) software
distributions also routinely used symbolic links for the 'man'
subdirectoy located just under the head of the software distribution
head.  By not following those symbolic links, the associated manual
pages were not made available to the |apropos(1)| utility.

= Security concerns

There really are no security concerns since |makewhatis(1m)| is
never (and should never) be run with 'root' permissions.  Doing so
is completely unnecessay and foolhardly as well.  The UNIX® and
UNIX-like systems all have the ability to create mulitple users and
specialized users (along with specialized groups) to facilitate any
security arrangement an administrator may want.  Following (or not
following) symbolic links is not a security threat in a properly
conifigured and administered system.

= Other enhancements

There is one additional option provided now.  It is the 'Q' (capital
Q character).  This option suppresses most of the most annoying
error (or warning) messages when a directory is either not available
or not writable.

