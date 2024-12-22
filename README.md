# Dist::Zilla::Plugin::Alt ![linux](https://github.com/uperl/Dist-Zilla-Plugin-Alt/workflows/linux/badge.svg) ![macos](https://github.com/uperl/Dist-Zilla-Plugin-Alt/workflows/macos/badge.svg) ![windows](https://github.com/uperl/Dist-Zilla-Plugin-Alt/workflows/windows/badge.svg)

Create Alt distributions with Dist::Zilla

# SYNOPSIS

Your dist.ini:

```
[GatherDir]
[MakeMaker]
[Alt]
```

# DESCRIPTION

This [Dist::Zilla](https://metacpan.org/pod/Dist::Zilla) plugin can be added to an existing dist.ini file to
turn your (or someone else's) distribution into an [Alt](https://metacpan.org/pod/Alt) distribution.
What it does is:

- Modifies `Makefile.PL` or `Build.PL`

    Adds code to change the install location so that your dist won't
    be installed unless the environment variable `PERL_ALT_INSTALL`
    is set to `OVERWRITE`.

    \[version 0.08\]

    Will also add a diagnostic warning that will display when
    `Makefile.PL` or `Build.PL` is run, with a link to [Alt](https://metacpan.org/pod/Alt) to help
    de-confuse those unfamiliar with the [Alt](https://metacpan.org/pod/Alt) namespace.

- Updates the no\_index meta

    So that only `.pm` files in your lib directory that are in the
    `Alt::` namespace will be indexed.

- Sets the dist name property

    If the name isn't already set in your `dist.ini` by some other
    means, this plugin will set the name based on the Alt module.
    If you have more than one Alt module (which would be unusual)
    then it is an error unless you set the name by some other means.

# CAVEATS

This plugin should appear in your `dist.ini` toward the end, or at
least after your `[GatherDir]` and `[MakeMaker]` plugins (or equivalent).

# SEE ALSO

- [Alt](https://metacpan.org/pod/Alt)
- [Dist::Zilla](https://metacpan.org/pod/Dist::Zilla)

# AUTHOR

Graham Ollis <plicease@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2016-2024 by Graham Ollis.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
