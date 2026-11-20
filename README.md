# IT Projects Portfolio

A staged portfolio of 50 original, documented engineering projects across AI,
cybersecurity, developer infrastructure, business software, and computer
science. The work is developed one project milestone at a time; project status
is recorded in [PROJECT-STATUS.md](PROJECT-STATUS.md).

## Start here

- [Project catalogue](PORTFOLIO.md)
- [Roadmap](ROADMAP.md)
- [Technology choices](TECH-STACK.md)
- [Portfolio architecture and workflow](ARCHITECTURE.md)
- [Current status](PROJECT-STATUS.md)

## First implementation: AlgorithmUniverse

The Wave 1 flagship is a dependency-free browser application for stepping
through sorting algorithms. It includes Bubble, Selection, and Insertion Sort,
randomized input, playback controls, and deterministic unit tests.

```sh
cd projects/algorithm-universe
env -u LD_LIBRARY_PATH python -m http.server 8000
```

Open `http://127.0.0.1:8000` in a browser. Run its tests with:

```sh
env -u LD_LIBRARY_PATH node --test
```

The temporary `env -u LD_LIBRARY_PATH` accommodates this Termux session's
Codex-injected native-library path; it does not modify shell configuration.

## Development principles

Projects begin as modular, runnable implementations with explicit limits.
Databases, services, and infrastructure are introduced only when the project
requires them. No secrets, credentials, or user data belong in this repository.
Public releases follow review of the exact files and Git status.

## License

Portfolio materials are released under the MIT License unless a project says
otherwise.
