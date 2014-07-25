timber
======

A “Code Golf” challenge. Contains description &amp; test input files. Specially “Timber”, № 8, here: http://codegolf.stackexchange.com/questions/16707/9-hole-challenge
# Timber!

From [№ 8 on this post][rules] on the codegolf StackExchange:

A program that takes a single argument from the command line. The argument is a path to a file with an ASCII “building” in. Blocks with white space underneath them will fall. (Except from slashes, which stay in place if there is a stable block in the opposite direction to the way they face). If the building is structurally integral print “true” followed by a newline, otherwise return “false” followed by a newline. All non whitespace blocks are counted as being solid and other than slashes, they all fall.

You may assume that the text file is ASCII. `Perl` is the preferred language, but anything will do. Scripts need not have a “shebang” line.

Structurally safe:

    ____
    |/\|
    |  |

Not Safe:

    |__
      | 
      |

Safe version of above:

    |__
    \\| 
      |

## Test Inputs

Inside `tests` are several files with “buildings” in them. The below bit of shell will test your program against the test files, provided your working directory contains the test files.

    for TEST in *safe*
    do
        echo -n "$TEST: "
        perl [path-to-your-script] $TEST
        printf '`cat %s`\n' "$TEST"
        tr '\t\r' '  ' < $TEST
        echo '<EOF>'
        echo '―――――――――'
    done

The above as a oneliner:

    for TEST in *safe*; do echo -n "$TEST: "; [path-to-your-script] $TEST; printf '`cat %s`\n' "$TEST"; tr '\t\r' '  ' < $TEST; echo '<EOF>'; echo '―――――――――'; done


[rules]: http://codegolf.stackexchange.com/questions/16707/9-hole-challenge