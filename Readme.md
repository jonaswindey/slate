

<p align="center"><img src="support/banner.png" /></p>

<p align="center">A <em>completely</em> customizable framework <br/>for building rich text editors in the browser.</p>
<br/>
<br/>

<p align="center"><a href="#principles">Principles</a> • <a href="#examples">Examples</a> • Plugins • <a href="#documentation">Documentation</a> • Contributing</p>
<br/>
<br/>

Slate is like a pluggable implementation of `contenteditable`, built with React and Immutable. It lets you build editors like [Medium](https://medium.com/), [Dropbox Paper](https://www.dropbox.com/paper), or [Canvas](https://usecanvas.com/). And was inspired by libraries like [Draft.js](https://facebook.github.io/draft-js/) and [Prosemirror](http://prosemirror.net/).

_Slate is currently in **beta**, while work is being done on: cross-browser support, atomic node support, and collaboration support. It's useable now, but you might need to pull request one or two fixes for your use case._


## Principles

1. **First-class plugins.** The most important part of Slate is that plugins are first-class entities—the core editor logic is even implemented as its own plugin. That means you can _completely_ customize the editing experience, to build complex editors like Medium's or Canvas's without having to fight against the library's assumptions.

2. **Schema-less core.** Slate's core logic doesn't assume anything about the schema of the data you'll be editing, which means that there are no assumptions baked into the library that'll trip you up when you need to go beyond basic usage.

3. **Nested document model.** The document model used for Slate is a nested, recursive tree, just like the DOM itself. This means that creating complex components like tables or nested block quotes are possible for advanced use cases. But it's also easy to keep it simple by only using a single level of hierachy.

4. **Stateless and immutable.** By using React and Immutable.js, the Slate editor is built in a stateless fashion using immutable data structures, which leads to better performance, and also a much easier time writing plugins.

5. **Collaboration friendly.** The data model Slate uses—specifically how transforms are applied to the document—has been designed to allow for collaborative editing to be layered on top, so you won't need to rethink everything if you decide to make your editor collaborative.


## Examples

To get a sense for how you might use Slate, check out a few of the examples:

- [**Plain text**](examples/plain-text) — showing the most basic case: a glorified `<textarea>`.
- [**Rich text**](examples/rich-text) — showing the features you'd expect from a basic editor.
- [**Auto-markdown**](examples/auto-markdown) — showing how to add key handlers for Markdown-like shortcuts.
- [**Links**](examples/links) — showing how wrap text in inline nodes with associated data.
- [**Images**](examples/images) — showing how to use void (text-less) nodes to add images.
- [**Hovering menu**](examples/hovering-menu) — showing how a contextual hovering menu can be implemented.
- [**Tables**](examples/tables) — showing how to nest blocks to render more advanced components.
- [**Paste HTML**](examples/paste-html) — showing how to use an HTML serializer to handle pasted HTML.
- [**Code Highlighting**](examples/code-highlighting) — showing how to use decorators to dynamically mark text.

If you have an idea for an example that shows a common use case, pull request it!


## Documentation

If you're using Slate for the first time, check out the [Getting Started](./docs/getting-started) guide and the [Core Concepts](./docs/concepts) to familiarize yourself with Slate's architecture and mental models:

- [**Getting Started**](docs/getting-started.md)
  - Installing Slate
  - Adding Slate to Your App
  - Customizing Slate's Behavior
  - Adding Plugins
- **Core Concepts**
  - Statelessness & Immutability
  - [The Document Model](docs/getting-started.md#the-document-model)
  - The Selection Model
  - Plugins

Once you've gotten familiar with those, you'll probably want to check out the full [API Reference](./docs/reference):

- **API Reference**
  - Components
    - Editor
  - Models
    - Block
    - Character
    - Data
    - Document
    - Inline
    - Mark
    - Node
    - Selection
    - State
    - Text
    - Transform
  - Plugins

If even that's not enough, you can always [read the source itself](./lib), which is explained along with a handful of readme's.
