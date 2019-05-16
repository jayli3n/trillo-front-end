# [Trillo Hotel Booking - Front End](https://jayli3n.github.io/trillo-front-end/ "Trillo Hotel Booking - Front End")
`Live:` https://jayli3n.github.io/trillo-front-end/

A mockup hotel booking site. Completed with HTML & CSS.

## Features
- Fully responsive
- HTML and SASS only
- Uses **7-1 sass pattern** & **BEM** to create scalable and maintainable code.

###  Overview
----
Designed by Jonas Schmedtmann, implemented by me.

[![overview](https://github.com/jayli3n/trillo-front-end/blob/master/README_resources/overview.jpg?raw=true "overview")](https://github.com/jayli3n/trillo-front-end/blob/master/README_resources/overview.jpg?raw=true "overview")

#### Responsiveness:
---
The website is fully responsive thanks to `flexbox`.

[![responsive demo](https://github.com/jayli3n/trillo-front-end/blob/master/README_resources/gif05.gif?raw=true "responsive demo")](https://github.com/jayli3n/trillo-front-end/blob/master/README_resources/gif05.gif?raw=true "responsive demo")


#### Hover Menues:
---
Hover menues are created with a `div` that is positioned `absolute`, and appears when hovered.

[![search hover menu ](https://github.com/jayli3n/trillo-front-end/blob/master/README_resources/gif03.gif?raw=true "search hover menu ")](https://github.com/jayli3n/trillo-front-end/blob/master/README_resources/gif03.gif?raw=true "search hover menu ")

###### Closer look:

[![hover menu](https://github.com/jayli3n/trillo-front-end/blob/master/README_resources/gif04.gif?raw=true "hover menu")](https://github.com/jayli3n/trillo-front-end/blob/master/README_resources/gif04.gif?raw=true "hover menu")


#### Buttons Animations:
---
This is achieved by placing a `::before` pseudo element right ontop of the button anchor text. This pseudo element is initially at the far left, when hovered, it expands and fills it&apos;s parent&apos;s full width.

[![button animations](https://github.com/jayli3n/trillo-front-end/blob/master/README_resources/gif02.gif?raw=true "button animations")](https://github.com/jayli3n/trillo-front-end/blob/master/README_resources/gif02.gif?raw=true "button animations")

```scss
&__item::before{
		content: "";
		position: absolute;
		top: 0;
		left: 0;
		height: 100%;
		width: 3px;
		background-color: var(--color-primary);
		transform: scaleY(0);

		transition: transform .2s, 
					width .3s cubic-bezier(1,0,0,1) .3s,
					background-color .1s;
	}

	&__item--active::before,
	&__item:hover::before{
		transform: scaleY(1);
		width: 100%;
	}

	&__item:active::before{
		background-color: var(--color-primary-light);
	}
```


## NPM Dev Packages:
```json
"devDependencies": {
    "autoprefixer": "^9.5.1",
    "concat": "^1.0.3",
    "node-sass": "^4.11.0",
    "npm-run-all": "^4.1.5",
    "postcss-cli": "^6.1.2"
  }
```

## Handy NPM Scripts:
```json
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "watch-sass": "node-sass ./sass/main.scss ./css/style.css -w",
    "live-server": "live-server",
    "start": "npm-run-all --parallel watch-sass live-server",
    "compile-sass": "node-sass ./sass/main.scss ./css/style.comp.css",
    "concat-css": "concat -o ./css/style.concat.css ./css/style.comp.css ./css/icon-fonts.css",
    "prefix-css": "postcss --use autoprefixer -b 'last 10 versions' ./css/style.concat.css -o ./css/style.prefix.css",
    "compress-css": "node-sass ./css/style.prefix.css ./css/style.min.css --output-style compressed",
    "build-css": "npm-run-all compile-sass concat-css prefix-css compress-css"
  }
```
