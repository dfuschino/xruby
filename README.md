# xRuby

Exercism Exercises in Ruby

## Setup

You'll need a recent (1.9.3+) version of Ruby, but that's it. Minitest ships
with the language, so you're all set.

## Working on Problems

Each problem should have a test suite and an example solution.
The example solution should be named `example.rb`.

**Some problems are generated from shared inputs/outputs, see
[Generated Problems](#generated-problems) below.** In short, if
the problem directory contains an `example.tt` file, then it's a
generated problem.

### Hard-coded Problems

Run the test with `ruby path/to/the_test.rb`.

At the moment the Ruby problems `skip` all but the first test, in order to not
overwhelm people with errors.

If you want to temporarily disable the skips while working on a problem, you can
run the file with a shim that temporarily disables them:


```ruby
ruby -I../lib -rdisable_skip <fiename_test.rb>
```

### Generated Problems

If you find an `example.tt` file in a problem directory, then the problem is
generated from shared data. In this case changing the test file itself will
not be enough.

You will need to have cloned [the shared metadata](https://github.com/exercism/x-common)
at the same level as the xruby repository. E.g.

```
tree -L 1 ~/code/exercism
├── x-common
└── xruby
```

1. `xruby/$PROBLEM/example.tt` - the Erb template for the test file, `$PROBLEM_test.rb`.
1. `x-common/$PROBLEM.json` - the shared inputs and outputs for the problem.
1. `lib/$PROBLEM.rb` - the logic for turning the data into tests.
1. `xruby/bin/generate-$PROBLEM` - the command to actually generate the test suite.
1. `.version` - used to keep track of the version of the test files as the data changes.

Additionally, there is some common generator logic in `lib/generator.rb`.

For example, take a look at the `hamming.json` file in the x-common repository, as well
as the following files in the xruby repository:

1. `hamming/example.tt`
1. `bin/generate-hamming`
1. `lib/hamming.rb`
1. `lib/generator.rb`

The `hamming/hamming_test.rb` will never be edited directly. If there's a missing test case,
then additional inputs/outputs should be submitted to the x-common repository.

Changes to the test suite (style, boilerplate, etc) will probably have to be made to
`example.tt`.

## Pull Requests

We welcome pull requests that provide fixes to existing problems (missing
tests, interesting edge cases, improved APIs), as well as new problems.

If you're unsure, then go ahead and open a GitHub issue, and we'll discuss the
change.

Please submit changes to a single problem per pull request unless you're
submitting a general change across many of the problems (e.g. formatting).

Thank you so much for contributing! :sparkles:

### Style Guide

We have created a minimal set of guidelines for the testing files, which
you can take advantage of by installing the `rubocop` gem.  It will use
the configuration file located in the root folder, `.rubocop.yml`.  When
you edit your code, you can simply run `rubocop -D`.  It will ignore
your `example.rb`, but will gently suggest style for your test code.

The `-D` option that is suggested is provided to give you the ability to
easily ignore the Cops that you think should be ignored.  This is easily
done by doing `# rubocop:disable CopName`, where the `CopName` is replaced
appropriately.

For more complete information, see [Rubocop](http://batsov.com/rubocop/).

## READMEs

Please do not add a README or README.md file to the problem directory. The
READMEs are constructed using shared metadata, which lives in the
[exercism/x-common](https://github.com/exercism/x-common) repository.

## Contributing Guide

For an in-depth discussion of how exercism language tracks and problem sets
work, please see the [contributing guide](https://github.com/exercism/x-api/blob/master/CONTRIBUTING.md#the-exercise-data)

## License

The MIT License (MIT)

Copyright (c) 2014 Katrina Owen, _@kytrinyx.com
