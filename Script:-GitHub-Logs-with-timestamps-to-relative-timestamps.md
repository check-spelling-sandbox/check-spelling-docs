# Script: GitHub Logs with timestamps to relative timestamps

Sometimes it's helpful to be able to compare two GitHub workflow runs to see how long steps are taking.

This script converts timestamps from absolute to relative:

```pl
#!/usr/bin/env perl
use Time::Piece;
my $last;
while (<>) {
  next unless /^(\d+-\d+-\d+T\d+:\d+:\d+)\.(\d+)Z (.*)/;
  my ($t, $s, $l) = ($1, $2, $3);
  my $p = Time::Piece->strptime($t, "%Y-%m-%dT%T");
  my $e = $p->epoch;
  $e = "$e$s";
  $l =~ s/\x1b/[ESC]/g;
  unless (defined $last) {
    $last = $e;
    print "[$t.$s]:\n";
    print "[+0] $l\n";
  } else {
    my $delta = $e - $last;
    $last = $e;
    print "[+$delta] $l\n";
  }
}
```

---
[FAQ](FAQ.md) | [Showcase](Showcase.md) | [Event descriptions](Event-descriptions.md) | [Configuration information](Configuration-information.md) | [Known Issues](Known-Issues.md) | [Possible features](Possible-features.md) | [Deprecations](Deprecations.md) | [Release notes](Release-notes.md) | [Helpful scripts](Helpful-scripts.md)
