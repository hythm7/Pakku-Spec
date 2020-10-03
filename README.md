NAME
====
`Pakku::Spec` - Dependency Specification for [Pakku](https://github.com/Raku/Blin.git) Package Manager.

SYNOPSIS
========
```raku
use Pakku::Spec;

my $spec = Pakku::Spec.new: 'ModuleName:ver(0.0.1):auth<Camelia <camelia@raku.org>>:api<>';

say $spec.spec;
# {api => , auth => Camelia <camelia@raku.org>, from => raku, name => ModuleName, ver => 0.0.1}


$spec = Pakku::Spec.new: {:hints(${"by-kernel.name" => ${:linux(${:checksum(${"sha-256" => "E6836E32802555593AEDAFE1CC00752CBDA"}), :target("resources/libraries/"), :url("http://raku.org/")})}}), :name("archive:from<native>")};

say $spec.spec;
# {from => native, name => archive}

say $spec.hints;

# Pakku::Spec::Hints.new(url => "http://raku.org/", target => "resources/libraries/", checksum => Pakku::Spec::Hints::Checksum.new(type => "sha-256", hash => "E6836E32802555593AEDAFE1CC00752CBDA"), source => Pakku::Spec::Hints::Source)

```

DESCRIPTION
===========
`Pakku::Spec` is a Dependency Specification used by [Pakku](https://github.com/hythm7/Pakku).

`Pakku::Spec` parses the dependencies specified by `Raku` distributions as string like `My::Dependency:ver<0.0.1+>` or hash like `{ :name<MyLib>,:from<native> }`. also parses the `hints` section if provided in a dependency to provide for example the correct name based on `$*DISTRO` or `$*KERNEL`

`Pakku::Spec` is mainly used by [Pakku::Meta](https://github.com/hythm7/Pakku-Meta)  to parse the `depends` section in `META6.json` files.



INSTALLATION
===========
```
pakku add Pakku::Spec

# or 

zef install Pakku::Spec
```

AUTHOR
======
Haytham Elganiny <elganiny.haytham@gmail.com>

COPYRIGHT AND LICENSE
=====================
Copyright 2020 Haytham Elganiny

This library is free software; you can redistribute it and/or modify it under the Artistic License 2.0.

