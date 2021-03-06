# NAME

dicepass - generate strong, pronouncable, rememberable passwords

# SYNOPSIS

    dicepass -m 4 -l 10 -n 3 -s "." -d "/usr/share/dict/words"

Possible parameters are

| Parameter                   | Description                         |
|-----------------------------|-------------------------------------|
| --min/-m _integer_          | The minimum length for words to use |
| --max/-l _integer_          | The maximum length for words to use |
| --num/-n _integer_          | The number of words to use          |
| --separator/-s _string_     | The string to use to separate words |
| --dictionary/-d _filename_  | The dictionary to draw words from   |
| --help/-h                   | Print this synopsis                 |
| --pod/--man/-p              | Print the full documentation        |
| --test/-t                   | Run the self-test                   |

All parameters are optional, with the following default values:

| Parameter       |                         |
|-----------------|-------------------------|
| --min/-m        | 4                       |
| --max/-l        | 10                      |
| --num/-n        | 3                       |
| --separator/-s  | "."                     |
| --dictionary/-d | "/usr/share/dict/words" |

# DESCRIPTION

dicepass generates strong passwords you can remember by stringing
together dictionary words.  It balances security with convenience to
ensure you, the user, will use good passwords.

Simply run the program from a command line and it will give you a
pretty good password.  Don't like it?  Run it again.

Some example passwords generated by dicepass:

    laceless.ours.magneoptic
    against.Cogswellia.mila
    sobering.rukh.bromomania
    gundy.consonance.tonetic


# FAQ

## Development

### I want to help!

Great!  We're on [Github](https://github.com/schwern/dicepass).  Send
us an [issue](https://github.com/schwern/dicepass/issues) and consider
[making a contribution](https://help.github.com/articles/fork-a-repo).

### I have an idea to make dicepass even better!

Great!  [Tell us about it](https://github.com/schwern/dicepass/issues)!

### I want to help, but I don't know how to use Git.

That's ok, you can [edit this file in your browser](https://github.com/schwern/dicepass/edit/master/dicepass) and Github will take care of the rest.

### I found a bug!

Great!  Well... not great... but [tell us about it](https://github.com/schwern/dicepass/issues)!

### I'm not sure it's a bug...

[Tell us about it](https://github.com/schwern/dicepass/issues) anyway!

Don't wait until you have a solution, don't worry if you don't have
all the information, tell us as soon as you have the problem.  Any
problem, concern, improvement, feature, annoyance, typo... we want to
hear from you.  Really!  Nothing can be improved unless we know about
it.

## Security

### Aren't dictionary words insecure?

Yes, if your password is just a dictionary word.  Even with easy to
guess replacements (the letter o to 0, for example) they can be easily
brute forced.  The standard OS X dictionary of 200,000 words means only 200,000
passwords need to be checked, multipled by each common letter
replacement trick.  Nothing for modern computers.

But with each word added, the problem becomes exponentially harder to
brute force.  Picking three words at random from a 200,000 word
dictionary leads to 8,000,000,000,000,000 possibilities which is
pretty good.



### Why use this instead of a random string?

A bunch of random characters is effectively impossible to crack, but
security is not just about numbers.  The biggest security hole is
_you_ the human.

A good security system must be both secure _and_ convenient.  If it
is not convenient, the users will simply circumvent it.  If your
passwords are all impossible difficult to remember gobblty gook you
will use weaker passwords, or start reusing passwords.



### Why use this instead of a browser based app?

Short version, you could be giving your password to an attacker.

Passwords are typically not directly stored, even encrypted.  It is
"hashed", converted to a bunch of apparently random characters but in
such a way that only your password will produce that same bunch of
characters and the process cannot be reversed.  This is also known as
a "checksum".

This is why a well run organization cannot tell you
what your password was if you forget it, they actually do not know.
When you log in, the password you enter is hashed and compared against
the hash in their database.  If they match, they know you entered the
right password without knowing what your password is.

Attackers pass around huge lists of common passwords and common
variations.  First, they will steal the hashed password file from an
organization.  Then they will try everything on their list and see
what matches.  If your password gets on that list, it doesn't matter
how clever or random it is, it doesn't matter if they don't know your
username, it is compromised.

A clever attacker would set up a web site to generate strong passwords
for users.  Every password they hand out would go straight onto their
list, your password would be pre-compromised.  Even if the site is
setup with the best of intentions, your connection to that site may be
insecure, or the site may have been quietly compromised, or your
browser could be compromised.

It's a simple risk to avoid.



### The NSA has computers that can hack a million Gibsons!

Yes, with enough time and money you can brute force this system in a
not unreasonable amount of time.  Quite honestly, you're not likely
worth the effort.  If you _are_ worth the effort, you shouldn't be
picking your passwords using a program you downloaded off the
internet.

In addition, if a security organization wants to access your accounts,
having a stronger password is unlikely to save you.  There are a
hundred faster and cheaper ways to crack your account than brute
forcing your password.



# COPYRIGHT AND LICNESE

Copyright 2012 by Michael G Schwern <schwern@pobox.com>.

This program is free software; you can redistribute it and/or
modify it under the same terms as Perl itself.

See [http://dev.perl.org/licenses/](http://dev.perl.org/licenses/)
