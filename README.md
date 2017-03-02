Percept - Erlang Concurrency Profiling Tool
====

Percept uses `erlang:trace/3` and `erlang:system_profile/2` to monitor events from
process states. Such states are,

 * waiting
 * running
 * runnable
 * free
 * exiting

There are some other states too, suspended, hibernating, and garbage collecting (GC).
The only ignored state is gc and a process is considered to have its previous
state through out the entire garbage collecting phase. The main reason for this,
is that our model considers the gc as a third state neither active nor inactive.

A waiting or suspended process is considered an inactive process and a running or
runnable process is considered an active process.

Events are collected and stored to a file. The file can be moved and analyzed on
a different machine than the target machine.
