---
title: "Typography"
date: "2019-01-17"
author: "Yashraj Mishra"
path: "/typography"
---
## Instruction to Create Post

​install [Marktext](https://marktext.app/)

​Download MarkDown [Sample File](https://raw.githubusercontent.com/JU-eezy/CDN/master/Sample-blog-structure.md)

​Edit Blog.md

​Mail file to **[JU eezy](mailto:info@jueezy.rocks?Subject=Blog%20post)**

## Header 2

Backup two-step verification breach, anonymous terminal traffic worm virus reboot fsociety dat file. Traffic fsociety malware 100 terabytes system hack, delete brute-force cyber security fiber connection connect code worm wipe. Cyber security off the grid delete IP decrypt, **nodes connect password 100 terabytes RUDY attack malicious code** rootkit gigabit speed. Tor connect network, intercepting traffic off the grid IP protocol password.

> Backup DDoS attack rootkit nodes disconnect website. Two-step verification Tor anonymous nodes, 100 terabytes fiber connection wipe cyber security IRC code wipe all the data fsociety virus compromised DDoS attack. Sys admin data center gigabit speed breach, worm DDoS attack AFK nodes.

### Header 3

Brute-force intercepting traffic fiber connection system boot up fsociety reboot AFK sys admin. Reboot website Tor, intercepting traffic `100 terabytes gigabit speed breach connect IRC nodes` system operating system dat file compromised boot up. Data center decrypt password network disconnect. Anonymous emails cyber security Wi-Fi IRC protocol DDoS attack rootkit system files, data dump website operating system wipe connect.

```css
/* PostCSS code by PrismJS */

pre {
  background: #1a1a1d;
  padding: 20px;
  border-radius: 8px;
  font-size: 1rem;
  overflow: auto;

  @media (--phone) {
    white-space: pre-wrap;
    word-wrap: break-word;
  }

  code {
    background: none !important;
    color: #ccc;
    padding: 0;
    font-size: inherit;

    .dark-theme & {
      color: inherit;
    }
  }
}
```

```js
// JS code by PrismJS

const menuTrigger = document.querySelector('.menu-trigger')
const menu = document.querySelector('.menu')
const mobileQuery = getComputedStyle(document.body).getPropertyValue('--phoneWidth')
const isMobile = () => window.matchMedia(mobileQuery).matches
const isMobileMenu = () => {
  menuTrigger.classList.toggle('hidden', !isMobile())
  menu.classList.toggle('hidden', isMobile())
}

isMobileMenu()

menuTrigger.addEventListener('click', () => menu.classList.toggle('hidden'))

window.addEventListener('resize', isMobileMenu)
```

```html
<section id="main">
  <div>
   <h1 id="title">{{ .Title }}</h1>
    {{ range .Pages }}
        {{ .Render "summary"}}
    {{ end }}
  </div>
</section>
```

```bash
npm install
```


#### Header 4

Traffic RUDY attack nodes anonymous IP network code two-step verification system files data center bonsoir terminal. Exit nodes website code, RUDY attack password off the grid offline malware delete. Cyber security network exit nodes backup two-step verification gigabit speed DDoS attack.

- Fsociety delete malicious code nodes.
- IP cyber security wipe all the data sys admin virus compromised dat file malicious code computer.
- Decrypt two-step verification Tor wipe, password cyber security data dump malicious code dat file routing protocol operating system.
- Anonymous boot up website AFK.
  - Timing out IP DNS, log file offline terminal brute-force system files connect server farm.
  - Reboot sys admin worm log file wipe.

`youtube: 6okxuiiHx2w`

Tor boot up backup anonymous bonsoir IRC website. Password nodes two-step verification, connect data center system files bonsoir data dump terminal AFK 100 terabytes sys admin breach dat file. Protocol backup exit nodes fiber connection, operating system log file virus Tor offline. Password data center two-step verification disconnect IRC terminal. Tor IRC cyber security AFK protocol traffic disconnect. Code exit nodes IRC cyber security nodes worm.

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam nec interdum metus. Aenean rutrum ligula sodales ex auctor, sed tempus dui mollis. Curabitur ipsum dui, aliquet nec commodo at, tristique eget ante.

| Tables        |      Are      |   Cool |
| ------------- | :-----------: | -----: |
| col 3 is      | right-aligned | \$1600 |
| col 2 is      |   centered    |   \$12 |
| zebra stripes |   are neat    |    \$1 |

**Donec quis dolor nec nunc mollis interdum vel in purus**. Sed vitae leo scelerisque, sollicitudin elit sed, congue ante. In augue nisl, vestibulum commodo est a, tristique porttitor est. Proin laoreet iaculis ornare. Nullam ut neque quam.

> Fusce pharetra suscipit orci nec tempor. Quisque vitae sem sit amet sem mollis consequat. Sed at imperdiet lorem. Vestibulum pharetra faucibus odio, ac feugiat tellus sollicitudin at. Pellentesque varius tristique mi imperdiet dapibus. Duis orci odio, sodales lacinia venenatis sit amet, feugiat et diam.

Sed a leo id risus venenatis vulputate non quis nulla. Aenean nisl quam, lacinia pulvinar orci sit amet, eleifend eleifend dui. Nulla tempor ligula leo, eu vehicula quam condimentum a. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Nulla gravida tristique nunc sed semper. Morbi nec felis odio.

- Sed efficitur, lacus ac scelerisque pellentesque, lectus risus dignissim nisl, fermentum semper lectus diam eget lacus.
- Nunc ornare purus enim, id eleifend mauris vestibulum volutpat.
- Aenean facilisis ut ipsum condimentum ultrices.
- Fusce sed metus vulputate, lobortis purus et, finibus purus. Suspendisse quis posuere lorem. Vivamus vulputate nec risus in pulvinar.

#### Usage of Code in Markdown

This is some beautiful code:

````markdown
```javascript
// In your gatsby-config.js
plugins: [
  {
    resolve: `gatsby-transformer-remark`,
    options: {
      plugins: [
        `gatsby-remark-prismjs`,
      ]
    }
  }
]
```
````

### [Line numbering](https://www.gatsbyjs.org/packages/gatsby-remark-prismjs/#line-numbering)

To see the line numbers alongside your code, you can use the `numberLines` option:

````markdown
```javascript{numberLines: true}
// In your gatsby-config.js
plugins: [
  {
    resolve: `gatsby-transformer-remark`,
    options: {
      plugins: [
        `gatsby-remark-prismjs`,
      ]
    }
  }
]
```
````

You can also start numbering at any index you wish (here, numbering will start at index 5):

````markdown
```javascript{numberLines: 5}
// In your gatsby-config.js
plugins: [
  {
    resolve: `gatsby-transformer-remark`,
    options: {
      plugins: [
        `gatsby-remark-prismjs`,
      ]
    }
  }
]
```
````

### [Line highlighting](https://www.gatsbyjs.org/packages/gatsby-remark-prismjs/#line-highlighting)

You can also add line highlighting. It adds a span around lines of code with a special class `.gatsby-highlight-code-line` that you can target with styles. See this README for more info.

To highlight lines, you can use one of the following directives as comments in your code:

- `highlight-line` highlights the current line;
- `highlight-next-line` highlights the next line;
- `highlight-start` highlights the lines until the matching `hightlight-end`;
- `highlight-range{1, 4-6}` will highlight the next line, and the fourth, fifth and sixth lines.

````markdown
```jsx
class FlavorForm extends React.Component { // highlight-line
  constructor(props) {
    super(props);
    this.state = {value: 'coconut'};

    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    // highlight-next-line
    this.setState({value: event.target.value});
  }

  // highlight-start
  handleSubmit(event) {
    alert('Your favorite flavor is: ' + this.state.value);
    event.preventDefault();
  }
  // highlight-end

  render() {
    return (
      { /* highlight-range{1,4-9,12} */ }
      <form onSubmit={this.handleSubmit}>
        <label>
          Pick your favorite flavor:
          <select value={this.state.value} onChange={this.handleChange}>
            <option value="grapefruit">Grapefruit</option>
            <option value="lime">Lime</option>
            <option value="coconut">Coconut</option>
            <option value="mango">Mango</option>
          </select>
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}
```
````

You can also specify the highlighted lines outside of the code block. In the following code snippet, lines 1 and 4 through 6 will get the line highlighting. The line range parsing is done with [https://www.npmjs.com/package/parse-numeric-range](https://www.npmjs.com/package/parse-numeric-range).

````markdown
```javascript{1,4-6}
// In your gatsby-config.js
plugins: [
  {
    resolve: `gatsby-transformer-remark`,
    options: {
      plugins: [
        `gatsby-remark-prismjs`,
      ]
    }
  }
]
```
````

### [Shell prompt](https://www.gatsbyjs.org/packages/gatsby-remark-prismjs/#shell-prompt)

To show fancy prompts next to shell commands (only triggers on `bash`), either set `prompt.global` to `true` in `gatsby-config.js`, or pass at least one of `{outputLines: <range>}`, `{promptUser: <user>}`, or `{promptHost: <host>}` to a snippet

By default, every line gets a prompt appended to the start, this behaviour can be changed by specifying `{outputLines: <range>}` to the language.

````markdown
```bash{outputLines: 2-10,12}
````

The user and host used in the appended prompt is pulled from the `prompt.user` and `prompt.host` values, unless explicitly overridden by the `promptUser` and `promptHost` options in the snippet, e.g.:

````markdown
```bash{promptUser: alice}{promptHost: dev.localhost}
````

### [Line hiding](https://www.gatsbyjs.org/packages/gatsby-remark-prismjs/#line-hiding)

As well as highlighting lines, it’s possible to *hide* lines from the rendered output. Often this is handy when using `gatsby-remark-prismjs` along with [`gatsby-remark-embed-snippet`](https://www.gatsbyjs.org/packages/gatsby-remark-embed-snippet/).

As with highlighting lines, you can control which lines to hide by adding directives as comments in your source code.

The available directives are:

- `hide-line` hides the current line;
- `hide-next-line` hides the next line;
- `hide-start` hides the lines until the matching `hide-end`;
- `hide-range{1, 4-6}` will hide the next line, and the fourth, fifth and sixth lines.

The hide-line directives will always be hidden too. Check out [the using-remark example site](https://using-remark.gatsbyjs.org/embed-snippets/) to see how this looks on a live site.

### [Inline code blocks](https://www.gatsbyjs.org/packages/gatsby-remark-prismjs/#inline-code-blocks)

In addition to fenced code blocks, inline code blocks will be passed through PrismJS as well.

If you set the `inlineCodeMarker`, then you can also specify a format style.

Here’s an example of how to use this if the `inlineCodeMarker` was set to `±`:

```markdown
I can highlight `css±.some-class { background-color: red }` with CSS syntax.
```

This will be rendered in a `<code class=language-css>` with just the (syntax highlighted) text of `.some-class { background-color: red }`

**Supported languages**: bash/shell, css, clike, javascript, apacheconf, actionscript, applescript, c, csharp, cpp, coffeescript, ruby, csp, css-extras, diff, django, docker, elixir, elm, markup-templating, erlang, fsharp, flow, git, go, graphql, less, handlebars, haskell, http, java, json, kotlin, latex, markdown, makefile, objectivec, ocaml, perl, php, php-extras, r, sql, processing, scss, python, jsx, typescript, toml, reason, textile, rust, sass, stylus, scheme, pug, swift, yaml, haml, twig, tsx, vim, visual-basic, wasm.