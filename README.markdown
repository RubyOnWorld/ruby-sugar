Ruby.sugar <img alt='Maintenance status: Unmaintained!' src="https://img.shields.io/badge/maintained%3F-no!-red.svg?style=flat"><img src="http://elliottcable.s3.amazonaws.com/p/8x8.png"><a target="_blank" href="COPYING.markdown"><img alt='License: ISC' src="https://img.shields.io/badge/license-ISC-blue.svg?style=flat"></a><img src="http://elliottcable.s3.amazonaws.com/p/8x8.png"><a target="_blank" href="http://ell.io/IRC"><img alt='Chat: IRC on Freenode.net' src="https://img.shields.io/badge/chat-IRC-blue.svg"></a><img src="http://elliottcable.s3.amazonaws.com/p/8x8.png"><a target="_blank" href="http://twitter.com/ELLIOTTCABLE"><img alt='Follow my work on Twitter' src="https://img.shields.io/twitter/follow/ELLIOTTCABLE.svg?style=flat&label=followers&color=blue"></a>
==========
A simple first stab at a Sugar for the [Espresso text editor][espresso] for
[Ruby][] source development.

[espresso]: <http://macrabbit.com/espresso/> "The Espresso text editor, by MacRabbit"
[ruby]: <http://ruby-lang.org/> "The Ruby programming language"

Using
-----
First install any and all dependencies, listed below. The instructions for
doing so can be found on their respective homes.

Clone this project somewhere, with the following:

    git clone git://github.com/elliottcable/ruby.sugar.git ./Ruby.sugar

And then link it to your syntaxes directory:

    mkdir -p "~/Library/Application Support/Espresso/Sugars/"
    ln -s "$(pwd)/Ruby.sugar" "/Users/$(whoami)/Library/Application Support/Espresso/Sugars/"

This project is released for public usage under the terms of the very-permissive [ISC license][] (a
modern evolution of the MIT / BSD licenses); more information is available in [COPYING][].

   [ISC license]: <http://choosealicense.com/licenses/isc/> "Information about the ISC license"
   [COPYING]: <./COPYING.text>

Dependencies
------------
- [Regex.sugar](http://github.com/elliottcable/Regex.sugar "elliottcable's Regex.sugar on GitHub")

More information
----------------
You can reach me (elliottcable, the author of this project) in the Espresso
IRC channel almost 24/7:

> [##Espresso](irc://chat.freenode.net/##Espresso) on [Freenode](http://freenode.net/ "Freenode IRC network") ([open in browser](http://widget.mibbit.com/?settings=54db06d9920299f628121bb397aaa524&server=chat.freenode.net&channel=%23%23Espresso&noServerNotices=true&noServerMotd=true&autoConnect=true "Mibbit IRC gateway for ##Espresso"))

Caveats
-------
The naming conventions among Sugar developers and themers aren't really
concrete as of yet. Thus, there's a good chance that a given theme won't be
able to show all of the data about a a given file that is associated with a
given sugar as of yet. Specifically, the default theme that is currently being
distributed with the Espresso previews can't handle this Sugar - if you just
plug this Sugar into Espresso, you won't see much interesting stuff in the way
of highlighting.

This situation will improve when we come up with a set of community standards
and start adhering to them, until then, hang tight. Espresso's built-in theme
and Sugars should all be adhering to the standard by Espresso's 1.0.2 release
(by 1.1 at the latest).

TODO
----
- Syntax/Itemizers
  - All other flow control elements (if/unless???then???else, case???when,
    begin???end, all of the above plus ???rescue???ensure)
    - Make sure single line uses work as well, including rescue.
  - 'Fix' the whole method- and block-arguments thing, it's really inadequate
    right now. It really should be *describing* what arguments allow, not just
    pulling in the variable collection (for the most part).
  - Method calls, including arguments and blocks.
  - Class/module definitions
  - Operators
  - Fix the regular expression interpolation SyntaxInjection such that
    interpolations work inside other regex structures, such as groups
  - Octal/Hex, and Control/Meta string escapes.
  - Heredocs
  - Ranges
  - String-ish Symbol syntax (:'foo bar', :"gaz #{123}")
  - Strange symbols (:*, :[]=, etc)
  - Arrays, including percent-delimited syntax (Might be hard, the syntax is
    so very simple)
  - Hashes
  - Special method names that aren't simple symbols
  - `echoed shelling out`, as well as %x(the percent delimited variant)
  - More advanced heredoc support
    - Nesting, see Thomas' heredoc stuff in the Experimental Ruby tmbundle
    - Support embedded languages, especially via injection
  - Fix it so that slash-operators (division operators) are properly
    regcognized as different from regexen, where appropriate (see how `ruby`
    handles it here: http://gist.github.com/86009)
- CodeSense
  - Everything!
- Actions
  - Running Ruby scripts from within Espresso
  - Everything!
- All new 1.9 syntax
