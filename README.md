[![JU-eezy](https://raw.githubusercontent.com/yashrajmishra/JU-eezy-Web/master/Support%20files/background.png)](https://jueezy.rocks)

# [JU-eezy](https://jueezy.rocks)

Website built with GatsbyJS.

## How to use it

- Clone this repo `git clone https://github.com/yashrajmishra/JU-eezy-Blog.git`
- `npm install` - install modules
- `npm run dev` - start for development
- `npm build` - build for production

## Features

- **dark/light mode**, depending on your preferences (dark is default, but you can change it)
- great reading experience thanks to [**Inter UI font**](https://rsms.me/inter/), made by [Rasmus Andersson](https://rsms.me/about/)
- nice code highlighting thanks to [**PrismJS**](https://prismjs.com)
- responsive youtube/vimeo etc. videos [gatsby-remark-embed-video](https://github.com/borgfriend/gatsby-remark-embed-video)
- fully responsive site

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

---

Designed By **[Yashraj Mishra](https://yashrajmishra.github.io)**
