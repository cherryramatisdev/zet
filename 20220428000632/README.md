# Perl reference and dereference

A reference is like a pointer as I briefly understand in Perl, but the important part here is the context that is **SUBCOMMANDS**.

I cross a part this amazing use case with sub routine references that is creating a hash full of subcommands and execute each one based on user input.

Example:

```perl
sub amend {
  say "amend";
}

sub teste {
  say "teste";
}

my %commands = (
  amend => \&amend,
  teste => \&teste
);

if (defined $commands{$ARGV[0]}) {
  my $command_ref = $commands{$ARGV[0]};

  &$command_ref;
}
```

1. Reference
	To reference subroutine in Perl we use this `\&` symbol, as we can see we can pass it as a value to a hash key

2. Dereference
	Dereferencing is basically calling the function on our case, but means to get the actual value from your reference, to dereference a subroutine we use the `&$` symbol and that's it!! Organization;

Also, this is the resource for other references types :: <https://www.geeksforgeeks.org/perl-references-to-a-subroutine/>
