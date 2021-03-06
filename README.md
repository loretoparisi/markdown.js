# markdown.js
Simple Markdown to HTML Visualizer/Editor with Code Syntax Highlighting and JSON Viewer.

## Why another markdown visualizer?
Because I did not find any all-in-one solution to live render a HTML page from a markdown page, featuring code highlighting and eventually rendering JSON snippets.

## How it works
It uses [Highlight.js](https://highlightjs.org/) as Code Syntax Highligher, [Markdown-js](https://github.com/evilstreak/markdown-js) as Markdown parser to HTML, and [PrettyJSON](https://github.com/warfares/pretty-json) to format the JSON object to the HTML page.

## About Markdown
John Gruber's Markdown Syntax Documentation [here](https://daringfireball.net/projects/markdown/syntax)

## How to Build
To build the example you can use `yarn` or `npm install`.

## How To Run
To run example you can use `yarn watch` or `npm run watch`.

## Example
The example shows a simple markdown page with markdown, some code and a json visualization output.
![screencapture-localhost-1234-2018-07-31-22_55_53](https://user-images.githubusercontent.com/163333/43486762-ecde010e-9514-11e8-85af-66c28c2ba324.png)


## Disclaimer
Both Markdown-js and PrettyJSON have been modified to be modularized with babel.
