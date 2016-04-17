---
layout: post
title: "Install therubyracer on the OSX - El Captian (10.11)"
date: 2016-04-15T19:22:31+02:00
categories: therubyracer
comments: true
---

Fresh installing `therubyracer` gem on ruby -v >= 2.1

{% highlight text %}
{% raw %}
gem install therubyracer
Fetching: ref-2.0.0.gem (100%)
Successfully installed ref-2.0.0
Fetching: libv8-3.16.14.13.gem (100%)
Building native extensions.  This could take a while...
ERROR:  Error installing therubyracer:
  ERROR: Failed to build gem native extension.
    current directory: /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/ext/libv8
/Users/user/.rvm/rubies/ruby-2.3.0/bin/ruby -r ./siteconf20160415-29419-1exohh8.rb extconf.rb
creating Makefile
Compiling v8 for x64
Using python 2.7.10
Using compiler: /usr/bin/c++ (clang version 6.1.0)
/Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/libtool: file: /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/atomicops_internals_x86_gcc.o has no symbols
In file included from ../src/accessors.cc:28:
In file included from ../src/v8.h:60:
In file included from ../src/objects-inl.h:38:
In file included from ../src/elements.h:33:
In file included from ../src/heap.h:35:
In file included from ../src/incremental-marking.h:33:
In file included from ../src/mark-compact.h:32:
../src/spaces.h:896:26: error: 'this' pointer cannot be null in well-defined C++ code; comparison may be assumed to always evaluate to true [-Werror,-Wtautological-undefined-compare]
  bool exists() { return this != NULL && code_range_ != NULL; }
../src/spaces.h:898:9: error: 'this' pointer cannot be null in well-defined C++ code; comparison may be assumed to always evaluate to false [-Werror,-Wtautological-undefined-compare]
    if (this == NULL || code_range_ == NULL) return false;
2 errors generated.
make[1]: *** [/Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/v8_base/src/accessors.o] Error 1
make: *** [x64.release] Error 2
/Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/ext/libv8/location.rb:36:in `block in verify_installation!': libv8 did not install properly, expected binary v8 archive '/Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/tools/gyp/libv8_base.a'to exist, but it was not found (Libv8::Location::Vendor::ArchiveNotFound)
  from /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/ext/libv8/location.rb:35:in `each'
  from /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/ext/libv8/location.rb:35:in `verify_installation!'
  from /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/ext/libv8/location.rb:26:in `install!'
  from extconf.rb:7:in `<main>'
GYP_GENERATORS=make \
  build/gyp/gyp --generator-output="out" build/all.gyp \
                -Ibuild/standalone.gypi --depth=. \
                -Dv8_target_arch=x64 \
                -S.x64  -Dv8_enable_backtrace=1 -Dv8_can_use_vfp2_instructions=true -Darm_fpu=vfpv2 -Dv8_can_use_vfp3_instructions=true -Darm_fpu=vfpv3 -Dwerror=''
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/allocation.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/atomicops_internals_x86_gcc.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/bignum.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/bignum-dtoa.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/cached-powers.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/conversions.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/diy-fp.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/dtoa.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/fast-dtoa.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/fixed-dtoa.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/once.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/preparse-data.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/preparser.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/preparser-api.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/scanner.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/strtod.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/token.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/unicode.o
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser_lib/src/utils.o
  LIBTOOL-STATIC /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/libpreparser_lib.a
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/preparser/preparser/preparser-process.o
  LINK(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/preparser
  CXX(target) /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13/vendor/v8/out/x64.release/obj.target/v8_base/src/accessors.o

extconf failed, exit code 1

Gem files will remain installed in /Users/user/.rvm/gems/ruby-2.3.0@test/gems/libv8-3.16.14.13 for inspection.
Results logged to /Users/user/.rvm/gems/ruby-2.3.0@test/extensions/x86_64-darwin-15/2.3.0/libv8-3.16.14.13/gem_make.out
{% endraw %}
{% endhighlight %}

Uninstalling libv8 and installing libv8 with `-- --with-system-v8` wont be able to solve the issue on El Caption

It can be solved in the following way


{% highlight ruby %}
brew tap homebrew/versions
brew install v8-315

brew link --force v8-315
- if it throws error from the previous v8
  brew unlink v8
  brew link --force v8-315
{% endhighlight %}

`Using bundle`
{% highlight ruby %}
bundle config build.libv8 --with-system-v8
bundle config build.therubyracer --with-v8-dir=/usr/local/opt/v8-315

bundle install
{% endhighlight %}

{% highlight ruby %}

gem install libv8 -v '3.16.14.13' -- --with-system-v8
gem install therubyracer -- --with-v8-dir=/usr/local/opt/v8-315

{% endhighlight %}


[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
