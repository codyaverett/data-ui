# @data-ui/network

demo at <a href="https://williaster.github.io/data-ui" target="_blank">williaster.github.io/data-ui</a>

## Overview
This package exports declarative react `<Network />` implemented with <a href="vx-demo.now.sh" target="_blank">@vx</a> which can be used to render network.

### Usage
See the demo at <a href="https://williaster.github.io/data-ui" target="_blank">williaster.github.io/data-ui</a> for more example outputs.

<img width="500" alt="Network Visualization" src="https://user-images.githubusercontent.com/2024960/30942113-d1baa152-a39d-11e7-940f-f7780bf15fb9.gif">


### Tooltips
Tooltips are controlled with the `renderTooltip` function passed to `<Network />`. This function takes an object with the shape `{ event, index, id, data }` as input and is expected to return the inner _contents_ of the tooltip (not the tooltip container!) as shown above. If this function returns a `falsy` value, a tooltip will not be rendered.

Under the covers this will wrap the `<Network />` component in the exported `<WithTooltip />` HOC, which wraps the `svg` in a `<div />` and handles the positioning and rendering of an HTML-based tooltip with the contents returned by `renderTooltip()`. This tooltip is aware of the bounds of its container and should position itself "smartly".

### Roadmap
- more layout algorithms
- dragging interaction enabled
