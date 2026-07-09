<p align="center"><img src="https://raw.githubusercontent.com/go-puppetdb/brand/main/social/go-puppetdb.png" alt="go-puppetdb" width="640"></p>

<h1 align="center">go-puppetdb</h1>
<p align="center"><strong>PuppetDB query language (PQL) in pure Go — parser, in-memory evaluator and /pdb/query/v4 client.</strong></p>

<p align="center">
  🌐 <a href="https://go-puppetdb.github.io">Website</a> ·
  📚 <a href="https://go-puppetdb.github.io/docs/">Documentation</a>
</p>

<p align="center">
  <a href="https://go-puppetdb.github.io/docs/"><img alt="Docs" src="https://img.shields.io/badge/docs-mkdocs--material-4F46E5?style=flat-square"></a>
  <a href="https://github.com/go-puppetdb/puppetdb/blob/main/LICENSE"><img alt="License: BSD-3-Clause" src="https://img.shields.io/badge/license-BSD--3--Clause-blue?style=flat-square"></a>
  <img alt="Go 1.26.4+" src="https://img.shields.io/badge/go-1.26.4%2B-00ADD8?style=flat-square&logo=go&logoColor=white">
  <img alt="Coverage 100%" src="https://img.shields.io/badge/coverage-100%25-1a7f37?style=flat-square">
</p>

---

go-puppetdb is a pragmatic, pure-Go (CGO_ENABLED=0) toolkit for PuppetDB's query language. It provides a PQL lexer, parser and typed AST; a compiler from that AST to PuppetDB's canonical AST-query JSON wire form; an in-memory evaluator so PQL is useful and fully testable without a server; and an HTTP client for a real PuppetDB /pdb/query/v4 endpoint behind an injectable http.RoundTripper seam. Entities (nodes, resources, facts, inventory, catalogs, reports, …), comparison / regexp / boolean operators, in subqueries, null tests, projection and order / limit / offset are all supported. Standard library only, 100% coverage, six arches and WebAssembly.

## Repositories

| Repo | What it is |
|------|------------|
| [**puppetdb**](https://github.com/go-puppetdb/puppetdb) | the engine library |
| [**docs**](https://github.com/go-puppetdb/docs) | MkDocs Material documentation, versioned with [mike], served at [/docs/](https://go-puppetdb.github.io/docs/) |
| [**go-puppetdb.github.io**](https://github.com/go-puppetdb/go-puppetdb.github.io) | the Hugo landing page |
| [**brand**](https://github.com/go-puppetdb/brand) | logos and brand assets |

## Principles

- **Pure Go, zero cgo.** `CGO_ENABLED=0`; imports the Go standard library only. Cross-compiles to the
  six 64-bit Go targets (amd64, arm64, riscv64, loong64, ppc64le, s390x) and WebAssembly, linking into a static binary.
- **Faithful to PuppetDB's PQL and AST-query wire form.**
- **An engine, not a service.** A small, stable Go API you embed — part of the
  pure-Go Puppet stack (siblings [go-facter](https://github.com/go-facter),
  [go-hiera](https://github.com/go-hiera), [go-pcore](https://github.com/go-pcore),
  [go-puppet](https://github.com/go-puppet)).
- **100% test coverage** including error branches, enforced as a CI gate.

BSD-3-Clause.

[mike]: https://github.com/jimporter/mike
