# Statamic Anchor Navigation

A Statamic addon that provides a custom tag for creating an anchor nav for all headings generated by the bard editor.

## Features

- Extends the TipTap heading node and adds a slugified ID to all configured heading levels (defaults to h2).
- The `{{ anchor_navigation }}` tag makes it easy to build an anchor navigation for all headings within your bard content.

## How to install

Run the following command from your project root:

``` bash
composer require visuellverstehen/statamic-anchor-navigation
```

## How to use

Include the `{{ anchor_navigation }}` tag in your template and supply the field handle of your bard field.
```
<ul>
    {{ anchor_navigation from="bard" }}
        <li>
            <a href="#{{ id }}">{{ headline }}</a>
        </li>
    {{ /anchor_navigation }}
</ul>
```

You can get the amount of headings found within the content with the `count` tag:

```
{{ if {anchor_navigation:count from="bard"} > 0 }}
    ...
{{ /if }}
```

## Configurations

You can define which heading levels should be included in your anchor navigation. Level 2 headings are set as a default.
```
'heading' => [
    'levels' => [2],
],
```

## More about us

- [www.visuellverstehen.de](https://visuellverstehen.de)

## License
The MIT license (MIT). Please take a look at the [license file](LICENSE.md) for more information.

