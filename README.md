NAME
====
`Pakku::Spec` - Dependency Specification for `Pakku`

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
`Pakku::Spec` is a Dependency Specification for `Pakku`

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

