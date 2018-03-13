# `format-your-pivot` 

`format-your-pivot` is a challenge that was created by
[Adam Doupé][adamd-homepage], specifically designed to introduce using
[Return Oriented Programming][rop] pivots along with a targeted
overwrite.

A good exercise is to compare this challenge with [baby-pivot][baby-pivot].

You are given the [binary][binary].

The goal is to write a repeatable exploit script to steal the flag
(located at `/challenge/flag`) remotely.

To run the challenge locally on your machine:

	docker run -p 127.0.0.1:31337:31337 -it adamdoupe/format-your-pivot

This will download the [docker image][docker-container] and run it
using docker. The challenge is running under [xinetd][xinetd-man] on
port 31337 in the container. The `-p` option maps the localhost's port
31337 to the docker container's port 31337. The 127.0.0.1 part is
optional (this restricts the port on your actual machine to only
listen for connections from localhost), however you are running
intentionally vulnerable software on your machine, so it's not a good
idea for it to be accessible to other machines.

You should then be able to access format-your-pivot like so:

	nc localhost 31337

To jump in and debug the program, you can use the following command
to get a bash shell

	docker run --security-opt seccomp:unconfined -it adamdoupe/format-your-pivot bash

[pctf-2017]: https://ctftime.org/event/439
[binary]: format-your-pivot
[docker-container]: https://hub.docker.com/r/adamdoupe/format-your-pivot/
[xinetd-man]: https://linux.die.net/man/8/xinetd
[adamd-homepage]: http://adamdoupe.com
[rop]: https://en.wikipedia.org/wiki/Return-oriented_programming
[babys-first-rop-32]: ../babys-first-rop-32/README.md
[baby-pivot]: ../baby-pivot/README.md
