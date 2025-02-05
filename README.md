# NOTE: This library is unmaintained and deprecated.

Hull.js is a JavaScript library that builds concave hull by set of points.

## Examples

See live examples <a target="_blank" href="http://andriiheonia.github.io/hull/">here</a>.

## Usage

	var points = [ [236, 126], [234, 115], [238, 109], [247, 102], ... ];
	hull(points, 50); // returns points of the hull (in clockwise order)

## Params

* 1st param - array of coordinates in format: `[[x1, y1], [x2, y2], ..., [xn, yn]]`.
* 2nd param - concavity. `1` - thin shape. `Infinity` - convex hull. By default `20`.
* 3rd param - points format. For example: `['.lng', '.lat']` if you have `{lng: x, lat: y}` points. By default you can use `[x, y]` points.

## How it works

<details>
    <summary>Expand</summary>

Let's see step by step what happens when you call `hull()` function:

<ol>
    <li>
        <div>Hull.js takes your source points of the shape:</div>
        <div><img src="https://raw.githubusercontent.com/andriiheonia/hull/master/readme-imgs/0.png" /></div>
    </li>
    <li>
        <div>Builds convex hull:</div>
        <div><img src="https://raw.githubusercontent.com/andriiheonia/hull/master/readme-imgs/1.png" /></div>
    </li>
    <li>
        <div>After that, the edges flex inward (according to the `concavity` param). For example:</div>
        <div>
            <img src="https://raw.githubusercontent.com/andriiheonia/hull/master/readme-imgs/2_1.png" />
            `concavity = 80`<br/>
            <img src="https://raw.githubusercontent.com/andriiheonia/hull/master/readme-imgs/2_2.png" />
            `concavity = 40`<br/>
            <img src="https://raw.githubusercontent.com/andriiheonia/hull/master/readme-imgs/2_3.png" />
            `concavity = 20`
        </div>
    </li>
</ol>

</details>

## NPM package

Since version 1.0.7 this library is not hosted on npmjs.com. You can still use [GitHub URL](https://docs.npmjs.com/cli/v10/configuring-npm/package-json#github-urls) as a dependency to fetch the latest version, but keep in mind that the entire library is deprecated and there are no plans to maintain it.

Publishing this library to the public NPM registry under a different name and encouraging other users using unmaintained package is not recommended.

## Development

    npm install     # install dependencies
    npm run test    # run tests and build file for debugging in browser
    npm run watch   # watch ./src dir and automatically rebuild file for debugging

## TypeScript

You can install <a target="_blank" href="https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/hull.js">third-party TypeScript definitions</a> via `npm install --save @types/hull.js`.

## Related papers

* <a target="_blank" href="http://www.it.uu.se/edu/course/homepage/projektTDB/ht13/project10/Project-10-report.pdf">Implementation of a fast and efficient concave hull algorithm</a>.
* <a target="_blank" href="http://www.cs.jhu.edu/~misha/Fall05/09.13.05.pdf">Computational Geometry: Convex Hulls</a>.
* <a target="_blank" href="https://en.wikibooks.org/wiki/Algorithm_Implementation/Geometry/Convex_hull/Monotone_chain">Andrew's monotone chain convex hull algorithm</a>.
* <a target="_blank" href="http://bryceboe.com/2006/10/23/line-segment-intersection-algorithm/">Line Segment Intersection Algorithm</a>.
* <a target="_blank" href="http://allenchou.net/2013/07/cross-product-of-2d-vectors/">Game Math: "Cross Product" of 2D Vectors</a>.
* <a target="_blank" href="http://users.livejournal.com/_winnie/237714.html">Угол между двумя векторами</a>.
* <a target="_blank" href="http://habrahabr.ru/post/105882/">Когда не нужна тригонометрия</a>.

## Changelog

<details>
    <summary>Expand</summary>

### 1.0.12 - 26.01.2025
- Some cleanup and deprecation.
### 1.0.11 - 11.12.2024
- Minor fixes in package.json.
### 1.0.10 - 07.11.2024
- Fix vulnerability issue.
### 1.0.9 - 29.10.2024
- Update NPM dependencies to address vulnerability issues.
### 1.0.8 - 31.05.2024
- Deprecate library on [npmjs registry](https://docs.npmjs.com/cli/v10/using-npm/registry).
### 1.0.7 - 03.05.2024
Squash previous tiny releases into one bigger commit with the following minor changes:
- Fix issue with formatting when users pass less than 4 points as an input.
- Remove bower and travis files as they are deprecated.
### 1.0.2 — 26.09.2021
- Clean up .gitignore.
- Add "debug" folder to .npmignore to reduce tarball size.
### 1.0.1 — 24.10.2020
- Fix that avoids hitting stack size limit on large arrays.
### 1.0.0 — 28.06.2019
- Change language level to ES6.
- Performance improvements.
### 0.2.11 — 05.05.2019
- Minor changes: return the first point as the last point when fewer than 4 unique points are provided.
### 0.2.10 — 04.09.2016
- Minor changes: fix missing "var" declaration.
### 0.2.9 — 28.07.2016
- Fix modification of the initial array.
- Add filtration of the duplicates.
### 0.2.8 — 01.04.2016
- Add edgeSkipList to increase performance of the highly accurate shapes (with the small `concavity` number) + some refactoring.
### 0.2.7 — 01.05.2015
- Minor changes: fix bower.json.
### 0.2.6 — 01.05.2015
- Minor changes: fix bower.json.
### 0.2.5 — 01.05.2015
- Minor changes: Bower support.
### 0.2.4 — 23.03.2015
- Minor changes: copyrights.
### 0.2.3 — 04.02.2015
- Minor changes: readme, package.json.
### 0.2.2 — 04.02.2015
- Configurable point format, now you can use points like `{x: 10, y: 10}` and `{lat: 52, lng: 82}`.
### 0.2.1 — 21.10.2014
- Minor changes: doc, package.json, etc.
### 0.2.0 — 20.10.2014
- Second version with better performance inspired by <a href="http://www.it.uu.se/edu/course/homepage/projektTDB/ht13/project10/Project-10-report.pdf" target="_blank">this</a> article.
### 0.1.0 — 06.09.2014
- First version based on Delaunay triangulation.
</details>
