# SIGEDU official website

This is the code for the official website for the ACL SIGEDU: the Association for Computational Linguistics Special Interest Group for building educational applications.  

It's currently using the [Minimal Mistakes Jekyll Theme](https://mmistakes.github.io/minimal-mistakes/).

## local testing with ruby

You can test this website locally on macOS as follows:

1. Install bundler: `sudo gem install bundler`. Make sure you have Ruby and Bundler versions > 2.4.
2. Check out this repository.
3. Run the gems needed by this repository: `sudo bundle install`. 
   *Note*: This step might fail when installing the `nokogiri` gem. If this happens, run `bundle config build.nokogiri --use-system-libraries` and then run `bundle install` again.
4. Start the jekyll server by running `bundle exec jekyll serve`.
5. You can then see the website at http://localhost:4000.

## local testing with Docker

Alternately, if you would prefer using Docker rather than
installing and configuring Ruby, that's also possible.

* Installing docker for Windows

For instructions on how to install docker for Windows 10, go
[here](https://docs.docker.com/docker-for-windows/install/),
or for slightly older Windows computers,
go [here](https://docs.docker.com/toolbox/overview/).

* Installing docker for MacOS

For instructions on how to install docker for MacOS (at
least El Capitan 10.11), go
[here](https://docs.docker.com/docker-for-mac/install/),
or for slightly older MacOS computers,
go [here](https://docs.docker.com/toolbox/overview/)

* Installing docker on Linux

For instructions on how to install docker for Ubuntu (at
least 14.04), go [here](https://docs.docker.com/install/linux/docker-ce/ubuntu/). This link also has options for other
Linux distributions.


to test your installation, just type:
`docker --version`
at the terminal/command prompt

A successful install will result in something that looks like:
`Docker version 17.05.0-ce, build 89658be`

Once you have docker up and running, the following command will
help you run the container locally from within the root
directory of the project:
`docker run --rm --label=jekyll --volume=$(pwd):/srv/jekyll \
-it -p 127.0.0.1:4000:4000 jekyll/jekyll`

This will first pull down the jekyll docker image, then install
all the dependencies inside the container and run the server.

If, instead, you don't want to have to wait for the gems to
download and install every time (perhaps because of a slow
network connection), then build from the dockerfile with:
`docker build -t YOUR_TAG_HERE .`
(the tag is so it's easy to reference later)

and after that's complete, you can just run a server at
http://localhost:4000 with:
`docker run --rm -it -p 4000:4000 -v $(pwd):/srv/jekyll YOUR_TAG_HERE`

## License

The MIT License (MIT)

Copyright (c) 2018 Association for Computational Linguistics.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
