> [!note]

> [!tip]

> [!faq]

> [!todo]

> [!example]

> [!abstract]

> [!info]

> [!success]

> [!Warning]

> [!Failure]

> [!danger]

> [!bug]

> [!quote]


### Customize callouts

[CSS snippets](https://help.obsidian.md/snippets) and [Community plugins](https://help.obsidian.md/community-plugins) can define custom callouts, or even overwrite the default configuration.

To define a custom callout, create the following CSS block:

```css
.callout[data-callout="custom-question-type"] {
    --callout-color: 0, 0, 0;
    --callout-icon: lucide-alert-circle;
}
```

The value of the `data-callout` attribute is the type identifier you want to use, for example `[!custom-question-type]`.

- `--callout-color` defines the background color using numbers (0–255) for red, green, and blue.
- `--callout-icon` can be an icon ID from [lucide.dev](https://lucide.dev), or an SVG element.

> [!warning] Note about lucide icon versions
>
> Obsidian updates Lucide icons periodically. The current version included is shown below; use these or earlier icons in custom callouts.  
>
> Version `0.446.0`  
> ISC License
> Copyright (c) 2020, Lucide Contributors

> [!tip] SVG icons
>
> Instead of using a Lucide icon, you can also use a SVG element as the callout icon.
>
> ```css
> --callout-icon: '<svg>...custom svg...</svg>';
> ```

