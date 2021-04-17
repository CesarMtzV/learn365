# Signals in C
___
Index | Topic
--- | ---
**1** | Description
**2** | Standar signals
**3** | Signal default actions
**4** | Handler functions

## Description

- Signals are generated events that notify a process or thread that something has happened.
- When the process receives a signal, it will stop its function and solve the corresponding signal
- They are defined in the library `signal.h` and every signal starts with __SIG__

## Standard Signals

- SIGHUP: Hang-up the process
- SIGINT: Interrupt the process
- SIGQUIT: Quit the process
- SIGILL: Illegal instruction
- SIGTRAP: Trace trap
- SIGABRT: Abort
- SIGFPE: Floating-point exception
- SIGUSR1 & SIGUSR2: Can be used however you wish

## Signal default actions

Each signal has a default action:
- Term: terminate the process
- Core: the process finishes and creates a core dump file
- Ign: the process ignores the signal
- Stop: the process stops
- Cont: the process continues even after being stopped

The default action can be changed using a __handler function__

## Handler functions

They are a custom way to handle a signal.

- `int signal() (int signum, void (*func)(int))`