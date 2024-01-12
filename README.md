<p align="center">
  <a href="http://nestpy.org/" target="blank"><img src="" width="120" alt="NestPy Logo" /></a>
</p>

 <p align="center">
    A progressive <a href="http://python.org" target="_blank">Python</a> framework for building efficient and scalable server-side applications.
</p>

## Description

This project is built on top of the [Mkdocs Material](https://github.com/squidfunk/mkdocs-material). It uses the [Mkdocs](https://github.com/mkdocs/mkdocs) to compile source documentation in markdown format into the published format. The Repository contains [docs.nestpy.org](https://docs.nestpy.org) source code, the official Nest documentation.

## Installing

Install project dependencies and start a local server with the following terminal commands:

```bash
$ make start
```

OR

```bash
$ docker run --rm -it -p 8000:8000 -v ${PWD}:/docs squidfunk/mkdocs-material
```

Navigate to [`http://localhost:8000/`](http://localhost:8000/).

All pages are written in [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) and located in the `docs` directory.

## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers.

## Stay in touch

- Author - [Manuel S. Lemos](https://twitter.com/manuels_lemos)
- Website - [https://docs.nestjs.com](https://docs.nestjs.com/)

## License

Nest is [MIT licensed](LICENSE).