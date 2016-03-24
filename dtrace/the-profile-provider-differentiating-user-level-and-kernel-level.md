# The profile provider: Differentiating between user-level and kernel-level

The following is based on Chapter 3 in
[DTrace: Dynamic Tracing in Oracle Solaris, Mac OS X, and FreeBSD](http://dtracebook.com/index.php/Main_Page)
by Brendan Gregg.

The [profile provider](http://dtrace.org/guide/chp-profile.html) can be
used to sample activity on the CPUs at given intervals, using the syntax
`profile-n`, where `n` is some time measure. In the DTrace book, Brendan
Gregg frequently uses `997hz`. This means that the profile provider
will sample all CPUs 997 times per second. He chooses 997, as opposed
to something rounder, so as to not go in lockstep with timed kernel
tasks.

The profile provider takes two arguments, and by detecting the
presence of these arguments, we can separate between user-level
code and kernel-level code. The first, `arg0`, is the program
counter in the kernel at the time the probe fired, or 0 if the
process was not executing in the kernel. Similarly, `arg1` is the
program counter in the user-level process at the time the probe
fired, or 0 if the code was running in the kernel when the probe
fired. This allows you to easily differentiate between user-level
and kernel-level code, like in this example from the [DTrace
manual](http://dtrace.org/guide/chp-profile.html), which shows how the
CPU's divide their time between user-level and kernel-level by sampling
every millisecond:

```
profile-1ms
{
    @ticks[arg0 ? "kernel" : "user"] = count();
}
```
