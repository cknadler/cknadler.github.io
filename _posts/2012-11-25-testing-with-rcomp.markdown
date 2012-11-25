---
layout: post
title: Testing With RComp
---
A few weeks ago I ran into a bit of a problem. I was working on [marktab][marktab] and I needed a way to test it. Shortly after, [russplaysguitar][russ] started development on a port, [marktab-coffee][marktab-coffee]. I needed output behavior tests to make sure we kept the grammar consistent between both projects.

While unit tests have their place and will definitely be used in both projects, we needed a framework that would make it easy to write simple output tests. 

I started working on a ruby script...

A few weeks later, [RComp][rcomp] was born.

## How It Works

With RComp, "tests" are each individual files. RComp stores tests in a directory, by default `[project_root]/rcomp`.

A simple RComp suite might look like:

```
.
|--rcomp
|----tests
|------test1.test
|------dir
|--------test2.test
|----expected
|------test1.out
|------dir
|--------test2.out
|--------test2.err
|----results
```

RComp tests by running a command concatenated with the a test path for each test.

For example, given the suite above, if you defined your test command as `./some_exec.rb`, `rcomp test` would run:

```
./some_exec.rb rcomp/tests/test1.test
./some_exec.rb rcomp/tests/dir/test2.test
```

passing the files as arguments to `some_exec.rb`.

If you wanted to pass the contents of the files as input instead of by argument, simply change the command to `./some_exec.rb <` and the resulting tests would be:

```
./some_exec.rb < rcomp/tests/test1.test
./some_exec.rb < rcomp/tests/dir/test2.test
```

Once a test is run, the output is stored in the `results` directory and is compared with the relative expected output.

Check out the [README](https://github.com/cknadler/rcomp#rcomp---) for more in depth usage.

## Purpose

RComp is meant to be a supplement to other testing frameworks with a focus on extremely simple, fast tests with low overhead. This is an attempt to make my original script as widely usable as possible, still, RComp is __not__ for all projects.

#### RComp _Can_...

* Test the output of a command or executable
* Generate expected output for tests
* Filter tests based on patterns

#### RComp _Can't_...

* Test multiple commands or executables per project
* Test complex commands where the test file isn't an argument (coming soon)

## Source

Everything is on [github][github] at [cknadler/rcomp][rcomp]. Contributions and feature requests are more than welcome. 

Resources:

* [RubyGems](https://rubygems.org/gems/rcomp)
* [Code Climate](https://codeclimate.com/github/cknadler/rcomp)
* [Travis CI](https://travis-ci.org/cknadler/rcomp)
* [Gemnasium](https://gemnasium.com/cknadler/rcomp)

If you have any questions you can ping me on twitter [@cknadler][twitter] or shoot me an [email][email]. 


[marktab]: https://github.com/cknadler/marktab
[russ]: https://github.com/russplaysguitar
[marktab-coffee]: https://github.com/russplaysguitar/marktab-coffee
[rcomp]: https://github.com/cknadler/rcomp
[github]: https://github.com
[twitter]: https://twitter.com/cknadler
[email]: mailto:takeshi91k@gmail.com
