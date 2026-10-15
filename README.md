<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# setDescriptorOffsets

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Set ndarray [descriptor][@stdlib/ndarray/base/descriptor] index offsets.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->

<section class="installation">

## Installation

```bash
npm install @stdlib/ndarray-base-set-descriptor-offsets
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm`][esm-url] branch (see [README][esm-readme]).
-   If you are using Deno, visit the [`deno`][deno-url] branch (see [README][deno-readme] for usage intructions).
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd`][umd-url] branch (see [README][umd-readme]).

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

To view installation and usage instructions specific to each branch build, be sure to explicitly navigate to the respective README files on each branch, as linked to above.

</section>

<section class="usage">

## Usage

```javascript
var setDescriptorOffsets = require( '@stdlib/ndarray-base-set-descriptor-offsets' );
```

#### setDescriptorOffsets( descriptors, offsets )

Sets ndarray [descriptor][@stdlib/ndarray/base/descriptor] index offsets.

```javascript
var Float64Array = require( '@stdlib/array-float64' );
var getOffset = require( '@stdlib/ndarray-base-offset' );
var ndarraylike2descriptor = require( '@stdlib/ndarray-base-ndarraylike2descriptor' );

var obj = ndarraylike2descriptor({
    'dtype': 'float64',
    'data': new Float64Array( [ 1.0, 2.0, 3.0, 4.0 ] ),
    'shape': [ 1 ],
    'strides': [ 1 ],
    'offset': 0,
    'order': 'row-major'
});

var arr = [ obj ];
var out = setDescriptorOffsets( arr, [ 2 ] );
// returns [...]

var bool = ( out === arr );
// returns true

var offset = getOffset( arr[ 0 ] );
// returns 2
```

The function supports the following parameters:

-   **descriptors**: list of ndarray [descriptors][@stdlib/ndarray/base/descriptor].
-   **offsets**: list of index offsets.

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

## Notes

-   The function mutates the provided [descriptors][@stdlib/ndarray/base/descriptor].

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

<!-- eslint-disable new-cap -->

```javascript
var zeros = require( '@stdlib/ndarray-zeros' );
var slice = require( '@stdlib/ndarray-slice' );
var E = require( '@stdlib/slice-multi' );
var ndarraylike2descriptor = require( '@stdlib/ndarray-base-ndarraylike2descriptor' );
var getOffsets = require( '@stdlib/ndarray-base-offsets' );
var setDescriptorOffsets = require( '@stdlib/ndarray-base-set-descriptor-offsets' );

// Create an array:
var x = zeros( [ 3, 3, 3 ] );
// returns <ndarray>

// Define a slice:
var s = E( 0, null, null ); // 0,:,:

// Create an ndarray view of the first subarray in the stack:
var view = slice( x, s );

// Create a list of ndarray descriptors:
var desc = [
    ndarraylike2descriptor( view ),
    ndarraylike2descriptor( view )
];

// Define a list of offsets:
var offsets = [ 9, 18 ];

// Set the index offsets for each descriptor so that each descriptor points to a different subarray in the stack:
var out = setDescriptorOffsets( desc, offsets );

// Resolve the offsets from the descriptors:
console.log( getOffsets( out ) );
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/ndarray-base-set-descriptor-offsets.svg
[npm-url]: https://npmjs.org/package/@stdlib/ndarray-base-set-descriptor-offsets

[test-image]: https://github.com/stdlib-js/ndarray-base-set-descriptor-offsets/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/ndarray-base-set-descriptor-offsets/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/ndarray-base-set-descriptor-offsets/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/ndarray-base-set-descriptor-offsets?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/ndarray-base-set-descriptor-offsets.svg
[dependencies-url]: https://david-dm.org/stdlib-js/ndarray-base-set-descriptor-offsets/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/ndarray-base-set-descriptor-offsets/tree/deno
[deno-readme]: https://github.com/stdlib-js/ndarray-base-set-descriptor-offsets/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/ndarray-base-set-descriptor-offsets/tree/umd
[umd-readme]: https://github.com/stdlib-js/ndarray-base-set-descriptor-offsets/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/ndarray-base-set-descriptor-offsets/tree/esm
[esm-readme]: https://github.com/stdlib-js/ndarray-base-set-descriptor-offsets/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/ndarray-base-set-descriptor-offsets/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/ndarray-base-set-descriptor-offsets/main/LICENSE

[@stdlib/ndarray/base/descriptor]: https://github.com/stdlib-js/ndarray-base-descriptor

</section>

<!-- /.links -->
