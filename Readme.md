My app uses [rugged](http://rubygems.org/gems/rugged).
To compile this, I need cmake and pkg-config.
Going to see if I can't get that stuffs installed with this buildpack.

---

Use [buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi)
to add this to the build.
Example of my [.buildpacks](https://github.com/JoshCheek/miniature-octo-ironman/blob/8d5cc7396a7fae3777387be921c6594c6bd4b5d5/.buildpacks).
Example of setting it up in [my repo](https://github.com/JoshCheek/miniature-octo-ironman/):

```
# Use multi-buildpacks
$ heroku buildpacks:set ddollar/multi

# Make sure it worked
$ heroku config | grep BUILD
BUILDPACK_URL: https://codon-buildpacks.s3.amazonaws.com/buildpacks/ddollar/multi.tgz

# Configure it to use this buildpack and Ruby
$ cat .buildpacks
https://github.com/JoshCheek/heroku-buildpack-for-cmake-and-pkg-config.git
https://github.com/heroku/heroku-buildpack-ruby.git
```



MIT-LICENSE
-----------

Copyright (c) 2014 Josh Cheek <josh.cheek@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
