# Notes Site

This is a site for my university notes, written in MDX

You can find the markdown for all the lectures in the `notes` directory, and all the images in the `public` directory. When adding styles you can use [Tailwind CSS](https://tailwindcss.com/).

## Issues
There are some issues which as far as I can tell are pretty much out of my control. They exist in differences between the rendering of Firefox and Chrome. I don't have an Apple device so I have no idea how things look on Safari.

* Extra space at the end of code blocks on Firefox. This is resolved in the pull request in Tailwind CSS Typography [here](https://github.com/tailwindlabs/tailwindcss-typography/pull/41), just waiting on that

* Wide tables cause extra width on Chrome. This is a strange bug that doesn't appear on Firefox. Despite having overflow auto on the tables, there is whitespace where the table would otherwise be. 

* On Firefox mobile, when scrolling up, there is a tiny gap between the top of the navbar and the top of the viewport you can see the text scrolling through

## Workarounds

In the React components, newline characters need to be inserted manually until I work out how to fix this, so follow the example below

```js
<Definition name="Sequential Consistency">
{`- The interleaved sequence of operations meets the specification of a (single) correct copy of the contents 
  
- The order of operations in the interleaving is consistent with the program order in which each individual process executed them`}
</Definition>
```
## Conversion

When converting from LaTeX notes, the best tool to use is pandoc, passing the `latex+raw_tex` flag under `-f` will leave in anything that can't be converted, which is useful for custom environments. Passing the `markdown-smart` flag under `-t` will stop quotes being escaped etc, reducing the work to tidy things.
