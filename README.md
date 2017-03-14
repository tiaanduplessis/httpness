<h1 align="center">🌏 httpness 🌏</h1>
<div align="center">
  <strong>Simple AF CLI HTTP client</strong>
</div>
<br>
<div align="center">
  <a href="https://npmjs.org/package/httpness">
    <img src="https://img.shields.io/npm/v/httpness.svg?style=flat-square" alt="Package version" />
  </a>
  <a href="https://npmjs.org/package/httpness">
  <img src="https://img.shields.io/npm/dm/httpness.svg?style=flat-square" alt="Downloads" />
  </a>
  <a href="https://github.com/feross/standard">
    <img src="https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat-square" alt="Standard" />
  </a>
  <a href="https://travis-ci.org/tiaanduplessis/httpness">
    <img src="https://img.shields.io/travis/tiaanduplessis/httpness.svg?style=flat-square" alt="Travis Build" />
  </a>
  <a href="https://github.com/RichardLitt/standard-readme)">
    <img src="https://img.shields.io/badge/standard--readme-OK-green.svg?style=flat-square" alt="Standard Readme" />
  </a>
  <a href="https://badge.fury.io/gh/tiaanduplessis%2Fhttpness">
    <img src="https://badge.fury.io/gh/tiaanduplessis%2Fhttpness.svg?style=flat-square" alt="GitHub version" />
  </a>
  <a href="https://dependencyci.com/github/tiaanduplessis/httpness">
    <img src="https://dependencyci.com/github/tiaanduplessis/httpness/badge?style=flat-square" alt="Dependency CI" />
  </a>
  <a href="https://github.com/tiaanduplessis/httpness/blob/master/other/LICENSE">
    <img src="https://img.shields.io/npm/l/httpness.svg?style=flat-square" alt="License" />
  </a>
  <a href="http://makeapullrequest.com">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square" alt="PRs" />
  </a>
  <a href="https://www.paypal.me/tiaanduplessis/1">
    <img src="https://img.shields.io/badge/$-support-green.svg?style=flat-square" alt="Donate" />
  </a>
</div>
<br>
<div align="center">
  <a href="https://github.com/tiaanduplessis/httpness/watchers">
    <img src="https://img.shields.io/github/watchers/tiaanduplessis/httpness.svg?style=social" alt="Github Watch Badge" />
  </a>
  <a href="https://github.com/tiaanduplessis/httpness/stargazers">
    <img src="https://img.shields.io/github/stars/tiaanduplessis/httpness.svg?style=social" alt="Github Star Badge" />
  </a>
  <a href="https://twitter.com/intent/tweet?text=Check%20out%20httpness!%20https://github.com/tiaanduplessis/httpness%20%F0%9F%91%8D">
    <img src="https://img.shields.io/twitter/url/https/github.com/tiaanduplessis/httpness.svg?style=social" alt="Tweet" />
  </a>
</div>
<br>
<div align="center">
  Built with ❤︎ by <a href="tiaanduplessis.co.za">Tiaan</a> and <a href="https://github.com/tiaanduplessis/httpness/graphs/contributors">contributors</a>
</div>

<h2>Table of Contents</h2>
<details>
  <summary>Table of Contents</summary>
	<li><a href="#about">about</a></li>
  <li><a href="#install">Install</a></li>
  <li><a href="#usage">Usage</a></li>
  <li><a href="#api">API</a></li>
  <li><a href="#contribute">Contribute</a></li>
  <li><a href="#license">License</a></li>
</details>

## About

This cli module is a simple HTTP client similar to [httpie](https://httpie.org/), but with a lot less functionality. It is build on top of [node-fetch](https://github.com/bitinn/node-fetch) and uses [prettyjson](https://github.com/rafeca/prettyjson) to provide nice formatting.

## Install

```sh
$ npm install -g httpness
```

Or

```sh
$ yarn add global httpness
```

## Usage

After the module has been installed globally, it can be called from the terminal:

```sh
$ httpness --url=https://jsonplaceholder.typicode.com/posts/1
```

This will output:


<div align="center" >
	<image src="media/get-example.png" alt="GET example" width="80%"/>
</div>


It also supports other HTTP methods like `POST`:


```sh
$ httpness --url=https://jsonplaceholder.typicode.com/posts --method=POST --body={title: 'Hi', body: 'Friend', userId: 1}
```


This will output:


<div align="center">
	<image src="media/post-example.png" alt="POST example" width="80%"/>
</div>


## API

The following argument flags are supported:


<table style="width:100%">
  <tr>
    <th>Flag</th>
    <th>Description</th>
    <th>Default</th>
		<th>Example</th>
  </tr>
  <tr>
    <td><code>--url</code>, <code>-url</code>, <code>--u</code> or <code>-u</code></td>
    <td>The URL to make request to. <strong>Required</strong></td>
    <td>-</td>
		<td><code>--url=https://jsonplaceholder.typicode.com/posts/1</code></td>
  </tr>
  <tr>
    <td><code>--method</code>, <code>-method</code>, <code>--m</code> or <code>-m</code></td>
    <td>The HTTP method to use.</td>
    <td><code>GET</code></td>
		<td><code>--method=POST</code></td>
  </tr>
	<tr>
    <td><code>--body</code>, <code>-body</code>, <code>--b</code> or <code>-b</code></td>
    <td>Body to send with request.</td>
    <td><code>''</code></td>
		<td><code>--body={title: 'Hi', body: 'Friend', userId: 1}</code></td>
  </tr>
	<tr>
    <td><code>--headers</code>, <code>-headers</code>, <code>--h</code> or <code>-h</code></td>
    <td>Headers to send with request.</td>
    <td><code>{}</code></td>
		<td><code>--headers={Content-Type: 'application/json; charset=utf-8'}</code></td>
  </tr>
	<tr>
    <td><code>--credentials</code>, <code>-credentials</code>, <code>--c</code> or <code>-c</code></td>
    <td>Credentials to send with request.</td>
    <td><code>''</code></td>
		<td><code>--credentials=same-origin</code></td>
  </tr>
</table>

## Contribute

Contributions are welcome. Please open up an issue or create PR if you would like to help out.

Note: If editing the README, please conform to the [standard-readme](https://github.com/RichardLitt/standard-readme) specification.

## License

Licensed under the MIT License.
