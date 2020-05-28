# `enshrine-commits`
A command that "enshrines" an author's contributions in a new repository.

Imagine you've made contributions to a branch in an public project, and you'd like a convenient way to specifically refer to your own work in the future. It would be ideal if you could recast your work in a new repository that:

* Contained only the part of the branch in which your contributions appear.
* Squashed all intervening commits by other authors.

This script accomplishes that. Here's the help message:

    This command examines the series of commits indicated by a given ref, identifies
    the segment that contains all the contributions by a given author, and creates a
    new "shrine" repository containing only that segment, with all intervening
    commits by other authors squashed.

    This command has these forms:


        enshrine-commits --help

            Show this message and exit immediately.


        enshrine-commits <author> <original> <ref> <shrine>

            Execute the operation as indicated by the values wired into this script.

            Where:

                <author>    is the name of the author whose commits are to be
                            enshrined. Make sure to use quotes if the name includes
                            white space.

                <original>  is the absolute path to the original repository.

                <ref>       is a ref that indicates where the search for commits is
                            to begin. This can be a hash.

                <shrine>    is the path to a directory this script will create to
                            contain the shrine repository.


        enshrine-commits --to-do <author> <to-do-file-path>

            This form is for internal or testing use. It's invoked by a Git
            call-back to edit a rebase to-do file.


        enshrine-commits --message <message-file-path>

            This form is for internal or testing use. It's invoked by a Git
            call-back to edit a message for a set of squashed commits.
