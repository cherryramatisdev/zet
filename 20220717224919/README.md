# how to get the approves from a pull request

## Get the list of reviews on a particular PR:

```sh
gh api -H "Accept: application/vnd.github+json" /repos/lami-health/website/pulls/720/reviews 
```

## Parse the list of reviews with `jq` to get every status:

```sh
gh api -H "Accept: application/vnd.github+json" /repos/lami-health/website/pulls/720/reviews | jq '.[].state'
```

## Parse the approvals correctly
Found the script on: <https://github.com/cherryramatisdev/dot/tree/main/scripts/review>

```perl
#!/usr/bin/env perl

use v5.14;

my @reviews = `gh api -H \"Accept: application/vnd.github+json\" /repos/lami-health/website/pulls/720/reviews | jq '.[].state'`;

my $acc = 0;

say @reviews;

foreach my $line (@reviews) {
    if ($line =~ /CHANGES_REQUESTED/) {
	$acc = 0;
	next;
    }

    if ($line =~ /APPROVED/) {
	$acc++;
    }
}

say "$acc/3 Approvals";
```

PR for the test: <https://github.com/lami-health/website/pull/720#pullrequestreview-1041193027>

Output:

```
"APPROVED"
"COMMENTED"
"CHANGES_REQUESTED"
"APPROVED"
"COMMENTED"
"APPROVED"

2/3 Approvals
```

  #git #github #api #gh #pr #pull #request

