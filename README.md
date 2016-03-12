# Dist::Zilla::Plugin::Alt [![Build Status](https://secure.travis-ci.org/plicease/Dist-Zilla-Plugin-Alt.png)](http://travis-ci.org/plicease/Dist-Zilla-Plugin-Alt)

Create Alt distributions with Dist::Zilla

# SYNOPSIS

Your dist.ini:

    [GatherDir]
    [MakeMaker]
    [Alt]

# DESCRIPTION

This [Dist::Zilla](https://metacpan.org/pod/Dist::Zilla) plugin can be added to an existing dist.ini file to
turn your (or someone else's distribution into an [Alt](https://metacpan.org/pod/Alt) distribution).
What it does is:

- Modifies `Makefile.PL` or `Build.PL`

    Adds code to change the install location so that your dist won't
    be installed unless the environment variable `PERL_ALT_INSTALL`
    is set.

- Updates the no\_index meta

    So that only `.pm` files in your lib directory that are in the
    `Alt::` namespace will be indexed.

- Sets the dist name property

    If it isn't already specified in your `dist.ini` file.  It will
    determine this from the `Alt::` module in your distribution.
    If you have more than one `Alt::` module it is an error.

# CAVEATS

This plugin should appear in your `dist.ini` toward the end, or at
least after your `[GatherDir]` and `[MakeMaker]` plugins (or equivalent).

# SEE ALSO

- [Alt](https://metacpan.org/pod/Alt)
- [Dist::Zilla](https://metacpan.org/pod/Dist::Zilla)

# AUTHOR

Graham Ollis <plicease@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2016 by Graham Ollis.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
