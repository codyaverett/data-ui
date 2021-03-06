# Changelog
- [v0.0.50](#v0050)
- [v0.0.49](#v0049)
- [v0.0.48](#v0048)
- [v0.0.47](#v0047)

## v0.0.50
🏆 Enhancements

[xy-chart]
- Ability to "snap" the tooltip to the `x` or `y` value of a datum, by setting `snapTooltipToDataX` and/or `snapTooltipToDataY`. fixes #77 [#81](https://github.com/williaster/data-ui/pull/81)
- Support for using the chart _container_ for mouse events, instead of series or a voronoi. this is now set with the `eventTrigger` prop as `'series'` [default], `'voronoi'`, or `'container'`. [#81](https://github.com/williaster/data-ui/pull/81)
- The addition of container events necessitates shared tooltips, i.e., tooltips that contain data for for all series for the hovered x value. fixes #78 [#81](https://github.com/williaster/data-ui/pull/81)
- Ability to programmatically trigger events using the `eventTriggerRefs` callback (see updated `<LineSeriesExample />` for an example) [#81](https://github.com/williaster/data-ui/pull/81)
- adds `innerRef` prop which is set on the inner `svg` [#81](https://github.com/williaster/data-ui/pull/81)

[shared]
- the signature of `onMouseMove` in `<WithTooltip />` now accepts an optional `coords` object of the shape `{ x: Number, y: Number }`. If either or both of `x` or `y` is specified they will be used to set the the tooltips `left` and `top` instead of the `event`'s coordinates. [#81](https://github.com/williaster/data-ui/pull/81)

[forms] 
- adds `active` prop to `<Button />` [#81](https://github.com/williaster/data-ui/pull/81)

💔 Breaking Changes
- [xy-chart] the `<XYChart />` `useVoronoi` prop is removed. instead use `eventTrigger='voronoi` [#81](https://github.com/williaster/data-ui/pull/81)

📜 Documentation
- [xy-chart] documents the above enhancements [#81](https://github.com/williaster/data-ui/pull/81)

🏠 Internal
[xy-chart] 
- moves `<XYChart />` static method to their own utils files [#81](https://github.com/williaster/data-ui/pull/81)
- breaks out several functions in `chartUtils` into their own files [#81](https://github.com/williaster/data-ui/pull/81)
- adds and uses `sharedSeriesProps` [#81](https://github.com/williaster/data-ui/pull/81)

🐛 Bug Fix
- Fixes a bug where `tickLabelProps` is not used when passed in either `<XAxis />` or `<YAxis />`. This prop enables per-tick styles so is importanté! [#82](https://github.com/williaster/data-ui/pull/82)

## v0.0.49
🏆  Enhancements
- Allows additional customization Adds `tooltipProps` to the `<WithTooltip />`which will be passed to its `TooltipComponent` (and adds example in demo) [#79](https://github.com/williaster/data-ui/pull/79)
- Exposes `@vx/responsive`'s [new observer-based `<ParentSize />` HOC](https://github.com/hshoff/vx/pull/198) [#79](https://github.com/williaster/data-ui/pull/79)
- Exposes the following props on `<BoxplotSeries />` to enable more customization: `containerProps`, `boxProps`, `outlierProps`, `minProps`, `maxProps`, `medianProps` (https://github.com/hshoff/vx/pull/198) [#80](https://github.com/williaster/data-ui/pull/80)
- Adds the ability to set mouse events on the boxplot container or on its component parts (whiskers, etc) [#80](https://github.com/williaster/data-ui/pull/80)
- Consolidates some of examples for [demo][boxplot] [#80](https://github.com/williaster/data-ui/pull/80)

🐛  Bug fix
- bumps `@vx/tooltip` to 0.0.148 for [bounds bug fix](https://github.com/hshoff/vx/pull/204) [#79](https://github.com/williaster/data-ui/pull/79)

```
Changes
 - @data-ui/demo: 0.0.48 => 0.0.49 (private)
 - @data-ui/event-flow: 0.0.48 => 0.0.49
 - @data-ui/histogram: 0.0.48 => 0.0.49
 - @data-ui/network: 0.0.48 => 0.0.49
 - @data-ui/radial-chart: 0.0.48 => 0.0.49
 - @data-ui/shared: 0.0.48 => 0.0.49
 - @data-ui/sparkline: 0.0.48 => 0.0.49
 - @data-ui/xy-chart: 0.0.48 => 0.0.49
```

## v0.0.48
💔 Breaking Changes
- [xy-chart] use `seriesKey` instead of `key` in `onMouseMove` event signature (relevant to `StackedAreaSeries`, `StackedBarSeries`, and `GroupedBarSeries` only) #73 

🏆 Enhancements
- [xy-chart] add `<StackedAreaSeries />` and example #74 
- [xy-chart] add `onClick` support to all series and voronoi #74
- [xy-chart] remove previously-required `label` prop from series #74
- [shared][tooltip] don't render a tooltip if the output of renderTooltip is `falsy` #73
- [demo] add `<LinkedXYCharts />` example with custom click handling and mouse overs #74
- [demo] add `disableMouseEvents` prop to all series #74
- removes enumeration of `@data-ui` packages in `readme`s #74

🐛 Bug Fix
- fix an offset bug for `BarSeries` with band scales #74

🏠 Internal
- [shared] bump `@vx/tooltip` to `0.0.147` for [smarter tooltips](https://github.com/hshoff/vx/blob/master/CHANGELOG.md#v00147) #74

```
 - @data-ui/data-table: 0.0.25 => 0.0.48
 - @data-ui/theme: 0.0.47 => 0.0.48
 - @data-ui/demo: 0.0.47 => 0.0.48 (private)
 - @data-ui/event-flow: 0.0.47 => 0.0.48
 - @data-ui/histogram: 0.0.47 => 0.0.48
 - @data-ui/network: 0.0.47 => 0.0.48
 - @data-ui/radial-chart: 0.0.47 => 0.0.48
 - @data-ui/shared: 0.0.47 => 0.0.48
 - @data-ui/sparkline: 0.0.47 => 0.0.48
 - @data-ui/xy-chart: 0.0.47 => 0.0.48
```

## v0.0.47

🎉 Finally syncing versions across packages! Will be easier to maintain the changelog :)

📈 Enhancements
- [sparkline] add support for tooltips #72 
- [xy-chart] add support for area bands in <AreaSeries /> #71 
- [shared] add package, move <WithTooltip /> all @data-ui packages to @data-ui/shared #72 

📜 Documentation
- [sparkline] update docs for tooltips

🏋️ Internal
- [xy-chart] absolute imports for all @vx components

Changes:
``` 
 - @data-ui/theme: 0.0.9 => 0.0.47
 - @data-ui/demo: 0.0.46 => 0.0.47 (private)
 - @data-ui/event-flow: 0.0.11 => 0.0.47
 - @data-ui/histogram: 0.0.8 => 0.0.47
 - @data-ui/network: 0.0.6 => 0.0.47
 - @data-ui/radial-chart: 0.0.11 => 0.0.47
 - @data-ui/shared: 0.0.0 => 0.0.47
 - @data-ui/sparkline: 0.0.3 => 0.0.47
 - @data-ui/xy-chart: 0.0.25 => 0.0.47
 ```
