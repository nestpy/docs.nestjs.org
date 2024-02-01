# Introduction

Nest (NestPy) is a framework for building efficient, scalable [Python](https://python.org/) server-side applications and combines elements of OOP (Object Oriented Programming), FP (Functional Programming), and FRP (Functional Reactive Programming).

Under the hood, Nest makes use of robust HTTP Server frameworks like [FastAPI](https://github.com/tiangolo/fastapi) (the default) and optionally can be configured to use [Flask](https://github.com/pallets/flask) (in development) as well!

Nest provides a level of abstraction above these common Python frameworks (FastAPI/Flask), but also exposes their APIs directly to the developer. This gives developers the freedom to use the myriad of third-party modules which are available for the underlying platform.

## Philosophy

Nest provides an out-of-the-box application architecture which allows developers and teams to create highly testable, scalable, loosely coupled, and easily maintainable applications. The architecture is heavily inspired by NestJS and Angular.

## Installation

To get started, you can either scaffold the project with the [Nest CLI](/cli/overview), or clone a starter project (both will produce the same outcome).

To scaffold the project with the Nest CLI, run the following commands. This will create a new project directory, and populate the directory with the initial core Nest files and supporting modules, creating a conventional base structure for your project. Creating a new project with the **Nest CLI** is recommended for first-time users. We'll continue with this approach in [First Steps](first-steps).

```bash
$ pip install nestpy-cli
$ nest new project-name
```

## Alternatives

Alternatively, to install the Poetry starter project with Git:

```bash
$ git clone https://github.com/nestpy/poetry-starter.git project
$ cd project
$ poetry install
$ poetry run start
```

> info **Hint** If you'd like to clone the repository without the git history, you can use [degit](https://github.com/Rich-Harris/degit).

Open your browser and navigate to [`http://localhost:3000/`](http://localhost:3000/).

To install the Pip flavor of the starter project, use `pip-starter.git` in the command sequence above.

You can also manually create a new project from scratch by installing the core and supporting files with **pip** (or **poetry**). In this case, of course, you'll be responsible for creating the project boilerplate files yourself.

```bash
$ pip add nestpy-framework
```