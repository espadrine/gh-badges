# GitHub badges in SVG format

[![npm version](http://b.adge.me/npm/v/gh-badges.svg)](https://npmjs.org/package/gh-badges)

Make your own badges (like this one above)! <http://gh-badges.herokuapp.com>

# Contribute

If you want to add a badge, you only need to modify `default-badges.json`.

The format is the following:

```js
/* Unique name of your badge. */
"build-passed": {
  /* Textual information shown, in order. */
  "text": [ "build", "passed" ],
  "colorscheme": "green"
}
```

Color schemes are located in `colorscheme.json`. Each scheme has a name and
a [CSS/SVG color](http://www.w3.org/TR/SVG/types.html#DataTypeColor) for the
color used in the first box (for the first piece of text, field `colorA`) and
for the one used in the second box (field `colorB`).

```js
"green": {
  "colorB": "#4c1"
}
```

Both `colorA` and `colorB` have default values. Usually, the first box uses the
same dark grey, so you can rely on that default value by not providing a
`"colorA"` field (such as above).

You can also use the `"colorA"` and `"colorB"` fields directly in the badges if
you don't want to make a color scheme for it. In that case, remove the
`"colorscheme"` field altogether.

# Requirements

Because of the usage of the npm module [canvas](https://npmjs.org/package/canvas) *you need* to have **cairo** installed.

For more information check the [wiki](https://github.com/LearnBoost/node-canvas/wiki/_pages) of the canvas project with system-specific installation details.

# Making your Heroku badge server

Once you have installed the [Heroku Toolbelt](https://toolbelt.heroku.com/):

```bash
heroku login
heroku create your-app-name
heroku config:set BUILDPACK_URL=https://github.com/mojodna/heroku-buildpack-multi.git#build-env
cp /path/to/Verdana.ttf .
make deploy
heroku open
```

# Origin

See <https://github.com/h5bp/lazyweb-requests/issues/150>.

# License

All work here is licensed CC0.
