# ScottPlot Changelog
* This document contains release notes for every version of ScottPlot
* https://scottplot.net/versions/ describes the major versions of ScottPlot
* https://scottplot.net/changelog/ is a formatted version of this document

## ScottPlot 5.0.22
_Not yet on NuGet..._
* Rendering: Added additional options for gradient fills (#3324) _Thanks @KroMignon_
* Plot: Improve `GetPixel()` behavior when a custom `ScaleFactor` is in use (#3327) _Thanks @MCF_
* Fonts: Improve behavior of cached typefaces (#3334, #3335) _Thanks @Milkitic_
* Legend: Added support for horizontal orientation (#3341, #3302, #3280) _Thanks @KroMignon_
* Controls: Created `AddSeparator()` to facilitate creation of custom context menus (#3342) _Thanks @MCF_
* Live Data: Improved indexing of the `Wipe` view to prevent race conditions when displaying live data (#3352) _Thanks @drolevar_
* Radial Gauge Plot: Added a new plot type for displaying categorical data as circular gauges (#3358) _Thanks @arthurits_
* Generate: Improved `RandomNormalSample()` behavior by fixing an off-by-one indexing error _Thanks @DominicBeer_
* Avalonia: Redraw plots using a non-blocking background thread to improve multi-axis behavior (#3373, #3359) _Thanks @oktrue, @BendRocks, and @ykarpeev_
* Bar plot: Added a `Label` property to allow a collection of bars to be displayed as a single item in the legend (#3375) _Thanks @fhannan-ti_

## ScottPlot 5.0.21
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2024-01-28_
* RenderManager: Exposed `EnableRendering` to facilitate render locking in async environments (#3264, #3213, #3095) _Thanks @kagerouttepaso_
* Arrow: Added a new arrow plot type that can be used to mark a position in coordinate space (#3265) _Thanks @hockerschwan_
* Label: Improved measurement of text containing leading or tailing whitespace (#3223, #3268) _Thanks @KroMignon and @lindpatr_
* Axis Line: Added `LabelOppositeAxis` property and created dedicated cookbook page (#3275) _Thanks Lyakabynka_
* Plot: `AddRectangle()` now accepts more input types (#3263) _Thanks @enumer_
* Ticks: Created `IMinorTickGenerator` to allow users to inject their own logic for placing minor ticks
* Axes: Added support for log-scale tick labels and grid lines (#3143)
* Plot: Users can now `Add.Ellipse()` and `Add.Circle()` to place closed curves on plots (#3277, #3287) _Thanks @hockerschwan_
* Plot: Added `Plot.Remove()` overloads for removing all plottables of the given type (#3296, #3296) _Thanks @DerekGooding_
* Plot: Added `Plot.Remove()` overloads for removing plottables matching specific criteria (#3296, #3297) _Thanks @KroMignon_
* Plot: Added `Plot.GetPlottables()` overloads to facilitate iterating over plottables of a specific type
* Rendering: Added support for gradient fills (#3298, #3157, #3310) _Thanks @KroMignon, @hockerschwan, and @faguetan_
* Controls: Disabling interactions then re-enabling them restores original interactions (#3305, #3304) _Thanks @Nils-Berghs_
* Plot: Added `Plot.GetPixel()` overload for improved support on multi-axis plots (#3306) _Thanks @MCF_
* Axis Lines: Label background color may be distinct from line color (#3309) _Thanks @PhoenixChenLu_
* Axis Spans: New `Plot.Add.HorizontalSpan()` and `Plot.Add.VerticalSpan()` methods for shading axis ranges (#3307) _Thanks @erikjl_
* Interactivity: Added methods to simplify dragging axis lines and spans. See the demo application for details. (#3307) _Thanks @erikjl_
* Ticks: Improved tick density calculation to prevent overlapping tick labels for very large numbers (#3203)
* Axes: Deprecate `DateTimeTicks(Edge.Bottom)` in favor of `DateTimeTicksBottom()` which now returns the created axis.
* Cookbook: Demonstrate DateTime tick labels with custom string formatting (#3272, #3273) _Thanks @sterenas and @stratdev3_
* Demo: Added icon to main application and all windows launched within (#3281, #3273) _Thanks @sterenas_
* Controls: Do not list OpenGL controls in the toolbox. They can still be added programmatically, but they invite many problems and offer little performance improvements for most applications so their use is discouraged (#3282, #3262, #3271)
* WinForms: Disable design time visibility in .NET Framework projects to prevent Visual Studio error messages (#3300) _Thanks @MaxFun_
* Markers: Added `Plot.Add.Markers()` to display a collection of marker positions all using the same style (#3283)
* Axes: Added `Plot.Axes.Remove()` to allow users to remove additional axes they may have added (#3288) _Thanks Felix_
* Data Streamer and Data Logger: Renamed `IAxisManager` to `IAxisLimitManager` to disambiguate it from the `AxisManager` class (#3289)
* Pie: Added support for displaying slice label text above each slice (#3295) _Thanks @sterenas_
* Plot: `Save()` methods used to return the saved file path as a `string` but now they return a `SavedImageInfo` with a `Path` property and additional information (#3314)

## ScottPlot 5.0.20
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2024-01-21_
* Assembly: ScottPlot packages are now strongly named (#3235, #3241) _Thanks @mlessmann_
* Scatter Plot: Added a `ConnectStyle` to enable step display mode (#3242) _Thanks @NoahSigl_
* Polygon: `Plot.Add.Polygon()` now accepts generic type lists and arrays (#3244) _Thanks howhowone_23_
* Demo: Added a draggable points window to show how to drag points of a scatter plot (#3248) _Thanks bologna_
* Generate: Added `RandomNumber()` and `RandomNumbers()` overloads
* OHLC: Improved autoscaling behavior for empty datasets
* Generate: Added `RandomOHLCs()` overload that accepts a starting `DateTime` (#3254) _Thanks @CBrauer_
* Axes: Improved support for inverted axes (#3252) _Thanks @fujiangang_
* Finance: Improved performance of financial charts by not rendering symbols outside the data area (#3258) _Thanks Lyakabynka_
* SignalXY: Support vertical orientation (#3253) _Thanks @manaruto_
* Data logger and streamer: The property `Data` has been renamed to `DataSource` (#3260)
* SignalConst: The property `Data` has been renamed to `DataSource` (#3260)
* Axes: Added `AutoScaleExpand()` to zoom out to fit data only if necessary (#3259)
* Style: Added `Plot.Style.ColorLegend()` for quick customization of legend colors (#3247)
* Plot: Replacing palettes is now achieved by setting `Plot.Add.Palette` instead of `Plot.Palette`.
* Plot: Added `ShowLegend()` overload that accepts manually created legend items
* Scatter Plot: Added `LinePattern` property for customizing line style
* Pie: Improved default colors of pie charts created from discrete values

## ScottPlot 4.1.71
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2024-01-21_
* Assembly: All ScottPlot packages use the same strong name signing key (#3235, #3241) _Thanks @mlessmann_
* WPF Control: Routed events now pass the original source (#3243) _Thanks @MarekJur_

## ScottPlot 5.0.19
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2024-01-18_
* Plot: Improved render manager initialization (#3233) _Thanks @VoteForPedro_
* Projects: Sign all assemblies using strong names (#3235, #283) _Thanks @mlessmann_
* Axes: Improved automatic axis determination for plots containing non-real or infinite data limits (#3232, #3237)
* Bar Plots: Do not overwrite existing colors when adding `Bar` collections to the plot (#3231)
* Label: Clear cached typefaces when styles change (#3236) _Thanks @kl7107 and @prime167_

## ScottPlot 5.0.18
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2024-01-17_
* Axes: Improved default label rotation for DateTime axes (#3211, #3216) _Thanks @CBrauer_
* Fonts: Improved font detection for strings containing mixed-language characters (#3220, #3184, #2746) _Thanks @kl7107 and @prime167_
* Controls: Add a Reset function for context menus (#3224) _Thanks @MCF_
* Axes: Prevent exceptions when generating ticks for a DateTime axis with zero size (#3221) _Thanks @devbotas_
* SignalXY: Added `MinimumIndex` and `MaximumIndex` for partial array rendering (#3227)
* SignalXY: Added `OffsetX` and `OffsetY` for for applying a fixed offset in coordinate space (#3227)
* SignalConst: Improved display when signals are zoomed in enough to see individual points (#3228) _Thanks @Marvenix_

## ScottPlot 5.0.17
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2024-01-16_
* Rendering: Added a `RenderManager.EnableRendering` flag to skip render requests while performing dangerous actions in multi-threaded environments. Skipping renders compliments the `PreRenderLock` event which hangs renders. See the [async FAQ page](https://scottplot.net/faq/async/) for usage details. (#3213, #3095) _Thanks @LumAsWell and @bclehmann_
* WPF: Improved "Copy to Clipboard" functionality (#3214) _Thanks @MCF_
* Controls: Created `FormsPlotViewer` and `WpfPlotViewer` for launching interactive plots from console applications. See the [Interactive Plots in Console Applications](https://scottplot.net/faq/launch-console/) page for details. (#3212, #308) _Thanks @chaojian-zhang_
* DataLogger: Added `Add()` overloads which support X/Y pairs (#3210) _Thanks @devbotas_

## ScottPlot 5.0.16
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2024-01-15_
* Data Streamer: A new plot type for displaying live data as a fixed-width line trace (#3202, #3205)
* Data Logger: A new plot type for displaying live data as a growing scatter plot (#3202, #3205)
* Generate: Created a `Generate.RandomWalker` class for producing an infinite amount of streaming random data
* Ticks: Improved support for multi-line tick labels on vertical axes (#3208) _Thanks @raburton_
* Text: Exposed `FontName` and `LabelText` properties
* Internationalization: `Fonts.Detect()` now inspects all characters instead of just the first (#3184, #2746) _Thanks @prime167_
* Label: Added `SetBestFont()` to apply the installed font most likely able to display characters in the label (#3184, #2746) _Thanks @prime167_
* Style: Added `Plot.Style.SetBestFonts()` to apply the best font to all plot components (#3184, #2746) _Thanks @prime167_
* Controls: Removed `GetCoordinates()` from `IPlotControl`. Users can call Plot.GetCoordinates()` directly. (#3199)
* Ticks: Do not display manually defined grid lines, tick marks, or tick labels to appear outside the data area (#3207)
* Rendering: Created `IManagesAxisLimits` for `IPlottable` objects that manipulate axis limits at render time (#3207)
* NuGet: Improved package descriptions to better reflect that ScottPlot 5 is no longer in preview (#3207)

## ScottPlot 5.0.15
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2024-01-14_
* Ticks: Added additional styling options for axis tick labels (#3185) _Thanks @barnettben_
* Finance: Added `Sequential` property to display OHLC data without gaps (#2611, #3187) _Thanks @robbyls, @mjpz, and @segeyros_
* SignalConst: A high performance plot type for evenly-spaced unchanging data (#70, #3188) _Thanks @StendProg_
* Plot: Created `Plot.Add.Rectangle()` for placing a rectangular polygon on the plot
* Axis Rules: Improved `MaximumBoundary` and `MinimumBoundary` correction behavior (#3191) _Thanks @Milyczekpolsl_
* Bar Plot: Added support for horizontal bar graphs (#3192) _Thanks @sghctoma_

## ScottPlot 5.0.14-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2024-01-10_
* Rendering: Improved performance by limiting how often `AutoScale()` is called by the renderer (#3183) _Thanks @Smonze_

## ScottPlot 5.0.13-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2024-01-09_
* SignalXY: New high performance plot type for signal data with defined ascending X positions (#3163) _Thanks @ChristianWeigand_
* Scatter, Signal, and SignalXY: Improved support for generic data types
* Axis: Improve behavior of axis rules which reference axes from previous renders (#3179) _Thanks @raburton_
* Primitives: Separated `CoordinateRange` struct for passing ranges and `CoordinateRangeMutable` for mutating them (#3170)
* Function: Improved autoscaling behavior

## ScottPlot 5.0.12-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2024-01-07_
* Axes: Improved automatic axis scaling for plots containing 1D plottables (#3132)
* Coordinates: Added `AreReal` property to confirm `X` and `Y` are finite
* Crosshair: Added `X` and `Y` properties to compliment `Position`
* Axes: Removed `Plot.Axes` list to encourage interaction with `Plot.YAxes` and `Plot.XAxes` (#3133)
* Plot: Added `AddLeftAxis()`, `AddRightAxis()`, etc. to simplify multi-axis creation and management (#3133)
* Layout: Created `Plot.Layout.Frameless()` to hide axes and allow the data area to fill the figure
* Axes: Improve rotation for right axis labels
* Bar: Improve autoscaling for bar plots displaying error ranges
* Signal: Improved rendering of makers when plots are zoomed in (#3136)
* Signal: Exposed `Color`, `LineWidth`, and `MaximumMarkerSize` so users do not interact with `LineStyle` and `MarkerStyle` directly (#3136)
* Statistics: Created `Series` class for calculating statistics for time series data
* Scatter Plot: Added `LineWidth` and `MarkerSize` properties
* Finance: Created `SimpleMovingAverage` and `BollingerBands` in the `ScottPlot.Finance` namespace to facilitate calculation and display of technical indicators (#3137)
* Axes: Moved axis management logic from `Plot` into the `Plot.Axes` class. Notable changed method names include `Plot.Axes.SetLimits()`, `Plot.Axes.GetLimits()`, `Plot.Axes.AutoScale()`, and `Plot.Axes.Margins()` (#3140)
* Rendering: Improved anti-aliased drawing of solid shapes
* Axis: Added rules for zoom in/out boundaries, axis span limits, and square ratio locking (#3139, #3142)
* ErrorBar: Improved axis limit detection for data that does not start at zero (#3155) _Thanks @wolfcomp_
* DataSources: Created `SignalSourceUInt16` to demonstrate how to plot data with custom types (#3154) _Thanks @angulion_
* Signal Plot: Added support for generic type arrays and lists (#3154)
* Scatter Plot: Added support for generic types including Xs and Ys of different types (#3154)
* Scatter Plot: Added support for DateTime types (#3154)
* Style: Added support for more line patterns (#3161) _Thanks @MCF_
* Controls: Assigning `Interaction` can be used instead of `Replace()` for customizing mouse actions (#3150)
* Controls: Added `Menu` with `Add()` and `Clear()` methods to simplify context menu customization (#3150)
* Axes: Added rules for locking horizontal and/or vertical axes (#3160) _Thanks @raburton_
* Signal: Added `Data.MinimumIndex` and `Data.MaximumIndex` to allow for partial array rendering (#3158) _Thanks @raburton_
* Heatmap: Added `GetIndexes()` and `GetValue()` to get data from a coordinate (#3165) _Thanks @skn41_

## ScottPlot 5.0.11-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-12-29_
* Plot: `AutoScaler` can now be assigned a `FractionalAutoScaler` with custom properties (#3069, #3067) _Thanks @arthurits_
* Controls: add SVG to recommended save formats in the right-click menu (#3068)
* Bar: Refactored bar plots to simplify individual bar customization (#3070, #3066)
* Legend: Added `ManualItems` to allow building custom legend content
* Render: Prevent the pre-render auto-scaler from resetting manually defined axis limits (#3058)
* Cookbook: Rewrote reflection and source file parsing for simplified querying (#3081, #3080, #3079, #2962, #2755)
* Function: Added a new line plot type where Y position is a user defined function (#3094) _Thanks @bclehmann_
* Axes: Improved axis label alignment for secondary axes (#3030) _Thanks @albyoo_
* Statistics: Added generic overloads to `Statistics.Descriptive` class, renamed `StDev()` to `StandardDeviation()`, and added methods for calculating both sample and population statistics (#3071 and #3055) _Thanks @arthurits_
* Markers: Added a `None` marker (#3075, #3057) _Thanks @Gray-lab_
* Generate: Added methods for generating random marker shapes and colors
* Generate: `Random()` is deprecated in favor of `RandomSample()`
* Plot: Added `ShowLegend()` and `HideLegend()` helper methods which set `Plot.Legend.IsVisible`
* Marker Plot: `Plot.AddMarker()` can now be used to place a single marker on the plot (#3076, #2806) _Thanks @Gray-lab_
* Rendering: Fixed issue where disabling a plottable's visibility prevented rendering of subsequent plottables (#3097, #3089) _Thanks @KroMignon_
* SVG: Improved rendering of shadows by adding slight color to semitransparent black (#3098, #3063) _Thanks @KroMignon_
* Colormap: Added a `Reversed()` method for creating colormaps with reversed color order (#3100) _Thanks @bukkideme_
* Version: Added `ShouldBe()` method to assert the version of ScottPlot matches the expected one (#3093)
* Ticks: `TickGenerators.NumericManual` now has `AddMajor()` and `AddMinor()` to simplify manual tick placement (#3105, #2957) _Thanks Lake_
* Legend: Added `Plot.GetLegendImage()` and `Plot.GetLegendSvg()` for displaying legends outside plots (#3062, #2934) _Thanks @KroMignon, @lichen95, and @bclehmann_
* Plot: Added new `Line` plot type for creating straight lines between two points (#2915, #3109) _Thanks @Gray-lab_
* Controls: Added `IPlotInteraction` so users can inject their own `Interaction` (#3111, #3110) _Thanks @albyoo_
* Signal: Improved appearance of signal plots where `YOffset` is used (#2949) _Thanks @minjjKang_
* AxisLine: Improve rendering and simplify API by exposing common properties (#3060, #3056)
* Legend: `Alignment` has been renamed to `Location` (#3059)
* Box: Refactored box plot API to favor simplicity and user customization (#3072)
* Rendering: Added `RenderManager.RenderStarting` event to allow modification of plottable properties (#3077) _Thanks GooBad_
* Rendering: Added `RenderManager.PreRenderLock` event so developers of multi-threaded applications can ensure plottables are stable at render time (#3095) _Thanks @bclehmann_
* Statistics: Added descriptive statistics methods and improved support for 2D arrays (#3113, #3121) _Thanks @arthurits_
* Rendering: Improved appearance of shapes with custom hatches and outlines (#3099) _Thanks @faguetan_
* Text: Improved support for multiline labels (#3087) _Thanks @raburton_
* Layout: Improved tick and axis label alignment in fixed layout plots (#3104) _Thanks @albyoo_
* Layout: Created `Plot.Layout` class for holding `Frameless()` and related methods (#3106) _Thanks @angulion_

## ScottPlot 4.1.70
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-12-29_
* Population Plot: Improved performance for populations with curves that run off the screen (#3054) _Thanks @Em3a-c and @cornford_
* Performance: Improved performance of Bar and Finance plots by not drawing shapes outside the data area (#3053, #3078) _Thanks @AndreyPalyutin_
* Colormap: Added a `Reversed()` method for creating colormaps with reversed color order (#3100) _Thanks @bukkideme_
* Version: Added `ShouldBe()` method to assert the version of ScottPlot matches the expected one (#3093)
* Marker: Added support for `Marker.horizontalBar` to compliment `verticalBar` (#3101) _Thanks @SerhiiMahera_
* Axis: Span limits are respected when zooming with a window or scroll wheel (#3082) _Thanks @ashe27_
* Statistics: Added `Descriptive.StdErr()` for calculating standard error of the mean (#3112)

## ScottPlot 5.0.10-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-12-03_
* Signal: Improved support for datasets with repeating values (#2933, #2935) _Thanks @StendProg_
* Blazor: Added a Blazor control (#2959) _Thanks @sulivanganter_
* Layout: Expose `Matched` layout engine (#2881) _Thanks @proplunger_
* Plot: Added `DisableGrid()` and `EnableGrid()` helper methods (#2947)
* Render: Created `IRenderLast` plottables can implement to draw above axes (#2998, #2993)
* Controls: Added `Interaction.Disable()` and `Interaction.Enable()` methods for easy control of mouse interactivity
* Render: Improve axis frame and tick mark rendering for SVG export (#2944) _Thanks @Crown0815_
* Controls: Created OpenGL controls `FormsPlotGL` and `WpfPlotGL` distinct from `FormsPlot` and `WpfPlot` (#3008, #3007, #2950, #2395, #2565)
* Markers: Added numerous additional marker types (#2999, #3019) _Thanks @Gray-lab_
* Plot: Improved support for multiple axes and automatic scaling (#3027)
* RandomDataGenerator: Use a global Random number generator for improved randomness and thread safety (#2893, #3022) _Thanks @KroMignon_
* Scatter: Added `Data.GetNearest()` to simplify locating the point nearest the cursor (#3026, #3048) _Thanks @JurasskPark and @CBrauer_
* Plottable: Added a new `Text` plot type for displaying a label at a location in coordinate space (#2939)
* Plot: Benchmark is now a user-customizable plottable and `Plot.ShowBenchmark` is now `Plot.Benchmark.IsVisible` (#2961)
* Grid: Improve support for custom line styles (#2904) _Thanks @minjjKang_
* Pie: Improve appearance of slice labels in the legend (#2894, #2852) _Thanks @zy1075984_
* Legend: Replaced `List<ILegend>` with a simple `Legend` object with an `IsVisible` property (#2792)
* Avalonia: Improved sizing of plot controls inside containers (#2923) _Thanks @JohnSmith20211124 and @Developer-Alexander_

## ScottPlot 4.1.69
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-12-03_
* Axis: Added `IsReverse` property to let users invert the orientation of an axis (#2958) _Thanks @HandsomeGoldenKnight_
* Text: Exposed `LastRenderRectangleCoordinates` to improve mouse interactivity (#2994) _Thanks @DaveMartel_
* Arrow: Fixed bug in constructor overload (#2976, #3001) _Thanks @Gray-lab_
* Controls: Resizing will now invoke `OnAxesChanged` event (#3000, #3002) _Thanks @dhgigisoave_
* Plot: Added `LastRenderDimensions` for easy access to the latest figure dimensions (#3000, #3002) _Thanks @dhgigisoave_
* DataLogger and DataStreamer: Added support for custom line styles (#2972, #2972) _Thanks @Gray-lab_
* Population: Defining `BoxAlphaOverride` and `MarkerAlpha` allows for exact color representation (#2967, #3013) _Thanks @Gray-lab and @Em3a-c_
* RandomDataGenerator: Use a global Random number generator for improved randomness and thread safety (#2893, #3022) _Thanks @KroMignon_
* Controls: Improve `Bitmap` disposal as controls are unloaded (#3023, #2902) _Thanks @KroMignon and @mocakturk_
* ScatterPlotDraggable: Fixed bug affecting `IsUnderMouse()` after `Update()` is called (#2870, #2969, #3025) _Thanks @KroMignon, @SasKayDE, and @onur-akaydin_
* Bar: New `AddBar()` overload for creating a single highly customized bar graph bar (#3024, #3033) _Thanks @melhashash_
* FormsPlot: Fix bug affecting mouse interaction on plots with all items hidden (#2895) _Thanks @LapinFou_
* RadarPlot: Added customization options for axis label string formatting, manual tick positions, and transparency (#3041) _Thanks @JbmOnGitHub_
* Axis: Added `Axis.SetTicks()` to allow full customization of major and minor ticks (#2957) _Thanks @FannyAtGitHub_
* Plot: `GetImageHTML()` has been renamed to `GetImageHtml()` (#2974) _Thanks @b4shful_

## ScottPlot 5.0.9-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-10-03_
* PixelPadding: `TotalHorizontal` and `TotalVertical` renamed to `Horizontal` and `Vertical` (#2874, #2878) _Thanks @viktoriussuwandi_
* CoordinateRect: Added `Expanded()` method for creating a copy of the rectangle expanded to include a given point (#2871, #2890) _Thanks @aespitia_
* FillY: Added legend support (#2886, #2896) _Thanks @msroest_
* Plot: Created `Add.Line(x1, x2, y1, y2)` and related overloads for adding straight lines to plots (#2901, #2915)
* LinearRegression: Added `Statistics.Regression` (see cookbook) for fitting lines to collections of X/Y data points (#2901) _Thanks @anewton_
* Avalonia: Improve rendering in multi-control windows (#2920) _Thanks @nightfog-git_

## ScottPlot 4.1.68
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-10-03_
* Heatmap: Added a `UseParallel` option which can improve `Update()` performance for large datasets (#2897) _Thanks @bukkideme_

## ScottPlot 5.0.8-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-08-13_
* Rendering: Improved performance by caching typefaces (#2833, #2848) _Thanks @KroMignon and @taya92413_
* Avalonia: Improved performance, DPI awareness, and color rendering (#2818, #2859) _Thanks @oktrue_
* Rename: `XMin`, `XMax`, `YMin`, and `YMax` properties are now `Left`, `Right`, `Bottom`, `Top` for all coordinate primitives (#2840)
* Plot: Improve `AutoScale()` customization using `Margins()` to define whitespace area (#2857)
* Primitives: Improved equality checks (#2855)
* Controls: Added a `RenderQueue` to allow cross-control render requests that would otherwise cause render artifacts or infinite loops
* Controls: Created `SharedAxisManager` and `SharedLayoutManager` to facilitate pairing controls together
* Multiplot: Added methods for creating creating static multi-plot figures (#2868, #2869)

## ScottPlot 4.1.67
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-08-13_
* DataLogger: Improved appearance of legend items (#2829, #2850) _Thanks @KroMignon and @p4pravin_
* Radial Gauge Plot: Improved layout for plots with a large number of gauges (#2722) _Thanks @tinuskotze_
* DataLogger: Added support for markers (#2862) _Thanks @KroMignon_
* AxisLimits: Added `WithPan()` overloads to facilitate panning in interactive applications (#2863) _Thanks @LapinFou_
* Rectangle: Plots now have an `AddRectangle()` for placing rectangular shapes on plots (#2866) _Thanks @dpieve_

## ScottPlot 5.0.7-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-08-06_
* Axis: Fixed issue where axes with zero span would cause renders to fail (#2714) _Thanks @ahmad-qamar_
* Avalonia: Improve support for cross-platform and non-desktop applications (#2748) _Thanks @PremekTill_
* Scatter Plot: Improve support for empty datasets (#2740)
* Scatter Plot: Improve support for user-defined line widths (#2739, #2750) _Thanks @dayo05_
* Fonts: New static class to facilitate selecting fonts that support international characters (#2746) _Thanks @heartacker_
* Axis: Exposed `TickFont` to allow tick label size and style customization (#2747) _Thanks @heartacker_
* Plot: Added `Title()`, `XLabel()`, and `YLabel()` helper methods
* Fonts: Favor the system default font to achieve better support international characters (#2746) _Thanks @heartacker_
* Plot: Added `ScaleFactor` property to manage scaling of all plot components (#2747) _Thanks @heartacker_
* WinForms: Automatically adjust plot scaling to match display scaling (#2747) _Thanks @heartacker_
* Plot: Added a `RenderManager` which has a `List<RenderAction>` the user can modify to customize the render sequence (#2767)
* Plot: Refactored rendering system for all plottables, axes, etc. so canvases (not surfaces) are passed (#2767)
* WPF: Improved support for display scaling (#2760, #2766) _Thanks @DmitryKotenev_
* Plot: Added support for SVG export (#2704, #717)
* Legend: Respect `IsVisible` property (#2805)
* Ticks: Added `NumericManual` tick generator for manually-defined tick positions and labels
* Plot: `Title()`, `XLabel()`, and `YLabel()` have optional arguments for `size`
* Plot: Added `Plot.Style.SetFont()` to apply the given font to all titles, axis labels, and tick labels
* Plot: Added `Plot.Style.SetFontFromText()` to apply system font that best supports the language of the provided text (#2746) _Thanks @heartacker_
* RandomDataGenerator: Improved XML docs and added methods for returning single numbers (#2774, #2787) _Thanks @Silent0Wings_
* Pixel: Added constructor overload that accepts `double` values (#2780) _Thanks @Silent0Wings_
* Primitives: Refactored and added XML docs to `Pixel`, `PixelSize`, and `PixelRect` (#2784)
* Color: Added `WithAlpha()` method that accepts a fraction (#2794, #2776) _Thanks @mjpz_
* Coordinates: Added `Distance()` method for calculating distance between two points in axis space (#2791, #2798) _Thanks @able-j_
* CoordinateRect: Added a `Center` property that returns a `Coordinates` value in axis space (#2789, #2812) _Thanks @tijin-abe-thomas_
* CoordinateRect: Added a `Contains()` method to evaluate whether given `Coordinates` are inside the rectangle (#2790, #2813) _Thanks @tijin-abe-thomas_
* Crosshair: New plot type that draws a cross centered at a given position in X/Y space
* Avalonia: Support Avalonia version 11.0.1 (#2822) _Thanks @oktrue_
* Controls: Now have `GetCoordinates()` with built-in logic for display scaling compensation (#2760)
* Rendering: Improve multi-platform color support (#2818) _Thanks @KroMignon and @oktrue_
* Random Data Generation: Added an optional `slope` argument to `RandomWalk()` (#2763, #2826) _Thanks @JasonC0x0D_
* Browser: Improved support and documentation for running ScottPlot in the browser with Avalonia and WinUI (#2830) _Thanks @oktrue_
* Android: Improved support and documentation for running ScottPlot in Avalonia Android projects (#2830) _Thanks @oktrue_
* Legend: Now hidden by default with opt-in visibility by calling `Plot.Legend()` (#2764)
* Style: `Plot.Axes` has been renamed to `Plot.AxisStyler` to better communicate its purpose (#2778)
* Primitives: Created `ExpandingAxisLimits` helper class for creating `AxisLimits` inside plottables (#2799)
* Plot: Added `Pan()` and `Zoom()` methods that do not require passing state like `MousePan()` and `MouseZoom()` do (#2800)
* Plot: Added `Plot.RenderManager.RenderFinished` event that provides a `RenderDetails` indicating whether axes or layout changed (#2801)
* FormsPlot: Added `RefreshQueue()` to allow facilitate event-driven refreshing of multiple controls in single-thread applications (#2801, #2802)
* Plot: Added `MatchAxisLimits()` to simplify applying limits from one plot to another in multi-control applications (#2802)
* Layout: Added `MatchLayout()` and `FixedLayout()` as an alternative to the default `AutomaticLayout()` engine (#2802)

## ScottPlot 4.1.66
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-08-06_
* DataLogger: Improved support for single-point datasets (#2733) _Thanks @KroMignon_
* Plot: Added optional arguments to `AddDataLogger()` and `AddDataStreamer()` for customizing style (#2733) _Thanks @KroMignon_
* Version: Build information can now be accessed from the static `ScottPlot.Version` class
* Avalonia: Removed dependency on `Avalonia.Desktop` package (#2752, #2748) _Thanks @Fruchtzwerg94_
* Cookbook: Remove "experimental" designator from ScatterPlotList (#2782) _Thanks @prime167_
* Heatmap: Added `Rotation` and `CenterOfRotation` properties (#2814, #2815) _Thanks @bukkideme_
* WPF: Improved the `PlottableDragged` event (#2820) _Thanks @tadmccorkle_
* Avalonia: Support Avalonia version 11.0.1 (#2822) _Thanks @oktrue_
* Heatmap: Improved XML docs (#2738, #2827) _Thanks @JasonC0x0D_

## ScottPlot 5.0.6-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-07-09_
* Legend: Improve support for custom positioning (#2584, #2638) _Thanks @heartacker_
* OpenGL: Use CPU to render on devices without hardware acceleration (#2651) _Thanks @StendProg_
* Polygon: New plot type for displaying closed shapes with arbitrary X/Y corners (#2696) _Thanks @Tilation_
* FillY: New plot type for displaying a shaded area between two sets of Y points that share the same X points (#2696) _Thanks @Tilation_
* Avalonia: Added support for Avalonia 11 (#2720, #2184, #2664, #2507, #2321, #2184, #2183, #2725) _Thanks @Fruchtzwerg94, @Xerxes004, and @bclehmann_

## ScottPlot 4.1.65
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-07-09_
* Axis: Improved log-scaled axis minor tick density default value and customization (#2646) _Thanks @hellfo_
* Image: Added option to disable anti-aliasing for scaled images (#2649) _Thanks @mYcheng-95_
* Binned Histogram: New plot type that represents binned 2D histogram data as a heatmap (#2453)
* DataLogger: New type of scatter plot designed for infinitely growing X/Y datasets (#2377, #2641)
* DataStreamer: New type of signal plot for displaying live data as it is shifted in (#2377, #2641)
* WPF: Multi-target Framework 4.6.1 changed to 4.6.2 (#2685)
* Axis: Added option to customize tick line width (#2643, #2654) _Thanks @Guillaume-Deville_
* Horizontal Span: Fixed `ToString()` message _Thanks @RachamimYaakobov_
* Signal Plot: Added `ScaleY` property to compliment `OffsetY` (#2642, #2656) _Thanks @Guillaume-Deville_
* Colorbar: Automatically adjust label position to prevent overlap with tick labels (#2684) _Thanks @bukkideme_
* Launcher: Made `Plot.Launch` methods available without requiring using statements (#2627, #2657) _Thanks @Guillaume-Deville_
* Population plot: Added `BoxBorderColor` and `ErrorStDevBarColor` properties to customize appearance (#2708) _Thanks @johndoh_
* Arrow: Made tip and base positions mutable (#2673) _Thanks @MyZQL_
* ScatterPlotList: Add `GetXs()` and `GetYs()` to let users retrieve copies of data points (#2694, #2711) _Thanks @bukkideme and @Marc-Frank_
* FormsPlotViewer: New constructor for synchronized plots with bidirectional updates (#2653, #2710, #2722) _Thanks @bukkideme_
* LineStyle: Default patterns (and a new custom pattern) can be customized by assigning `ScottPlot.LineStylePatterns` (#2690, #2692) _Thanks @mocakturk, @Marc-Frank, and @bukkideme_
* Radar Plots: Improve vertical spacing for all aspect ratios (#2702) _Thanks @pjt33_
* Avalonia: Added support for Avalonia 11 (#2720, #2184, #2664, #2507, #2321, #2184, #2183, #2725) _Thanks @Fruchtzwerg94, @Xerxes004, and @bclehmann_
* Colorbar: Added a `ResizeLayout()` helper method for adjusting plot layouts to accommodate large tick labels (#2703)
* Scatter List: Improved support for data containing NaN values (#2707) _Thanks @oldteacup_
* Population Plot: Improved support for populations with no data (#2727, #2726) _Thanks @marklam_

## ScottPlot 5.0.5-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-05-17_
* Box Plot: New plot type for displaying multiple collections of population data (#2589) _Thanks @bclehmann_
* OpenGL Control: Prevent exceptions on keyboard input (#2609, #2616) _Thanks @stendprog_
* Platforms: Improved linux support by using SkiaSharp native assets without dependencies (#2607) _Thanks @chrisxfire
* Color: Improved support for alpha values in constructor (#2625) _Thanks Clay_

## ScottPlot 4.1.64
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-05-17_
* Ellipse: Added `Rotation` property (#2588, #2595) _Thanks @JohniMIEP and @bclehmann_
* Controls: Prevent horizontal scroll wheel events from throwing exceptions (#2600, #2626, #2630) _Thanks @bclehmann, @szescxz, and @Jordant190_
* ScatterDataLogger: Experimental plot type for live incoming data (#2377, #2599)
* Ticks: Improved automatic layout sizing when manual ticks are used (#2603, #2605) _Thanks @StefanBertels and @szescxz_
* Ticks: Improved automatic layout sizing for short and empty tick labels (#2606) _Thanks @szescxz_
* Plot: Improved `AddVerticalLine()` XML docs (#2610) _Thanks @wfs1900_
* FinancePlot: `GetBollingerBands()` now accepts an optional standard deviation coefficient (#2594) _Thanks @Minu476_
* SignalPlot: Fixed bug where `Update()` did not change the final point (#2592) _Thanks @Angeld10_
* ScatterPlotDraggable: Expose IndexUnderMouse for access after drag events (#2682) _Thanks @mocakturk_

## ScottPlot 5.0.4-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-04-09_
* WpfPlot: Converted the `UserControl` to a `CustomControl` to facilitate inheritance and theming (#2565) _Thanks @KroMignon_
* Controls: Improved ALT + left-click-drag zoom rectangle behavior (#2566)

## ScottPlot 4.1.63
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-04-09_
* WpfPlot: Converted the `UserControl` to a `CustomControl` to facilitate inheritance and theming (#2509, #2526) _Thanks @KroMignon_
* Lollipop and Cleveland plots: Added `LineWidth` property (#2556) _Thanks @benton-anderson_
* Pie: Added `SliceLabelPosition` property to allow slice labels to be placed outside the pie (#2515, #2510, #2275) _Thanks @nuelle16 and @cpa-level-it_
* Axis: Made `Edge` and `AxisIndex` immutable to prevent accidental modification after construction (#2539, #2538) _Thanks @cxjcqu_
* Plot: Created `LeftAxis`, `RightAxis`, `BottomAxis`, and `TopAxis` which alias `YAxis`, `YAxis2`, `XAxis`, and `XAxis2` but are more expressive (#2568)
* Plot: `Launch` property has methods for launching the plot as a static image, refreshing web page, or interactive window (#2543, #2570)
* Heatmap: Improved support for semitransparent cells (#2313, #2277, #2285, #2461, #2484) _Thanks @bukkideme_
* Axis: Added `SetZoomInLimit()`, `SetZoomOutLimit()`, and `SetBoundary()` to control zoom and pan (#2250, #2291, #1997, #1873, #662) _Thanks @dusko23, @Gholamalih, and @bclehmann_
* Controls: Added `Configuration.RightClickDragZoomFromMouseDown` flag to enable right-click-drag zoom to scale relative to the cursor (#2296, #2573) _Thanks @pavlexander_
* Finance: Improved DateTime position of random stock price sample data (#2574)
* Axis: Improve tick spacing for extremely small plots (#2289) _Thanks @Xerxes004_
* Signal: Fixed bug causing `Update()` to throw an indexing error (#2578) _Thanks @Angeld10_
* Annotation: Position is no longer defined as `X` and `Y` but instead `Alignment`, `MarginX`, and `MarginY` (#2302) _Thanks @EFeru_
* Colorbar: Add `Label` property (#2341) _Thanks @bukkideme_

## ScottPlot 5.0.4-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-04-02_
* OpenGL: Enhanced customization options for OpenGL-accelerated scatter plots (#2446) _Thanks @StendProg_
* Data: Added axis limit caching functionality for improved performance of large scatter plots (#2460) _Thanks @StendProg_
* DataOperations: New static class with helper methods for working with 1D and 2D data (#2497) _Thanks @bukkideme and @StendProg_
* Financial: Created `IOHLC` to allow users to inject their own pricing logic (#2404) _Thanks @mjpz_
* Solution: Fixed configuration error caused by invalid GUIDs (#2525) _Thanks @KroMignon_
* Controls: Disabled context menu in non-interactive mode (#2475) _Thanks @KroMignon_
* Histogram: Improved constructor argument validation and support for small bins(#2490) _Thanks @Margulieuxd and @bukkideme_
* WpfPlot: Control now appears in the Visual Studio Toolbox (#2535, #1966) _Thanks Valkyre_
* Axis: Improved tick label format customization (#2500) _Thanks @chhh_

## ScottPlot 4.1.62
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-04-02_
* WinForms Control: `Reset()` makes new plots transparent (#2445) _Thanks @Neopentane1_
* Ellipse and Circle: New plot types demonstrated in the cookbook. (#2413, #2437) _Thanks @bukkideme_
* Heatmap: Added `FlipVertically` to invert vertical axis of heatmap data (#2444, #2450) _Thanks @Neopentane1_
* Histogram: Improved support for datasets with low variance (#2464, #2463) _Thanks @Xerxes004_
* Heatmap: Added `Opacity` property (#2461, #2484) _Thanks @bukkideme_
* DataOperations: New static class with helper methods for working with 1D and 2D data (#2497) _Thanks @bukkideme and @StendProg_
* Population: Added option for customizing horizontal errorbar alignment (#2502) _Thanks @benton-anderson_
* Financial: Created `IOHLC` to allow users to inject their own pricing logic (#2404) _Thanks @mjpz_
* OHLC: The `Volume` property and constructor overload initializing it have been deprecated (#2404)
* Axis: Expose tick, spine, and label configuration objects (#2512, #2513, #2353) _Thanks @cxjcqu and @SaltyTears_
* Signal: Improved `FillDisable()` behavior (#2436) _Thanks @szescxz_
* RadialGaugePlot: Improve alignment for plots with 1-3 gauges (#2448, #2128) _Thanks @DavidWhataGIT, @johndoh, and daddydavid_
* Pie: Added `LegendLabels` property so slices and legend items can have different labels (#2459) _Thanks @vietanhbui_
* Controls: Improved `GetCoordinate()` behavior for empty plots (#2468, #2540) _Thanks @dusko23_
* Histogram: Improved constructor argument validation and support for small bins(#2490) _Thanks @Margulieuxd and @bukkideme_
* Axis: Improved `Plot.AxisPanCenter()` support for multi-axis plots (#2483, #2544) _Thanks @dusko23_
* Bubble Plot: Added `RadiusIsPixels` flag which when `falst` sizes bubbles using radius units instead of pixels (#2492) _Thanks @marcelpel_
* Axis: Improved `Plot.MatchAxisLimits()` support for multi-axis plots (#2495) _Thanks @Margulieuxd_
* Plot: Improved `Plot.XLabel()` XML documentation (#2552) _Thanks @JulianusIV_

## ScottPlot 5.0.2-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-02-27_
* Signal Plot: Support X and Y offset (#2378) _Thanks @minjjKang_
* WebAssembly: New sandbox demonstrates interactive ScottPlot in a browser (#2380, #2374) _Thanks rafntor_
* OpenGL: Added experimental support for direct GPU rendering (#2383, #2397) _Thanks @StendProg_
* Finance Plots: Added OHLC and Candlestick plot types (#2386) _Thanks @bclehmann_
* Style: Improved `Plot.Style.Background()` color configuration (#2398) _Thanks @Jonathanio123_
* WPF: Added OpenGL support to the WPF control (#2395) _Thanks @StendProg_
* Palette: Refactored the palette system to allow ScottPlot 4 and 5 to share palette code (#2409)
* Plot: Added `GetImageHTML()` for improved rendering in interactive notebooks (#2385, #1772) _Thanks @neilyoung2008_

## ScottPlot 4.1.61
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-02-27_
* Axis: Throw exception immediately upon setting invalid axis limits (#2327) _Thanks @mjpz_
* Heatmap: Added support for transparent single-color heatmaps (#2336) _Thanks @bukkideme_
* Statistics: Improved median calculation method in population plots (#2363) _Thanks @Syntaxrabbit_
* AxisLineVector: Improved automatic axis limits when using limited axis lines (#2371) _Thanks @ChrisAtVault_
* Controls: `Configuration.AddLinkedControl()` simplifies axis sharing across multiple controls (#2402, #2372)
* Statistics: New `ScottPlot.Statistics.Histogram` class optimized for simplicity and live data (#2403, #2389) _Thanks @bukkideme and @Xerxes004_
* Statistics: Improved bin edge calculations for histograms with fixed bin size bins (#2299) _Thanks @Xerxes004_
* Palette: Refactored the palette system to allow ScottPlot 4 and 5 to share palette code (#2409)
* Heatmap: Added `GetBitmap()` to provide access to raw heatmap image data (#2396, #2410) _Thanks @bukkideme_
* Pie: Prevent invalid argument exceptions when drawing zero-size pie charts (#2415) _Thanks @KC7465128305_
* Colormap: Colormaps can be created from a set of colors (#2375, #2191, #2187) _Thanks @dhgigisoave_
* Function Plot: New optional `AxisLimits` allows users to define default axis limits (#2428, #2412) _Thanks @bukkideme_
* Population: Fixed bug causing argument exceptions for 1px high plots (#2429, #2384) _Thanks @Sprenk_
* Controls: Added `Configuration.AltLeftClickDragZoom` option to customize zooming behavior (#2391, #2392) _Thanks @DevJins_
* Error Bar: Added `Label` property which allows error bars to appear independently in the legend (#2432, #2388) _Thanks @dongyi-cai-windsab_
* Demo: Fixed bug preventing the cookbook from launching (#2443) _Thanks @FannyAtGitHub_

## ScottPlot 5.0.1-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-02-09_
* Namespace: DataSource → DataSources
* Error Bar: New plot type (#2346) _Thanks @bclehmann_
* Plot: Added `Style` object to group functions that perform complex styling tasks
* Controls: Added right-click context menus (#2350) _Thanks @bclehmann_
* Rendering: Added support for saving bitmap files (#2350) _Thanks @bclehmann_
* Axes: Added support for DateTime Axes (#2369) _Thanks @bclehmann_
* Rendering: Added support for line styles (#2373) _Thanks @bclehmann_
* WinUI3: Created a Uno WinUI3 control (#2374, #2039) _Thanks @rafntor_

## ScottPlot 5.0.0-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2023-01-01_
* ScottPlot 5: First version 5 release published to NuGet #2304

## ScottPlot 4.1.60
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-12-23_
* Pie Chart: Improved display when a single slice covers the entire pie (#2248, #2251) _Thanks @bclehmann_
* Plot: Added `AddFill()` arguments for `LineWidth` and `LineColor` (#2258) _Thanks @Fruchtzwerg94_
* Plot: Improved support for filled polygons with fewer than 3 points (#2258) _Thanks @Fruchtzwerg94_
* A new `IDraggableSpan` interface was added to trigger events when the edges of spans are dragged (#2268) _Thanks @StendProg_
* Palettes: Added new light-color palettes PastelWheel, LightSpectrum, and LightOcean (#2271, #2272, #2273) _Thanks @arthurits_
* Ticks: Improved tick calculations for very small plots (#2280, #2278) _Thanks @Xerxes004_
* Crosshair: HLine and VLine are no longer readonly (#2208) _Thanks @arthurits_
* Function Plot: Added support for filling above and below lines (#2239, #2238) _Thanks @SGanard_
* Signal Plot: Improved error messages for when `Update()` fails to replace data (#2263)
* Plot: `Clear()` now resets inner and outer view limits (#2264) _Thanks @vietanhbui_
* FormsPlot: Right-click help menu is now `TopMost` (#2282) _Thanks @dusko23_
* Signal Plot: Allow users to apply different colors to lines and markers (#2288) _Thanks @Nuliax7_
* Pie: Added `Size` option to allow customizing how large the pie chart is (#2317) _Thanks @Rudde_
* FormsPlot: Improved support for horizontal legends in the pop-out legend viewer (#2300) _Thanks @rotger_
* Axis: Added arguments to `AxisPan()` to improve multi-axis support (#2293)
* Axis: Added `AxisPanCenter()` to center the view on a coordinate (#2293) _Thanks @dusko23_
* Project: Use System.Drawing.Common version 4.7.2 to avoid CVE-2021-26701 (#2303, #1004, #1413) _Thanks @gobikulandaisamy_

## ScottPlot 4.1.59
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-11-06_
* Ticks: Improve datetime tick labels for systems with a 24-hour display format (#2132, #2135) _Thanks @MareMare and @bclehmann_
* Axis: `Plot.AddAxis()` now uses auto-incremented axis index unless one is explicitly defined (#2133) _Thanks @bclehmann and Discord/Nick_
* Axis: `Plot.GetAxesMatching()` was created to obtain a given vertical or horizontal axis (#2133) _Thanks @bclehmann and Discord/Nick_
* Axis: Corner label format can be customized for any axis by calling `CornerLabelFormat()` (#2134) _Thanks @ShannonZ_
* BarSeries: Improved rendering of negative values (#2147, #2152) _Thanks @fe-c_
* Function Plot: Added optional `XMin` and `XMax` fields which limit function rendering to a defined horizontal span (#2158, #2156, #2138) _Thanks @bclehmann and @phil100vol_
* FormsPlot: Plot viewer now has `RefreshLegendImage()` allowing the pop-out legend to be redrawn programmatically (#2157, #2153) _Thanks @rosdyana_
* Function Plot: Improved performance for functions which return null (#2158, #2156, #2138) _Thanks @bclehmann_
* BarSeries: improve support for negative and horizontal bar labels (#2148, #2159, #2152) _Thanks @bclehmann_
* Palette: Added `Normal` Palette based on [Anton Tsitsulin's Normal 6-color palette](http://tsitsul.in/blog/coloropt/) (#2161, #2010) _Thanks @martinkleppe_
* BarSeries: Added helper function to create a bar series from an array of values (#2161) _Thanks @KonH_
* SignalPlot: Add `Smooth` option (#2174, #2137) _Thanks @rosdyana_
* Signal Plot: Use correct marker when displaying in legend (#2172, #2173) _Thanks @bclehmann_
* Data Generation: Improved floating point precision of `RandomNormalValue` randomness (#2189, #2206) _Thanks @arthurits and @bclehmann__
* Finance Plot: Improved SMA calculations for charts with unordered candlesticks (#2199, #2207) _Thanks @zachesposito and @xenedia_
* Avalonia Control: Fixed subscription to ContexMenu property changes (#2215) _Thanks @DmitryZhelnin_
* Legend: Support horizontal orientation and added cookbook example (#2216) _Thanks @lucabat_
* Data Generation: Added generic support for `Consecutive()`, `Random()`, and `RandomWalk()`
* SignalPlot: New `SignalPlotGeneric` type allows `AddSignal()` to support generic data types (#2217) _Thanks @codecrafty_

## ScottPlot 4.1.58
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-09-08_
* Radar: New `Smooth` field allows radar areas to be drawn with smooth lines (#2067, #2065) _Thanks @theelderwand_
* Ticks: Setting manual ticks will now throw an immediate `ArgumentException` if positions and labels have different lengths (#2063) _Thanks @sergaent_
* VectorFieldList: New plot type for plotting arbitrary coordinate/vector pairs which are not confined to a grid (#2064, #2079) _Thanks @sjdemoor and @bclehmann_
* HLine and VLine: Line (but not position label) is hidden if `LineWidth` is `0` (#2085) _Thanks @A1145681_
* Controls: The cursor now reverts to `Configuration.DefaultCursor` after moving off draggable objects (#2091) _Thanks @kurupt44_
* Snapping: SnapNearest classes now expose `SnapIndex()` (#2099) _Thanks @BambOoxX_
* Background: Added optional arguments to `Style()` lets users place a custom background image behind their plot (#2016) _Thanks @apaaris_
* Axis Line: Remove the ability to drag invisible lines (#2110) _Thanks @A1145681_
* Controls: Draggable objects can now only be dragged with the left mouse button (#2111, #2120) _Thanks @A1145681_
* Heatmap: Prevent rendering artifacts by throwing an exception if the 2D array is larger than 2^15 in either dimension (#2119, #2116) _Thanks @dhgigisoave_

## ScottPlot 4.1.57
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-08-18_
* Scatter: Improved `GetPointNearest()` when `OnNaN` is `Gap` or `Ignore` (#2048) _Thanks @thopri_
* Heatmap and Image: Added `Coordinate[] ClippingPoints` to give users the ability to clip to an arbitrary polygon (#2049, #2052) _Thanks @xichaoqiang_
* Image: Improved automatic axis limits measurement when `HeightInAxisUnits` is defined
* Plot: Reduced anti-aliasing artifacts at the edge of frameless plots (#2051)

## ScottPlot 4.1.56
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-08-16_
* Signal: Improved accuracy of `GetIndexForX()` (#2044) _Thanks @CharlesMauldin_
* Palette: Added help messages for users attempting to create custom palettes (#1966) _Thanks @EFeru_

## ScottPlot 4.1.55
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-08-14_
* Scatter: Data may now contain NaN if the `OnNaN` field is customized. `Throw` throws an exception of NaN is detected (default behavior), `Ignore` skips over NaN values (connecting adjacent points with a line), and `Gap` breaks the line so NaN values appear as gaps. (#2040, #2041)
* Plot: Added a `AddFillError()` helper method to create a shaded error polygon for displaying beneath a scatter plot (#2037)

## ScottPlot 4.1.53
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-08-11_
* Scatter and Signal Plot: `GetYDataRange()` now returns the range of Y values between a range of X positions, useful for setting automatic axis limits when plots are zoomed-in (#1946, #1942, #1929) _Thanks @bclehmann_
* WPF Control: Right-click copy now renders high quality image to the clipboard (#1952) _Thanks @bclehmann_
* Radar, Coxcomb, and Pie Chart: New options to customize hatch pattern and color. See cookbook for examples. (#1948, #1943) _Thanks @bclehmann_
* Signal Plot: Improve support for plots with a single point (#1951, #1949) _Thanks @bclehmann and @Fruchtzwerg94_
* Draggable Marker Plots: Improved drag behavior when drag limits are in use (#1970) _Thanks @xmln17_
* Signal Plot: Added support for plotting `byte` arrays (#1945)
* Axis Line: Added properties to customize alignment of position labels (#1972) _Thanks @hamhub7_
* Plot: MatchAxis no longer modifies limits of unintended axes (#1980) _Thanks @PlayCreatively_
* Plot: Improved error reporting for invalid axis limits (#1994) _Thanks @Xerxes004_
* Signal Plot: Improved `GetPointNearestX()` accuracy for plots with high zoom (#1987, #2019, #2020) _Thanks @dhgigisoave_
* Draggable: `IDraggable` now has functions to facilitate snapping (#2006, #2007, #2022) _Thanks @Agorath_
* Palette: `ScottPlot.Palette` has been refactored to replace `ScottPlot.Drawing.Palette` and `ScottPlot.Drawing.Colorset` (#2024)
* Palette: Palettes now implement `IEnumerable` and colors can be retrieved using `foreach` (#2028)
* Render: Improved thread safety of the render lock system (#2030) _Thanks @anprevost_
* Scatter: Exposed `SmoothTension` to customize behavior when `Smooth` is enabled (#1878) _Thanks Michael99_

## ScottPlot 4.1.52
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-07-09_
* WinForms control: Fixed a bug introduced by the previous version which resulted in flickering while using the mouse to pan or zoom (#1938, #1913) _Thanks @AbeniMatteo_
* Plot: Added obsolete `GetLegendBitmap()` with message indicating `RenderLegend()` is to be used instead (#1937, #1936) _Thanks @johnfoll_
* Signal Plot: Improved performance using platform-specific fast paths for common data types to minimize allocations (#1927) _Thanks @AbeniMatteo, @StendProg, and @bclehmann_

## ScottPlot 4.1.51
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-06-30_
* WinForms Control: Fixed a bug that caused frequent mouse events to overflow the stack (#1906, #1913) _Thanks @AbeniMatteo_
* Performance: Improve string measurement performance using cached fonts (#1915) _Thanks @AbeniMatteo_
* Layout: Improve axis alignment when `ManualDataArea()` is used (#1901, #1907, #1911) _Thanks @dhgigisoave_
* Cookbook: Improve error message if recipes.json is not found (#1917) _Thanks @AbeniMatteo_

## ScottPlot 4.1.50
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-06-26_
* BarSeries: Lists passed into new BarSeries are preserved and can be modified after instantiation. Added a `Count` property. Added a `AddBarSeries()` overload that permits creating an empty BarSeries. (#1902)
* Markers: Improved performance for plot types that render multiple markers (#1910) _Thanks @AbeniMatteo_
* Plot: New `ManualDataArea()` function allows users to define pixel-perfect layouts (#1907, #1901) _Thanks @dhgigisoave_

## ScottPlot 4.1.49
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-06-21_
* BarSeries: A new type of bar plot which allows each bar to be individually customized and offers mouse collision detection (#1891, #1749) _Thanks @jhm-ciberman_
* SignalXY: When step mode is activated markers are now only drawn at original data points (#1896) _Thanks @grabul_
* SignalConst: Fixed indexing error affecting the Update() overload that accepted generic arrays (#1895, #1893) _Thanks @strontiumpku_
* Scatter and Signal: When `StepDisplay` is enabled, the new `StepDisplayRight` property can toggle step orientation (#1894, #1811) _Thanks @dhgigisoave_
* SignalXY: Markers now shown in legend when the plot is zoomed-in enough that they become visible on the plot itself

## ScottPlot 4.1.48
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-06-09_
* Plottable: Collapsed `IHasAxisLimits`, `IHasDataValidation`, and `IHasLegendItems` back into `IPlottable`, reverting a change introduced by the previous version. The intent of the original change was to promote interface segregation (e.g., colorbar has no axis limits). However, the purpose of this reversion is to maintain consistent behavior for users who implemented their own plottables implementing `IPlottable` and may not be aware of these new interfaces. (#1868, #1881)

## ScottPlot 4.1.47
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-06-07_
* Scatter Plot: New `Smooth` property allows data points to be connected by smooth lines (#1852, #1853) _Thanks @liuhongran626_
* Axis: Improved corner notation for multi-axis plots (#1875) _Thanks @nassaleh_
* Plottable: Optional segregated interfaces `IHasAxisLimits`, `IHasDataValidation`, and `IHasLegendItems` were broken-out of `IPlottable`. Note that this change was reverted in the subsequent release. (#1868, #1881)

## ScottPlot 4.1.46
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-06-05_
* Image: `AddImage()` has optional arguments to define rotation, scale, and anchor alignment. The `Image` plot type has new public properties allowing images to be stretched so position and size can be defined using axis units (see Cookbook). `Rotation` now respects all anchor alignments. (#1847) _Thanks @wtywtykk and @bclehmann_
* Bracket: New plot type to highlight a range of data between two points in coordinate space (#1863) _Thanks @bclehmann_
* Heatmap: Added `FlipVertically` property to invert orientation of original data (#1866, #1864) _Thanks @bclehmann and @vtozarks_
* Axis: Improved placement of horizontal axis tick labels when multiple axes are in use (#1861, #1848) _Thanks @bclehmann and @Shengcancheng_
* Crosshair: Now included in automatic axis limit detection. Use its `IgnoreAxisAuto` property to disable this functionality. (#1855, #1857) _Thanks @CarloToso and @bclehmann_
* BarPlot: Improved automatic axis detection for bar plots containing negative values (#1855, #1857) _Thanks @CarloToso and @bclehmann_
* IHittable: new interface to facilitate mouse click and hover hit detection (#1845) _Thanks @StendProg and @bclehmann_
* Tooltip: Added logic to enable detection of mouse hover or click (#1843, #1844, #1845) _Thanks @kkaiser41, @bclehmann, and @StendProg_
* Controls: All user controls now have a `LeftClickedPlottable` event that fires when a plottable implementing `IHittable` was left-clicked
* FormsPlot: Set `Configuration.EnablePlotObjectEditor` to `true` to allow users to launch a plot object property editor from the right-click menu (#1842, #1831) _Thanks @bradmartin333 and @BambOoxX_
* BarPlot: Fixed bug where zooming extremely far in would cause large fills to disappear (#1849, #1850) _Thanks @ChrisAtVault_

## ScottPlot 4.1.45
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-05-05_
* Plottables: Fields converted to properties and setters paired with getters to facilitate binding (#1831) _Thanks @bradmartin333_

## ScottPlot 4.1.44
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-05-05_
* SignalXY: Permit duplicate X values and improve exception messages when invalid X data is loaded (#1832) _Thanks @Niravk1997_

## ScottPlot 4.1.43
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-05-02_
* Draggable Scatter Plot: Fixed a bug where horizontal drag limits were applied to the vertical axis (#1795) _Thanks @m4se_
* Plot: Improved support for user-defined ticks when inverted axis mode is enabled (#1826, #1814) _Thanks @Xerxes004_
* Heatmap: Added `GetCellIndexes()` to return the heatmap data position for a given coordinate (#1822, #1787) _Thanks @tonpimenta_
* Controls: Added `LeftClicked` event to customize left-click actions in GUI environments (#1822, #1787)

## ScottPlot 4.1.42
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-05-01_
* SignalXY: Fixed bug causing plots to disappear when displaying partial data containing duplicated X values. (#1803, #1806) _Thanks @StendProg and @bernhardbreuss_
* SignalXY: X data is no longer required to be ascending when it is first assigned, improving support for plots utilizing min/max render indexing (#1771, #1777) _Thanks @bernhardbreuss_
* Grid: Calling `Plot.Grid(onTop: true)` will cause grid lines to be drawn on top of plottables (#1780, #1779, #1773) _Thanks @bclehmann and @KATAMANENI_
* FormsPlot: Fixed a bug that caused the default right-click menu to throw an exception when certain types of plottables were present (#1791, #1794) _Thanks @ShenxuanLi, @MareMare, and @StendProg_
* Avalonia: Improved middle-click-drag zoom-rectangle behavior (#1807) _Thanks @kivarsen_
* Avalonia: Improved position of right-click menu (#1809) _Thanks @kivarsen_
* Avalonia: Added double-click support which displays benchmark information by default (#1810) _Thanks @kivarsen_
* Axis: Improved support for switching between custom tick label format strings and custom formatter functions (#1813) _Thanks @schifazl_
* Plot: `AutomaticTickPositions()` can now be used to undo action of `ManualTickPositions()` (#1814)
* Plot: `AutomaticTickPositions()` optionally accepts an array of ticks and labels that can be displayed in addition to the automatic ones (#1814) _Thanks @Xerxes004_
* Signal Plot: Improved low density display when `LineStyle` is `None` (#1797) _Thanks @nassaleh_
* FormsPlot: Detached legend now restores initial legend visibility state on close (#1804) _Thanks @BambOoxX_

## ScottPlot 4.1.41
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-04-09_
* Plot: Added `Plot.GetImageHTML()` to make it easy to display ScottPlot images in .NET Interactive / Jupyter notebooks (#1772) _Thanks @StendProg and @Regenhardt_

## ScottPlot 4.1.40
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-04-07_
* SignalPlotXY: Improved support for custom markers (#1763, #1764) _Thanks @bclehmann and @ChrisCC6_
* Legend: `Plot.Legend()` accepts a nullable `Location` so legends can be enabled/disabled without changing position (#1765) _Thanks @envine_
* FormsPlot: The right-click menu now shows "detach legend" even if all plottable items with legends are set to invisible (#1765) _Thanks @envine_
* AxisLine: Added a `PositionLabelAxis` field that can be used to define a specific axis to draw the position label on in multi-axis plots (#1766) _Thanks @fuxinsen_

## ScottPlot 4.1.39
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-04-01_
* SignalPlotXY: Fixed bug where `GetPointNearestX()` did not check proximity to the final point (#1757) _Thanks @MareMare_

## ScottPlot 4.1.38
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-03-31_
* Bar plot: Improved automatic axis limit detection for bars with negative offset (#1750) _Thanks @painstgithub_
* Axis labels: Added a `rotation` argument to `Axis.LabelStyle()` to support flipping label orientation (#1754, #1194) _Thanks @zeticabrian_

## ScottPlot 4.1.37
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-03-25_
* Controls: Improved multi-axis support for mouse tracking by giving `GetMouseCoordinates()` optional axis index arguments (#1743) _Thanks @kv-gits_

## ScottPlot 4.1.36
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-03-19_
* Axis: Allow grid line and tick mark pixel snapping to be disabled (#1721, #1722) _Thanks @Xerxes004_
* Axis: `ResetLayout()` sets padding to original values to reverse changes made by adding colorbars (#1732, #1736) _Thanks @ccopsey_

## ScottPlot 4.1.35
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-03-06_
* Eto.Forms: Improved handling of events (#1719, #1718) _Thanks @rafntor and @VPKSoft_

## ScottPlot 4.1.34
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-03-03_
* Bubble plot: Added methods to get the point nearest the cursor (#1657, #1652, #1705) _Thanks @BambOoxX, @Maoyao233, and @adgriff2_
* Markers: Improved alignment of markers and lines on Linux and MacOS by half a pixel (#1660, #340)
* Plottable: Added `IsHighlighted` properties to make some plot types bold (#1660) _Thanks @BambOoxX_
* Plottable: Segregated existing functionality interfaces for `IHasLine`, `IHasMarker`, and `IHilightable` (#1660) _Thanks @BambOoxX_
* Plot: `AxisAuto()` now throws an exception of margins are defined outside the allowable range (#450, #1682) _Thanks @xichaoqiang_
* Plot: Added `PlotFillRightLeft` method for adding horizontal filled scatter plots (#450) _Thanks @xichaoqiang_
* Markers: All shapes are now drawn discretely instead of relying on text rendering for improved performance and consistency (#1668, #1660) _Thanks @BambOoxX_
* Scatter Plot: Support distinct `LineColor` and `MarkerColor` colors (#1668)
* SignalXY: Fix bug affecting the edge of the plot when step mode is active (#1703, #1699) _Thanks @PeppermintKing_
* SignalXY: Improve appearance of filled regions when step mode is active (#1703, #1697) _Thanks @PeppermintKing_
* Axis Span: Added options to customize fill pattern and border (#1692) _Thanks @BambOoxX_
* Markers: Additional customization options such as `MarkerLineWidth` (#1690) _Thanks @BambOoxX_
* Legend Viewer: New functionality to customize line, marker, and highlight options have been added to the the right-click menu of the Windows Forms control (#1655, #1651) _Thanks @BambOoxX_

## ScottPlot 4.1.33
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-02-04_
* Spline Interpolation: Added new methods for data smoothing including Bézier interpolation (#1593, #1606)
* Detachable Legend: Added an option to detach the legend to the right-click menu in the Windows Forms control. Clicking items in the detached legend toggles their visibility on the plot (#1589, #1573, #1326) _Thanks @BambOoxX_
* Marker: Added an optional `Text` (and `TextFont`) for displaying a message that moves with a marker (#1599)
* Heatmap: Heatmaps with custom X and Y sizing or positioning no longer call `AxisScaleLock()` automatically (#1145) _Thanks @bclehmann_
* Axis: GetCoordinateY() now returns more accurate coordinate (#1625, #1616) _Thanks @BambOoxX_
* Text: Now has `IsDraggable` field and improved mouseover detection that supports rotation (#1616, #1599) _Thanks @BambOoxX and @Niravk1997_
* Plot: `Frameless()` no longer results in an image with a 3 pixel transparent border (#1571, #1605) _Thanks @sjlai1993_
* Colorbar: `AddColorbar()` has new optional argument to enable placement on the left side of the plot (#1524) _Thanks @Niravk1997_
* Heatmap: Fixed bug affecting manually-scaled heatmaps (#1485) _Thanks @ZPYin, @mYcheng-95, and @bclehmann_
* Colorbar: Exposed `DataAreaPadding` to improve layout customization for multi-axis plots (#1637) _Thanks @ccopsey_

## ScottPlot 4.1.32
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-01-23_
* Interpolation: New cubic interpolation module with improved stability and simplified API (#1433) _Thanks @allopatin_
* Legend: `GetBitmap()` returns a transparent image instead of throwing an exception if there are no items in the legend (#1578) _Thanks @BambOoxX_
* Legend: Added `Count`, `HasItems`, and `GetItems()` so users can inspect legend contents to if/how they want to display it (#1578) _Thanks @BambOoxX_
* Plot: Exposed `GetDraggable()` to allow users to retrieve the plotted objects at specific pixel positions (#1578) _Thanks @BambOoxX_
* Axis Limits: Improved handling of axis limits for plots containing no data (#1581) _Thanks @EFeru_
* Repeating Axis Line: Improved display of text labels (#1586, #1557) _Thanks @BambOoxX_
* Axis: Improved multi-axis support for `GetPixel()` methods (#1584, #1587) _Thanks @ChrisCC6 and @BambOoxX_
* Error Bar: `Plot.AddErrorBars()` can now be used to place 1D or 2D error bars anywhere on the plot (#1466, #1588) _Thanks @bclehmann_
* Scatter Plot List: Added generic support to `ScatterPlotList<T>` as demonstrated in the cookbook (#1463, #1592) _Thanks @tyrbentsen_
* Draggable Scatter Plot: Created a new `ScatterPlotListDraggable` that supports dragging points and custom clamp logic as seen in the cookbook (#1422) _Thanks @EFeru and @BambOoxX_
* Axis: Users may now customize the number of minor ticks and grid lines when log scale is enabled (#1594, #1595, #1583) _Thanks @hibus_

## ScottPlot 4.1.31
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-01-17_
* MultiAxis: Improved support for draggable items placed on non-primary axes (#1556, #1545) _Thanks @BambOoxX_
* RepeatingAxisLine: New plot types `RepeatingVLine` and `RepeatingHLine` show a primary line and a user-defined number of harmonics. See cookbook for example and usage notes. (#1535, #1775) _Thanks @BambOoxX_
* Scatter: The new `ScatterPlotDraggable` plot type is for creating scatter plots with mouse-draggable points (#1560, #1422) _Thanks @BambOoxX and @EFeru_
* Controls: Improved middle-click-drag zoom rectangle support for plots with multiple axes (#1559, #1537) _Thanks @BambOoxX_
* Marker: New plot types `DraggableMarkerPlot` and `DraggableMarkerPlotInVector` give users options to add mouse-interactive markers to plots (#1558) _Thanks @BambOoxX_
* Bar Plot: New `ValueFormatter` option allows users to customize the text displayed above bars (#1542) _Thanks @jankri_
* Plot: `Title()` now has additional arguments for customizing text above the plot (#1564) _Thanks Hendri_

## ScottPlot 4.1.30
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-01-15_
* Plot: Improve values returned by `GetDataLimits()` when axis lines and spans are in use (#1415, #1505, #1532) _Thanks @EFeru_
* Rendering: Revert default text hinting from ClearType back to AntiAliased to improve text appearance on transparent backgrounds. Users may call `ScottPlot.Drawing.GDI.ClearType(true)` to opt-in to ClearType rendering which is superior for most situations. (#1553, #1550, #1528) _Thanks @r84r, @wangyexiang, @Elgot, @EFeru, and @saklanmazozgur_

## ScottPlot 4.1.29
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-01-02_
* WinForms Control: Improve ClearType text rendering by no longer defaulting to a transparent control background color (#1496)

## ScottPlot 4.1.28
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2022-01-01_
* Eto Control: New ScottPlot control for the Eto GUI framework (#1425, #1438) _Thanks @rafntor_
* Radar Plot: `OutlineWidth` now allows customization of the line around radar plots (#1426, #1277) _Thanks @Rayffer_
* Ticks: Improved minor tick and minor grid line placement (#1420, #1421) _Thanks @bclehmann and @at2software_
* Palette: Added Amber and Nero palettes (#1411, #1412) _Thanks @gauravagrwal_
* Style: Hazel style (#1414) _Thanks @gauravagrwal_
* MarkerPlot: Improved data area clipping (#1423, #1459) _Thanks @PremekTill, @lucabat, and @AndXaf_
* MarkerPlot: Improved key in legend (#1459, #1454) _Thanks @PremekTill and @Logicman111_
* Style: Plottables that implement `IStylable` are now styled when `Plot.Style()` is called. Styles are now improved for `ScaleBar` and `Colorbar` plot types. (#1451, #1447) _Thanks @diluculo_
* Population plot: Population plots `DataFormat` now have a `DataFormat` member that displays individual data points on top of a bar graph representing their mean and variance (#1440) Thanks _@Syntaxrabbit_
* SignalXY: Fixed bug affecting filled plots with zero area (#1476, #1477) _Thanks @chenxuuu_
* Cookbook: Added example showing how to place markers colored according to a colormap displayed in a colorbar (#1461) _Thanks @obnews_
* Ticks: Added option to invert tick mark direction (#1489, #1475) _Thanks @wangyexiang_
* FormsPlot: Improved support for WinForms 6 (#1430, #1483) _Thanks @SuperDaveOsbourne_
* Axes: Fixed bug where `AxisAuto()` failed to adjust all axes in multi-axis plots (#1497) _Thanks @Niravk1997_
* Radial Gauge Plot: Fixed bug affecting rendering of extremely small gauge angles (#1492, #1474) _Thanks @arthurits_
* Text plot and arrow plot: Now have `PixelOffsetX` and `PixelOffsetY` to facilitate small adjustments at render time (#1392)
* Image: New `Scale` property allows customization of image size (#1406)
* Axis: `Plot.GetDataLimits()` returns the boundaries of all data from all visible plottables regardless of the current axis limits (#1415) _Thanks @EFeru_
* Rendering: Improved support for scaled plots when passing scale as a `Plot.Render()` argument (#1416) _Thanks @Andreas_
* Text: Improved support for rotated text and background fills using custom alignments (#1417, #1516) _Thanks @riquich and @AndXaf_
* Text: Added options for custom borders (#1417, #1516) _Thanks @AndXaf and @MachineFossil_
* Plot: New `RemoveAxis()` method allows users to remove axes placed by `AddAxis()` (#1458) _Thanks @gobikulandaisamy_
* Benchmark: `Plot.BenchmarkTimes()` now returns an array of recent frame render times (#1493, #1491) _Thanks @anose001_
* Ticks: Disabling log-scaled minor ticks now disables tick label integer rounding (#1419) _Thanks @at2software_
* Rendering: Improve appearance of text by defaulting to ClearType font rendering (#1496, #823) _Thanks @Elgot_

## ScottPlot 4.1.27
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-10-24_
* Colorbar: Exposed fields for additional tick line and tick label customization (#1360) _Thanks @Maoyao233_
* Plot: Improved `AxisAutoY()` margins (#1363) _Thanks @Maoyao233_
* Radar Plot: `LineWidth` may now be customized (#1277, #1369) _Thanks @bclehmann_
* Controls: Stretching due to display scaling can be disabled with `Configuration.DpiStretch` in WPF and Avalonia controls (#1352, #1364) _Thanks @ktheijs and @bclehmann_
* Axes: Improved support for log-distributed minor tick and grid lines (#1386, #1393) _Thanks @at2software_
* Axes: `GetTicks()` can be used to get the tick positions and labels from the previous render
* WPF Control: Improved responsiveness while dragging with the mouse to pan or zoom (#1387, #1388) _Thanks @jbuckmccready_
* Layout: `MatchLayout()` has improved alignment for plots containing colorbars (#1338, #1349, #1351) _Thanks @dhgigisoave_
* Axes: Added multi-axis support for `SetInnerViewLimits()` and `SetOuterViewLimits()` (#1357, #1361) _Thanks @saroldhand_
* Axes: Created simplified overloads for `AxisAuto()` and `Margins()` that lack multi-axis arguments (#1367) _Thanks @cdytoby_
* Signal Plot: `FillAbove()`, `FillBelow()`, and `FillAboveAndBelow()` methods have been added to simplify configuration and reduce run-time errors. Direct access to fill-related fields has been deprecated. (#1401)
* Plot: `AddFill()` now has an overload to fill between two Y curves with shared X values
* Palette: Made all `Palette` classes public (#1394) _Thanks @Terebi42_
* Colorbar: Added `AutomaticTicks()` to let the user further customize tick positions and labels (#1403, #1362) _Thanks @bclehmann_
* Heatmap: Improved support for automatic tick placement in colorbars (#1403, #1362)
* Heatmap: Added `XMin`, `XMax`, `YMin`, and `YMax` to help configure placement and edge alignment (#1405) _Thanks @bclehmann_
* Coordinated Heatmap: This plot type has been deprecated now that the special functionality it provided is present in the standard `Heatmap` (#1405)
* Marker: Created a new `Marker` class to simplify the marker API. Currently it is a pass-through for `MarkerShape` enumeration members.
* Plot: `AddMarker()` makes it easy to place a styled marker at an X/Y position on the plot. (#1391)
* Plottable: `AddPoint()` now returns a `MarkerPlot` rather than a `ScatterPlot` with a single point (#1407)
* Axis lines: Added `Min` and `Max` properties to terminate the line at a finite point (#1390, #1399) _Thanks @bclehmann_

## ScottPlot 4.1.26
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-10-12_
* SignalPlotYX: Improve support for step display (#1342) _Thanks @EFeru_
* Heatmap: Improve automatic axis limit detection (#1278) _Thanks @bclehmann_
* Plot: Added `Margins()` to set default margins to use when `AxisAuto()` is called without arguments (#1345)
* Heatmap: Deprecated `ShowAxisLabels` in favor of tight margins (see cookbook) (#1278) _Thanks @bclehmann_
* Histogram: Fixed bug affecting binning of values at the upper edge of the final bin (#1348, #1350) _Thanks @jw-suh_
* NuGet: Packages have improved debug experience with SourceLink and snupkg format symbols (#1285)

## ScottPlot 4.1.25
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-10-06_
* Palette: `ScottPlot.Palette` has been created and cookbook recipes have been updated to use it. The module it replaces (`ScottPlot.Drawing.Palette`) will not be marked obsolete until ScottPlot 5. (#1299, #1304)
* Style: Refactored to use static classes instead of enumeration members (#1299, #1291)
* NuGet: Improved System.Drawing.Common dependencies in user control packages (#1311, #1310) _Thanks @Kritner_
* Avalonia Control: Now targets .NET 5 (#1306, #1309) _Thanks @bclehmann_
* Plot: Fixed bug causing `GetPixel()` to return incorrect values for some axes (#1329, #1330) _Thanks @riquich_
* New Palettes:
  * `ColorblindFriendly` modeled after [Wong 2011](https://www.nature.com/articles/nmeth.1618.pdf) (#1312) _Thanks @arthurits_
  * `Dark` (#1313) _Thanks @arthurits_
  * `DarkPastel` (#1314) _Thanks @arthurits_
  * `Redness` (#1322) _Thanks @wbalbo_
  * `SummerSplash (#1317)` _Thanks @KanishkKhurana_
  * `Tsitsulin` 25-color optimal qualitative palette ([described here](http://tsitsul.in/blog/coloropt)) by [Anton Tsitsulin](http://tsitsul.in) (#1318) _Thanks @arthurits and @xgfs_
* New Styles:
  * `Burgundy` (#1319) _Thanks @arthurits_
  * `Earth` (#1320) _Thanks @martinkleppe_
  * `Pink` (#1234) _Thanks @nanrod_

## ScottPlot 4.1.23
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-09-26_
* NuGet: use deterministic builds, add source link support, and include compiler flags (#1285)

## ScottPlot 4.1.22
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-09-26_
* Coxcomb Plots: Added support for image labels (#1265, #1275) _Thanks @Rayffer_
* Palette: Added overloads for `GetColor()` and `GetColors()` to support transparency
* Plot Viewer: fixed bug causing render warning to appear in WinForms and Avalonia plot viewers (#1265, #1238) _Thanks @bukkideme, @Nexus452, and @bclehmann_

## ScottPlot 4.1.21
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-09-18_
* Legend: Throw an exception if `RenderLegend()` is called on a plot with no labeled plottables (#1257)
* Radar: Improved support for category labels. (#1261, #1262) _Thanks @Rayffer_
* Controls: Now have a `Refresh()` method as an alias of `Render()` for manually redrawing the plot and updating the image on the screen. Using `Render()` in user controls is more similar to similar plotting libraries and less likely to be confused with `Plot.Render()` in documentation and warning messages. (#1264, #1270, #1263, #1245, #1165)
* Controls: Decreased visibility of the render warning (introduced in ScottPlot 4.1.19) by allowing it only to appear when the debugger is attached (#1165, #1264)
* Radial Gaugue Plot: Fixed divide-by-zero bug affecting normalized gauges (#1272) _Thanks @arthurits_

## ScottPlot 4.1.20
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-09-09_
* Ticks: Fixed bug where corner labels would not render when multiplier or offset notation is in use (#1252, #1253) _Thanks @DavidBergstromSWE_

## ScottPlot 4.1.19
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-09-08_
* Controls: Fixed bug where render warning message is not hidden if `RenderRequest()` is called (#1165) _Thanks @gigios_

## ScottPlot 4.1.18
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-09-08_
* Ticks: Improve placement when axis scale lock is enabled (#1229, #1197)
* Plot: `SetViewLimits()` replaced by `SetOuterViewLimits()` and `SetInnerViewLimits()` (#1197) _Thanks @noob765_
* Plot: `EqualScaleMode` (an enumeration accepted by `AxisScaleLock()`) now has `PreserveSmallest` and `PreserveLargest` members to indicate which axis to prioritize when adjusting zoom level. The new default is `PreserveSmallest` which prevents data from falling off the edge of the plot when resizing. (#1197) _Thanks @noob765_
* Axis: Improved alignment of 90º rotated ticks (#1194, #1201) _Thanks @gigios_
* Controls: Fix bug where middle-click-drag zoom rectangle would persist if combined with scroll wheel events (#1226) _Thanks @Elgot_
* Scatter Plot: Fixed bug affecting plots where `YError` is set but `XError` is not (#1237, #1238) _Thanks @simmdan_
* Palette: Added `Microcharts` colorset (#1235) _Thanks @arthurits_
* SignalPlotXY: Added support for `FillType` (#1232) _Thanks @ddrrrr_
* Arrow: New plot type for rendering arrows on plots. Arrowhead functionality of scatter plots has been deprecated. (#1241, #1240)
* Controls: Automatic rendering has been deprecated. Users must call Render() manually at least once. (#1165, #1117)
* Radial Gauge Plots: `AddRadialGauge()` now adds a radial gauge plot (a new circular plot type where values are represented as arcs spanning a curve). See cookbook for examples and documentation. (#1242) _Thanks @arthurits_

## ScottPlot 4.1.17
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-08-25_
* Improved `RadarPlot.Update()` default arguments (#1097) _Thanks @arthurits_
* Radar Plot: Improved `Update()` default arguments (#1097) _Thanks @arthurits_
* Crosshair: Added `XLabelOnTop` and `YLabelOnRight` options to improve multi-axis support and label customization (#1147) _Thanks @rutkowskit_
* Signal Plot: Added `StepDisplay` option to render signal plots as step plots when zoomed in (#1092, #1128) _Thanks @EFeru_
* Testing: Improved error reporting on failed XML documentation tests (#1127) _Thanks @StendProg_
* Histogram: Marked `ScottPlot.Statistics.Histogram` obsolete in favor of static methods in `ScottPlot.Statistics.Common` designed to create histograms and probability function curves (#1051, #1166). See cookbook for usage examples. _Thanks @breakwinz and @bclehmann_
* WpfPlot: Improve memory management for dynamically created and destroyed WpfPlot controls by properly unloading the dispatcher timer (#1115, #1117) _Thanks @RamsayGit, @bclehmann, @StendProg, and @Orace_
* Mouse Processing: Improved bug that affected fast drag-dropping of draggable objects (#1076)
* Rendering: Fixed clipping bug that caused some plot types to be rendered above data area frames (#1084)
* Plot: Added `Width` and `Height` properties
* Plot: `GetImageBytes()` now returns bytes for a PNG file for easier storage in cloud applications (#1107)
* Axis: Added a `GetSettings()` method for developers, testers, and experimenters to gain access to experimental objects which are normally private for extreme customization
* Axis: Axis ticks now have a `Ticks()` overload which allows selective control over major tick lines and major tick labels separately (#1118) _Thanks @kegesch_
* Plot: `AxisAuto()` now has `xAxisIndex` and `yAxisIndex` arguments to selectively adjust axes to fit data on a specified index (#1123)
* Crosshair: Refactored to use two `AxisLine`s so custom formatters can now be used and lines can be independently styled (#1173, #1172, #1122, 1195) _Thanks @Maoyao233 and @EFeru_
* ClevelandDotPlot: Improve automatic axis limit detection (#1185) _Thanks @Nextra_
* ScatterPlotList: Improved legend formatting (#1190) _Thanks @Maoyao233_
* Plot: Added an optional argument to `Frameless()` to reverse its behavior and deprecated `Frame()` (#1112, #1192) _Thanks @arthurits_
* AxisLine: Added `PositionLabel` option for displaying position as text (using a user-customizable formatter function) on the axis (#1122, #1195, #1172, #1173) _Thanks @EFeru and @Maoyao233_
* Radar Plot: Fixed rendering artifact that occurred when axis maximum is zero (#1139) _Thanks @petersesztak and @bclehmann_
* Mouse Processing: Improved panning behavior when view limits (axis boundaries) are active (#1148, #1203) _Thanks @at2software_
* Signal Plot: Fixed bug causing render artifacts when using fill modes (#1163, #1205)
* Scatter Plot: Added support for `OffsetX` and `OffsetY` (#1164, #1213)
* Coxcomb: Added a new plot type for categorical data. See cookbook for examples. (#1188) _Thanks @bclehmann_
* Axes: Added `LockLimits()` to control pan/zoom manipulation so individual axes can be manipulated in multi-axis plots. See demo application for example. (#1179, #1210) _Thanks @kkaiser41_
* Vector Plot: Add additional options to customize arrowhead style and position. See cookbook for examples. (#1202) _Thanks @hhubschle_
* Finance Plot: Fixed bug affecting plots with no data points (#1200) _Thanks @Maoyao233_
* Ticks: Improve display of rotated ticks on secondary axes (#1201) _Thanks @gigios_

## ScottPlot 4.1.16
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-05-30_
* Made it easier to use custom color palettes (see cookbook) (#1058, #1082) _Thanks @EFeru_
* Added a `IgnoreAxisAuto` field to axis lines and spans (#999) _Thanks @kirsan31_
* Heatmaps now have a `Smooth` field which uses bicubic interpolation to display smooth heatmaps (#1003) _Thanks @xichaoqiang_
* Radar plots now have an `Update()` method for updating data values without clearing the plot (#1086, #1091) _Thanks @arthurits_
* Controls now automatically render after the list of plottables is modified (previously it was after the number of plottables changed). This behavior can be disabled by setting a public field in the control's `Configuration` module. (#1087, #1088) _Thanks @bftrock_
* New `Crosshair` plot type draws lines to highlight a point on the plot and labels their coordinates in the axes (#999, #1093) _Thanks @kirsan31_
* Added support for a custom `Func<double, string>` to be used as custom tick label formatters (see cookbook) (#926, #1070) _Thanks @damiandixon and @ssalsinha_
* Added `Move`, `MoveFirst`, and `MoveLast` to the `Plot` module for added control over which plottables appear on top (#1090) _Thanks @EFeru_
* Fixed bug preventing expected behavior when calling `AxisAutoX` and `AxisAutoY` (#1089) _Thanks @EFeru__

## ScottPlot 4.1.15
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-05-27_
* Hide design-time error message component at run time to reduce flicking when resizing (#1073, #1075) _Thanks @Superberti and @bclehmann_
* Added a modern `Plot.GetBitmap()` overload suitable for the new stateless rendering system (#913 #1063)
* Controls now have `PlottableDragged` and `PlottableDropped` event handlers (#1072) _Thanks @JS-BGResearch_

## ScottPlot 4.1.14
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-05-23_
* Add support for custom linestyles in SignalXY plots (#1017, #1016) _Thanks @StendProg and @breakwinz_
* Improved Avalonia dependency versioning (#1018, #1041) _Thanks @bclehmann_
* Controls now properly process `MouseEnter` and `MouseLeave` events (#999) _Thanks @kirsan31 and @breakwinz_
* Controls now have a `RenderRequest()` method that uses a render queue to facilitate non-blocking render calls (#813, #1034) _Thanks @StendProg_
* Added Last() to finance plots to make it easier to access the final OHLC (#1038) _Thanks @CalderWhite_
* Controls that fail to render in design mode now display the error message in a textbox to prevent Visual Studio exceptions (#1048) _Thanks @bclehmann_

## ScottPlot 4.1.13-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-05-02_
* `Plot.Render()` and `Plot.SaveFig()` now have a `scale` argument to allow for the creation of high resolution scaled plots (#983, #982, #981) _Thanks @PeterDavidson_
* A `BubblePlot` has been added to allow display of circles with custom colors and sizes. See cookbook for examples. (#984, #973, #960) _Thanks @PeterDavidson_
* Avalonia 0.10.3 is now supported (#986) _Thanks @bclehmann_
* Default version of System.Drawing.Common has been changed from `5.0.0` to `4.6.1` to minimize errors associated with downgrading (#1004, #1005, #993, #924, #655) _Thanks @bukkideme_

## ScottPlot 4.1.12-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-04-12_
* Added "Open in New Window" option to right-click menu (#958, #969) _Thanks @ademkaya and @bclehmann_
* User control `Configuration` module now has customizable scroll wheel zoom fraction (#940, #937) _Thanks @PassionateDeveloper86 and @StendProg_
* Added options to `Plot.AxisScaleLock()` to let the user define scaling behavior when the plot is resized (#933, #857) _Thanks @boingo100p and @StendProg_
* Improved XML documentation for `DataGen` module (#903, #902) _Thanks @bclehmann_
* Fixed bug where tick labels would not render for axes with a single tick (#945, #828, #725, #925) _Thanks @saklanmazozgur and @audun_
* Added option to manually refine tick density (#828) _Thanks @ChrisAtVault and @bclehmann_
* Improved tick density calculations for DateTime axes (#725) _Thanks @bclehmann_
* Fixed SignalXY rendering artifact affecting the right edge of the plot (#929, #931) _Thanks @damiandixon and @StendProg_
* Improved line style customization for signal plots (#929, #931) _Thanks @damiandixon and @StendProg_
* Fixed bug where negative bar plots would default to red fill color (#968, #946) _Thanks @pietcoussens_
* Fixed bug where custom vertical margin was not respected when `AxisAuto()` was called with a middle-click (#943) _Thanks Andreas_
* Added a minimum distance the mouse must travel while click-dragging for the action to be considered a drag instead of a click (#962)
* Improved Histogram documentation and simplified access to probability curves (#930, #932, #971) _Thanks @LB767, @breakwinz, and @bclehmann_

## ScottPlot 4.1.11-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-03-30_
* FormsPlot mouse events are now properly forwarded to the base control (#892, #919) _Thanks @grabul_
* Prevent right-click menu from deploying after right-click-drag (#891, #917)
* Add offset support to SignalXY (#894, #890) _Thanks @StendProg_
* Eliminate rendering artifacts in SignalXY plots (#893, #889) _Thanks @StendProg and @grabul_
* Optimize cookbook generation and test execution (#901) _Thanks @bclehmann_

## ScottPlot 4.1.10-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-03-21_
* Fixed a bug where applying the Seabourn style modified axis frame and minor tick distribution (#866) _Thanks @oszymczak_
* Improved XML documentation and error reporting for getting legend bitmaps (#860) _Thanks @mzemljak_
* Fixed rendering bug affecting finance plots with thin borders (#837) _Thanks @AlgoExecutor_
* Improved argument names and XML docs for SMA and Bollinger band calculation methods (#830) _Thanks @ticool_
* Improved GetPointNearest support for generic signal plots (#809, #882, #886) _Thanks @StendProg, @at2software, and @mrradd_
* Added support for custom slice label colors in pie charts (#883, #844) _Thanks @bclehmann, @StendProg, and @Timothy343_
* Improved support for transparent heatmaps using nullable double arrays (#849, #852) _Thanks @bclehmann_
* Deprecated bar plot `IsHorizontal` and `IsVertical` in favor of an `Orientation` enumeration
* Deprecated bar plot `xs` and `ys` in favor of `positions` and `values` which are better orientation-agnostic names
* Added Lollipop and Cleveland plots as new types of bar plots (#842, #817) _Thanks @bclehmann_
* Fixed a bug where `Plot.AddBarGroups()` returned an array of nulls (#839) _Thanks @rhys-wootton_
* Fixed a bug affecting manual tick labels (#829) _Thanks @ohru131_
* Implemented an optional render queue to allow asynchronous rendering in user controls (#813) _Thanks @StendProg_

## ScottPlot 4.1.9-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-02-21_
* Improved support for negative DateTimes when using DateTime axis mode (#806, #807) _Thanks @StendProg and @at2software_
* Improved axis limit detection when using tooltips (#805, #811) _Thanks @bclehmann and @ChrisAtVault_
* Added `WickColor` field to candlestick plots (#803) _Thanks @bclehmann_
* Improved rendering of candlesticks that open and close at the same price (#803, #800) _Thanks @bclehmann and @AlgoExecutor_
* Improved rendering of SignalXY plots near the edge of the plot (#795) _Thanks @StendProg_
* new `AddScatterStep()` helper method creates a scatter plot with the step style (#808) _Thanks @KlaskSkovby_
* Marked `MultiPlot` obsolete
* Refactored `Colormap` module to use classes instead of reflection (#767, #773) _Thanks @StendProg_
* Refactored `OHLC` fields and finance plots to store `DateTime` and `TimeSpan` instead of `double` (#795)

## ScottPlot 4.1.8-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-02-16_
* Improved validation and error reporting for large heatmaps (#772) _Thanks @Matthias-C_
* Removed noisy console output in `ScatterPlotList` (#780) _Thanks @Scr0nch_
* Improved rendering bug in signal plots (#783, #788) _Thanks @AlgoExecutor and @StendProg_
* Fix bug that hid grid lines in frameless plots (#779)
* Improved appearance of marker-only scatter plots in the legend (#790) _Thanks @AlgoExecutor_
* `AddPoint()` now has a `label` argument to match `AddScatter()` (#787) _Thanks @AlgoExecutor_

## ScottPlot 4.1.7-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-02-14_
* Added support for image axis labels (#759, #446, #716) _Thanks @bclehmann_
* Added `MinRenderIndex` and `MaxRenderIndex` support to Scatter plots (#737, #763) _Thanks @StendProg_
* Improved display of horizontal manual axis tick labels (#724, #762) _Thanks @inqb and @Saklut_
* Added support for listing and retrieving colormaps by their names (#767, #773) _Thanks @StendProg_
* Enabled mouse pan and zoom for plots with infinitely small width and height (#768, #733, #764) _Thanks @saklanmazozgur_
* A descriptive exception is now thrown when attempting to create heatmaps of unsupported dimensions (#722) _Thanks @Matthias-C_

## ScottPlot 4.1.6-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-02-08_
* Fixed single point render bug in Signal plots (#744, #745) _Thanks @at2software and @StendProg_
* Improved display scaling support for WPF control (#721, #720) _Thanks @bclehmann_
* User control `OnAxesChanged` events now send the control itself as the sender object (#743, #756) _Thanks @at2software_
* Fixed configuration bug related to Alt + middle-click-drag-zoom (#741) _Thanks @JS-BGResearch and @bclehmann_
* Fixed render bug related to ALT + middle-click-drag zoom box (#742) _Thanks @bclehmann_
* Fixed render bug for extremely small plots (#735)
* Added a coordinated heatmap plot type (#707) _Thanks @StendProg_
* Improved appearance of heatmap edges (#713) _Thanks @StendProg_
* Improved design-time rendering of Windows Forms control
* Added and expanded XML documentation for Plot and Plottable classes
* Created a new cookbook website generator that combines reflection with XML documentation (#727, #738, #756)
* ScottPlot is now a reserved prefix on NuGet

## ScottPlot 4.1.5-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-02-01_
* Helper methods were added for creating scatter plots with just lines (`AddScatterLines()`) or just markers (`AddScatterPoints()`).
* Scatter and Signal plots have `GetPointNearest()` which now has a `xyRatio` argument to support identifying points near the cursor in pixel space (#709, #722) _Thanks @oszymczak, @StendProg, @bclehmann_
* Improved display of manual tick labels (#724) _Thanks @bclehmann_

## ScottPlot 4.1.4-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2021-01-25_
* User controls have been extensively redesigned (#683)
  * All user controls are almost entirely logic-free and pass events to `ScottPlot.Control`, a shared common back-end module which handles mouse interaction and pixel/coordinate conversions.
  * Controls no longer have a `Configure()` method with numerous named arguments, but instead a `Configuration` field with XML-documented public fields to customize behavior.
  * Renders occur automatically when the number of plottables changes, meaning you do not have to manually call `Render()` when plotting data for the first time. This behavior can be disabled in the configuration.
  * Avalonia 0.10.0 is now supported and uses this new back-end (#656, #700) _Thanks @bclehmann_
  * Events are used to provide custom right-click menu actions.
  * The right-click plot settings window (that was only available from the WinForms control) has been removed.
* New methods were added to `ScottPlot.Statistics.Common` which efficiently find the Nth smallest number, quartiles, or other quantiles from arrays of numbers (#690) _Thanks @bclehmann_
* New tooltip plot type (#696) _Thanks @bclehmann_
* Fixed simple moving average (SMA) calculation (#703) _Thanks @Saklut_
* Improved multi-axis rendering (#706) _Thanks @bclehmann_
* Improved `SetSourceAsync()` for segmented trees (#705, #692) _Thanks @jl0pd and @StendProg_
* Improved layout for axes with rotated ticks (#706, #699) _Thanks @MisterRedactus and @bclehmann_
* ScottPlot now multi-targets more platforms and supports the latest C# language version on modern platforms but restricts the language to C# 7.3 for .NET Framework projects (#691, #711) _Thanks @jl0pd_
* Improved project file to install `System.ValueTuple` when targeting .NET Framework 4.6.1 (#88, #691)

## ScottPlot 4.1.3-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-12-27_
* Scott will make a document to summarize 4.0 → 4.1 changes as we get closer to a non-beta release
* Fixed rendering bug affecting axis spans when zoomed far in (#662) _Thanks @StendProg_
* Improved Gaussian blur performance (#667) _Thanks @bclehmann_
* Largely refactored heatmaps (#679, #680) _Thanks @bclehmann_
* New `Colorbar` plot type (#681)
* Improved SMA and Bollinger band generators (#647) _Thanks @Saklut_
* Improved tick label rounding (#657)
* Improved setting of tick label color (#672)
* Improved fill above and below for scatter plots (#676) _Thanks @MithrilMan_
* Additional customizations for radar charts (#634, #628, #635) _Thanks @bclehmann and @SommerEngineering_

## ScottPlot 4.1.0-beta
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-11-29_
* In November, 2020 ScottPlot 4.0 branched into a permanent `stable` branch, and ScottPlot 4.1 began development as beta / pre-release in the main branch. ScottPlot 4.0 continues to be maintained, but modifications are aimed at small bugfixes rather than large refactoring or the addition of new features. ScottPlot 4.1 merged into the master branch in November, 2020 (#605). Improvements are focused at enhanced performance, improved thread safety, support for multiple axes, and options for data validation.
* Most plotting methods are unchanged so many users will not experience any breaking changes.
* Axis Limits: Axis limits are described by a `AxisLimits` struct (previously `double[]` was used)
* Axis Limits: Methods which modify axis limits do not return anything (previously they returned `double[]`)
* Axis Limits: To get the latest axis limits call `Plot.AxisLimits()` which returns a `AxisLimits` object
* Multiple Axes: Multiple axes are now supported! There is no change to the traditional workflow if this feature is not used.
* Multiple Axes: Most axis methods accept a `xAxisIndex` and `yAxisIndex` arguments to specify which axes they will modify or return
* Multiple Axes: Most plottable objects have `xAxisIndex` and `yAxisIndex` fields which specify which axes they will render on
* Multiple Axes: You can enable a second Y and X axis by calling `YLabel2` and `XLabel2()`
* Multiple Axes: You can obtain an axis by calling `GetXAxis(xAxisIndex)` or `GetYAxis(yAxisIndex)`, then modify its public fields to customize its behavior
* Multiple Axes: The default axes (left and bottom) both use axis index `0`
* Multiple Axes: The secondary axes (right and top) both use axis index `1`
* Multiple Axes: You can create additional axes by calling `Plot.AddAxis()` and customize it by modifying fields of the `Axis` it returns.
* Layout: The layout is re-calculated on every render, so it automatically adjusts to accommodate axis labels and ticks.
* Layout: To achieve extra space around the data area, call `Layout()` to supply a minimum size for each axis.
* Layout: To achieve a frameless plot where the data area fills the full figure, call `LayoutFrameless()`
* Naming: The `Plottable` base class has been replaced with an `IPlottable` interface
* Naming: Plottables have been renamed and moved into a `Plottable` namespace (e.g., `PlottableScatter` is  now `Plottable.ScatterPlot`)
* Naming: Several enums have been renamed
* Settings: It is still private, but you can request it with `Plot.GetSettings()`
* Settings: Many of its objects implement `IRenderable`, so their customization options are stored at the same level as their render methods.
* Rendering: `Bitmap` objects are never stored. The `Render()` method will create and return a new `Bitmap` when called, or will render onto an existing `Bitmap` if it is supplied as an argument. This allows controls to manage their own performance optimization by optionally re-using a `Bitmap` for multiple renders.
* Rendering: Drawing is achieved with `using` statements which respect all `IDisposable` drawing objects, improving thread safety and garbage collection performance.

## ScottPlot 4.0.46
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-12-11_
* Improved ticks for small plots (#724) _Thanks @Saklut_
* Improved display of manual ticks (#724) _Thanks @bclehmann_

## ScottPlot 4.0.45
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-11-25_
* Fixed a bug that affected very small plots with the benchmark enabled (#626) _Thanks @martin-brajer_
* Improved labels in bar graphs using a yOffset (#584) _Thanks Terbaco_
* Added `RenderLock()` and `RenderUnlock()` to the Plot module to facilitate multi-threaded plot modification (#609) _Thanks @ZTaiIT1025_

## ScottPlot 4.0.44
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-11-22_
* Improved limits for fixed-size axis spans (#586) _Thanks @Ichibot200 and @StendProg_
* Mouse drag/drop events now send useful event arguments (#593) _Thanks @charlescao460 and @StendProg_
* Fixed a bug that affected plots with extremely small (<1E-10) axis spans (#607) _Thanks @RFIsoft_
* `Plot.SaveFig()` now returns the full path to the file it created (#608)
* Fixed `AxisAuto()` bug affecting signal plots using min/max render indexes with a custom sample rate (#621) _Thanks @LB767_
* Fixed a bug affecting histogram normalization (#624) _Thanks @LB767_
* WPF and Windows Forms user controls now also target .NET 5
* Improved appearance of semi-transparent legend items (#567)
* Improved tick labels for ticks smaller than 1E-5 (#568) _Thanks @ozgur640_
* Improved support for Avalonia 0.10 (#571) _Thanks @bclehmann and @apkrymov_
* Improved positions for base16 ticks (#582, #581) _Thanks @bclehmann_

## ScottPlot 4.0.42
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-09-27_
* Improved DPI scaling support when using WinForms in .NET Core applications (#563) _Thanks @Ichibot200_
* Improved DPI scaling support for draggable axis lines and spans (#563) _Thanks @Ichibot200_

## ScottPlot 4.0.41
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-09-26_
* Improved density of DateTime ticks (#564, #561) _Thanks @StendProg and @waynetheron_
* Improved display of DateTime tick labels containing multiple spaces (#539, #564) _Thanks @StendProg_

## ScottPlot 4.0.40
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-09-20_
* Added user control for Avalonia (#496, #503) _Thanks @bclehmann_
* Holding shift while left-click-dragging the edge of a span moves it instead of resizing it (#509) _Thanks @Torgano_
* CSV export is now culture invariant for improved support on systems where commas are decimal separators (#512) _Thanks Daniel_
* Added fill support to scatter plots (#529) _Thanks @AlexFsmn_
* Fix bug that occurred when calling `GetLegendBitmap()` before the plot was rendered (#527) _Thanks @el-aasi_
* Improved DateTime tick placement and added support for milliseconds (#539) _Thanks @StendProg_
* Pie charts now have an optional hollow center to produce donut plots (#534) _Thanks @bclehmann and @AlexFsmn_
* Added electrocardiogram (ECG) simulator to the DataGen module (#540) _Thanks @AteCoder_
* Improved mouse scroll wheel responsiveness by delaying high quality render (#545, #543, #550) _Thanks @StendProg_
* `Plot.PlotBitmap()` allows Bitmaps to be placed at specific coordinates (#528) _Thanks @AlexFsmn_
* `DataGen.SampleImage()` returns a sample Bitmap that can be used for testing
* Bar graphs now have a hatchStyle property to customize fill pattern (#555) _Thanks @bclehmann_
* Support timecode tick labels (#537) _Thanks @vrdriver and @StendProg_

## ScottPlot 4.0.39
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-08-09_
* Legend now reflects LineStyle of Signal and SignalXY plots (#488) _Thanks @bclehmann_
* Improved mouse wheel zoom-to-cursor and middle-click-drag rectangle zoom in the WPF control for systems that use display scaling (#490) _Thanks @nashilnik_
* The `Configure()` method of user controls now has a `lowQualityAlways` argument to let the user easily enable/disable anti-aliasing at the control level. Previously this was only configurable by reaching into the control's plot object and calling its `AntiAlias()` method. (#499) _Thanks @RachamimYaakobov_
* SignalXY now supports parallel processing (#500) _Thanks @StendProg_
* SignalXY now respects index-based render limits (#493, #500) _Thanks @StendProg and @envine_

## ScottPlot 4.0.38
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-07-07_
* Improved `Plot.PlotFillAboveBelow()` rendering of data with a non-zero baseline (#477) _Thanks @el-aasi_
* Added `Plot.PlotWaterfall()` for easy creation of waterfall-style bar plots (#463, #476) _Thanks @bclehmann_
* Axis tick labels can be displayed using notations other than base 10 by supplying `Plot.Ticks()` with `base` and `prefix` arguments, allowing axes that display binary (e.g., `0b100110`) or hexadecimal (eg., `0x4B0D10`) tick labels (#469, #457) _Thanks @bclehmann_
* Added options to `PlotBar()` to facilitate customization of text displayed above bars when `showValue` is enabled (#483) _Thanks @WillemWever_
* Plot objects are colored based on a pre-defined set of colors. The default colorset (category10) is the same palette of colors used by matplotlib. A new `Colorset` module has been created to better define this behavior, and `Plot.Colorset()` makes it easy to plot data using alternative colorsets. (#481)
* Fixed a bug that caused instability when a population plot is zoomed-out so much that its fractional distribution curve is smaller than a single pixel (#480) _Thanks @HowardWhile_
* Added `Plot.Remove()` method to make it easier to specifically remove an individual plottable after it has been plotted. `Plot.Clear()` is similar, but designed to remove classes of plot types rather than a specific plot object. (#479) _Thanks @cstyx and @Resonanz_
* Signal plots can now be created with a defined `minRenderIndex` (in addition to the already-supported `maxRenderIndex`) to facilitate partial display of large arrays (#474) _Thanks @bclehmann_

## ScottPlot 4.0.37
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-06-22_
* Fixed a long-running issue related to strong assembly versioning that caused the WPF control to fail to render in the Visual Studio designer in .NET Framework (but not .NET Core) projects (#473, #466, #356) _Thanks @bhairav-thakkar, @riquich, @Helitune-RobMcKay, and @iu2kxv_
* User controls now also target `net472` (while still supporting `net461` and `netcoreapp3.0`) to produce a build folder with just 3 DLLs (compared to over 100 when building with .NET Framework 4.6.1)

## ScottPlot 4.0.36
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-06-22_
* `PlotSignal()` and `PlotSignalXY()` plots now have an optional `useParallel` argument (and public property on the objects they return) to allow the user to decide whether parallel or sequential calculations will be performed. (#454, #419, #245, #72) _Thanks @StendProg_
* Improved minor tick alignment to prevent rare single-pixel artifacts (#417)
* Improved horizontal axis tick label positions in ruler mode (#453)
* Added a `Statistics.Interpolation` module to generate smooth interpolated splines from a small number of input data points. See advanced statistics cookbook example for usage information. (#459) _Thanks Hans-Peter Moser_
* Improved automatic axis adjustment when adding bar plots with negative values (#461, #462) _Thanks @bclehmann_
* Created `Drawing.Colormaps` module which has over a dozen colormaps for easily converting a fractional value to a color for use in plotting or heatmap displays (#457, #458) _Thanks @bclehmann_
* Updated `Plot.Clear()` to accept any `Plottable` as an argument, and all `Plottable` objects of the same type will be cleared (#464) _Thanks @imka-code_

## ScottPlot 4.0.35
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-06-09_
* Added `processEvents` argument to `formsPlot2.Render()` to provide a performance enhancement when linking axes of two `FormsPlot` controls together (by calling `Plot.MatchAxis()` from the control's `AxesChanged` event, as seen in the _Linked Axes_ demo application) (#451, #452) _Thanks @StendProg and @robokamran_
* New `Plot.PlotVectorField()` method for displaying vector fields (sometimes called quiver plots) (#438, #439, #440) _Thanks @bclehmann and @hhubschle_
* Included an experimental colormap module which is likely to evolve over subsequent releases (#420, #424, #442) _Thanks @bclehmann_
* `PlotScatterHighlight()` was created as a type of scatter plot designed specifically for applications where "show value on hover" functionality is desired. Examples are both in the cookbook and WinForms and WPF demo applications. (#415, #414) _Thanks @bclehmann and @StendProg_
* `PlotRadar()` is a new plot type for creating Radar plots (also called spider plots or star plots). See cookbook and demo application for examples. (#428, #430) _Thanks @bclehmann_
* `PlotPlolygons()` is a new performance-optimized variant of `PlotPolygon()` designed for displaying large numbers of complex shapes (#426) _Thanks @StendProg_
* The WinForms control's `Configure()` now has a `showCoordinatesTooltip` argument to continuously display the position at the tip of the cursor as a tooltip (#410) _Thanks @jcbeppler_
* User controls now use SHIFT (previously ALT) to lock the horizontal axis and ALT (previously SHIFT) while left-click-dragging for zoom-to-region. Holding CTRL+SHIFT while right-click-dragging now zooms evenly, without X/Y distortion. (#436) _Thanks @tomwimmenhove and @StendProg_
* Parallel processing is now enabled by default. Performance improvements will be most noticeable on Signal plots. (#419, #245, #72)
* `Plot.PlotBar()` now has an `autoAxis` argument (which defaults `true`) that automatically adjusts the axis limits so the base of the bar graphs touch the edge of the plot area. (#406)
* OSX-specific DLLs are now only retrieved by NuGet on OSX (#433, #211, #212)
* Pie charts can now be made with `plt.PlotPie()`. See cookbook and demo application for examples. (#421, #423) _Thanks @bclehmann_
* `ScottPlot.FormsPlotViewer(Plot)` no longer resets the new window's plot to the default style (#416)  _Thanks @StendProg_
* Controls now have a `recalculateLayoutOnMouseUp` option to prevent resetting of manually-defined data area padding

## ScottPlot 4.0.34
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-05-18_
* Improve display of `PlotSignalXY()` by not rendering markers when zoomed very far out (#402) _Thanks @gobikulandaisamy_
* Optimized rendering of solid lines which have a user-definable `LineStyle` property. This modification improves grid line rendering and increases performance for most types of plots. (#401, #327) _Thanks @bukkideme and @Ichibot200_

## ScottPlot 4.0.33
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-05-18_
* Force grid lines to always draw using anti-aliasing. This compensates for a bug in `System.Drawing` that may cause diagonal line artifacts to appear when the user controls were panned or zoomed. (#401, #327) _Thanks @bukkideme and @Ichibot200_

## ScottPlot 4.0.32
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-05-17_
* User controls now have a `GetMouseCoordinates()` method which returns the DPI-aware position of the mouse in graph coordinates (#379, #380) _Thanks @bclehmann_
* Default grid color was lightened in the user controls to match the default style (#372)
* New `PlotSignalXY()` method for high-speed rendering of signal data that has unevenly-spaced X coordinates (#374, #375) _Thanks @StendProg and @LogDogg_
* Modify `Tools.Log10()` to return `0` instead of `NaN`, improving automatic axis limit detection (#376, #377) _Thanks @bclehmann_
* WpfPlotViewer and FormsPlotViewer launch in center of parent window (#378)
* Improve reliability of `Plot.AxisAutoX()` and `Plot.AxisAutoY()` (#382)
* The `Configure()` method of FormsPlot and WpfPlot controls now have `middleClickMarginX` and `middleClickMarginY` arguments which define horizontal and vertical auto-axis margin used for middle-clicking. Setting horizontal margin to 0 is typical when plotting signals. (#383)
* `Plot.Grid()` and `Plot.Ticks()` now have a `snapToNearestPixel` argument which controls whether these lines appear anti-aliased or not. For static images non-anti-aliased grid lines and tick marks look best, but for continuously-panning plots anti-aliased lines look better. The default behavior is to enable snapping to the nearest pixel, consistent with previous releases. (#384)
* Mouse events (MouseDown, MouseMove, etc.) are now properly forwarded to the FormsPlot control (#390) _Thanks @Minu476_
* Improved rendering of very small candlesticks and OHLCs in financial plots
* Labeled plottables now display their label in the ToString() output. This is useful when viewing plottables listed in the FormsPlot settings window #391 _Thanks @Minu476_
* Added a Statistics.Finance module with methods for creating Simple Moving Average (SMA) and Bollinger band technical indicators to Candlestick and OHLC charts. Examples are in the cookbook and demo program. (#397) _Thanks @Minu476_
* Scatter plots, filled plots, and polygon plots now support Xs and Ys which contain `double.NaN` #396
* Added support for line styles to Signal plots (#392) _Thanks @bukkideme_

## ScottPlot 4.0.31
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-05-06_
* Created `Plot.PlotBarGroups()` for easier construction of grouped bar plots from 2D data (#367) _Thanks @bclehmann_
* Plot.PlotScaleBar() adds an L-shaped scalebar to the corner of the plot (#363)
* Default grid color lightened from #D3D3D3 (Color.LightGray) to #EFEFEF (#372)
* Improved error reporting for scatter plots (#369) _Thanks @JagDTalcyon_
* Improve pixel alignment by hiding grid lines and snapping tick marks that are 1px away from the lower left edge (#359)
* PlotText() ignores defaults to upperLeft alignment when rotation is used (#362)
* Improved minor tick positioning to prevent cases where minor ticks are 1px away from major ticks (#373)

## ScottPlot 4.0.30
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-05-04_
* `Plot.PlotCandlestick()` and `Plot.PlotOHLC()`
  * now support `OHLC` objects with variable widths defined with a new `timeSpan` argument in the OHLC constructor. (#346) _Thanks @Minu476_
  * now support custom up/down colors including those with transparency (#346) _Thanks @Minu476_
  * have a new `sequential` argument to plot data based on array index rather than `OHLC.time`. This is a new, simpler way to display unevenly-spaced data (e.g., gaps over weekends) in a way that makes the gaps invisible. (#346) _Thanks @Minu476_
* Fixed a marker/line alignment issue that only affeced low-density Signal plots on Linux and MacOS (#340) _Thanks @SeidChr_
* WPF control now appears in Toolbox (#151) _Thanks @RalphLAtGitHub_
* Plot titles are now center-aligned with the data area, not the figure. This improves the look of small plots with titles. (#365) _Thanks @Resonanz_
* Fixed bug that ignored `Configure(enableRightClickMenu: false)` in WPF and WinForms user controls. (#365) _Thanks @thunderstatic_
* Updated `Configure(enableScrollWheelZoom: false)` to disable middle-click-drag zooming. (#365) _Thanks @eduhza_
* Added color mixing methods to ScottPlot.Drawing.GDI (#361)
* Middle-click-drag zooming now respects locked axes (#353) _Thanks @LogDogg_
* Improved user control zooming of high-precision DateTime axis data (#351) _Thanks @bukkideme_
* Plot.AxisBounds() now lets user set absolute bounds for drag and pan operations (#349) _Thanks @LogDogg_
* WPF control uses improved Bitmap conversion method (#350)
* Function plots have improved handling of functions with infinite values (#370) _Thanks @bclehmann_

## ScottPlot 4.0.29
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-04-11_
* `Plot.PlotFill()` can be used to make scatter plots with shaded regions. Giving it a single pair of X/Y values (`xs, ys`) lets you shade beneath the curve to the `baseline` value (which defaults to 0). You can also give it a pair of X/Y values (`xs1, ys1, xs2, ys2`) and the area between the two curves will be shaded (the two curves do not need to be the same length). See cookbook for examples. (#255) _Thanks @ckovamees_ 
* `DataGen.Range()` now has `includeStop` argument to include the last value in the returned array.
* `Tools.Pad()` has been created to return a copy of a given array padded with data values on each side. (#255) _Thanks @ckovamees_
* [Seaborn](https://seaborn.pydata.org/) style can be activated using `Plot.Style(Style.Seaborn)` (#339)
* The `enableZooming` argument in `WpfPlot.Configure()` and `FormsPlot.Configure()` has been replaced by two arguments `enableRightClickZoom` and `enableScrollWheelZoom` (#338) _Thanks Zach_
* Improved rendering of legend items for polygons and filled plots (#341) _Thanks @SeidChr_
* Improved Linux rendering of legend items which use thick lines: axis spans, fills, polygons, etc. (#340) _Thanks @SeidChr_
* Addded `Plot.PlotFillAboveBelow()` to create a shaded line plot with different colors above/below the baseline. (#255) _Thanks @ckovamees_
* Improved rendering in Linux and MacOS by refactoring the font measurement system (#340) _Thanks @SeidChr_

## ScottPlot 4.0.28
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-04-07_
* `Ticks()` now has arguments for numericStringFormat (X and Y) to make it easy to customize formatting of tick labels (percentage, currency, scientific notation, etc.) using standard [numeric format strings](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings). Example use is demonstrated in the cookbook. (#336) _Thanks @deiruch_
* The right-click menu can now be more easily customized by writing a custom menu to `FormsPlot.ContextMenuStrip` or `WpfPlot.ContextMenu`. Demonstrations of both are in the demo application. (#337) _Thanks @Antracik_

## ScottPlot 4.0.27
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-04-05_
* `Plot.Polygon()` can now be used to plot polygons from X/Y points (#255) _Thanks @ckovamees_
* User controls now have an "open in new window" item in their right-click menu (#280)
* Plots now have offset notation and multiplier notation disabled by default. Layouts are automatically calculated before the first render, or manually after MouseUp events in the user controls. (#310)
* `Plot.Annotation()` allows for the placement of text on the figure using pixel coordinates (not unit coordinates on the data grid). This is useful for creating custom static labels or information messages. (#321) _Thanks @SeidChr_
* `FormsPlot.MouseDoubleClicked` event now passes a proper `MouseEventArgs` instead of `null` (#331) _Thanks @ismdiego_
* Added a right-click menu to `WpfPlot` with items (save image, copy image, open in new window, help, etc.) similar to `FormsPlot`

## ScottPlot 4.0.26
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-04-05_
* The `ScottPlot.WPF` package (which provides the `WpfPlot` user control) now targets .NET Framework 4.7.2 (in addition to .NET Core 3.0), allowing it to be used in applications which target either platform. The ScottPlot demo application now targets .NET Framework 4.7.2 which should be easier to run on most Windows systems. (#333)
* The `ScottPlot.WinForms` package (which produves the `FormsPlot` control) now only targets .NET Framework 4.6.1 and .NET Core 3.0 platforms (previously it also had build targets for .NET Framework 4.7.2 and .NET Framework 4.8). It is important to note that no functionality was lost here. (#330, #333)

## ScottPlot 4.0.25
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-03-29_
* `PlotBar()` now supports displaying values above each bar graph by setting the `showValues` argument.
* `PlotPopulations()` has extensive capabilities for plotting grouped population data using box plots, bar plots, box and whisper plots, scatter data with distribution curves, and more! See the cookbook for details. (#315)
* `Histogram` objects now have a `population` property.
* `PopulationStats` has been renamed to `Population` and has additional properties and methods useful for reporting population statistics.
* Improved grid rendering rare artifacts which appear as unwanted diagnal lines when anti-aliasing is disabled. (#327)

## ScottPlot 4.0.24
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-03-27_
* `Plot.Clear()` has been improved to more effectively clear plottable objects. Various overloads are provided to selectively clear or preserve certain plot types. (#275) _Thanks @StendProg_
* `PlotBar()` has been lightly refactored. Argument order has been adjusted, and additional options have been added. Error cap width is now in fractional units instead of pixel units. Horizontal bar charts are now supported. (#277, #315) _Thanks @bonzaiferroni_

## ScottPlot 4.0.23
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-03-23_
* Interactive plot viewers were created to make it easy to interactively display data in a pop-up window without having to write any GUI code: `ScottPlot.WpfPlotViewer` for WPF and `ScottPlot.FormsPlotViewer` for Windows Forms
* Fixed bug that affected the `ySpacing` argument of `Plot.Grid()`
* `Plot.Add()` makes it easy to add a custom `Plottable` to the plot
* `Plot.XLabels()` and `Plot.YLabels()` can now accept just a string array (x values are auto-populated as a consecutive series of numbers).
* Aliased `Plot.AxisAuto()` to `Plot.AutoAxis()` and `Plot.AutoScale()` to make this function easier to locate for users who may have experience with other plot libraries. (#309) _Thanks @Resonanz_
* Empty plots now render grid lines, ticks, and tick labels (#313)
* New plot type: Error bars. They allow the user to define error bar size in all 4 directions by calling `plt.PlotErrorBars()`. (#316) _Thanks @zrolfs_
* Improve how dashed lines appear in the legend
* Improved minor tick positions when using log scales with `logScaleX` and `logScaleY` arguments of `plt.Ticks()` method
* Fixed bug that caused the center of the coordinate field to shift when calling `Plot.AxisZoom()`
* Grid line thickness and style (dashed, dotted, etc) can be customized with new arguments in the `Plot.Grid()` method

## ScottPlot 4.0.22
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-03-17_
* Added support for custom horizontal axis tick rotation (#300) _Thanks @SeidChr_
* Added support for fixed grid spacing when using DateTime axes (#299) _Thanks @SeidChr_
* Updated ScottPlot icon (removed small text, styled icon after emoji)
* Improved legend font size when using display scaling (#289)
* Scroll wheel zooming now zooms to cursor (instead of center) in WPF control. This feature works now even if display scaling is used. (#281)
* Added `Plot.EqualAxis` property to make it easy to lock axis scales together (#306) _Thanks @StendProg_

## ScottPlot 4.0.21
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-03-15_
* Created new cookbook and demo applications for WinForms and WPF (#271)
* The `FormsPlot.MouseMoved` event now has `MouseEventArgs` (instead of `EventArgs`). The purpose of this was to make it easy to access mouse pixel coordinates via `e.X` and `e.Y`, but this change may require modifications to applications which use the old event signature.
* WpfPlot now has an `AxisChanged` event (like FormsPlot)
* Fixed bug that caused `Plot.CoordinateFromPixelY()` to return incorrect value
* Fixed bug causing cursor to show arrows when hovered over some non-draggable objects
* Improved support for WinForms and WpfPlot transparency (#286) _Thanks @StendProg and @envine_
* Added `DataGen.Zeros()` and `DataGen.Ones()` to generate arrays filled with values using methods familiar to numpy users.
* Added `equalAxes` argument to `WpfPlot.Configure()` (#272)
* Fixed a bug affecting the `equalAxes` argument in `FormsPlot.Configure()` (#272)
* Made all `Plot.Axis` methods return axis limits as `double[]` (previously many of them returned `void`)
* Added overload for `Plot.PlotLine()` which accepts a slope, offset, and start and end X points to make it easy to plot a linear line with known formula. Using PlotFormula() will produce the same output, but this may be simpler to use for straight lines.
* Added `rSquared` property to linear regression fits (#290) _Thanks @bclehmann and @StendProg_
* Added `Tools.ConvertPolarCoordinates()` to make it easier to display polar data on ScottPlot's Cartesian axes (#298) _Thanks @bclehmann_
* Improved `Plot.Function()` (#243) _Thanks @bclehmann_
* Added overload for `Plot.SetCulture()` to let the user define number and date formatting rather than relying on pre-made cultures (#301, #236) _Thanks @SeidChr_

## ScottPlot 4.0.19
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-02-29_
* Improved how markers are drawn in Signal and SignalConst plots at the transition area between zoomed out and zoomed in (#263) _Thanks @bukkideme and @StendProg_
* Improved support for zero lineSize and markerSize in Signal and SignalConst plots (#263, #264) _Thanks @bukkideme and @StendProg_
* Improved thread safety of interactive graphs (#245) _Thanks @StendProg_
* Added `CoordinateFromPixelX()` and `CoordinateFromPixelY()` to get _double precision_ coordinates from a pixel location. Previously only SizeF (float) precision was available. This improvement is especially useful when using DateTime axes. (#269) _Thanks Chris_
* Added `AxisScale()` to adjust axis limits to set a defined scale (units per pixel) for each axis.
* Added `AxisEqual()` to adjust axis limits to set the scale of both axes to be the same regardless of the size of each axis (#272) _Thanks @gberrante_
* `PlotHSpan()` and `PlotVSpan()` now return `PlottableHSpan` and `PlottableVSpan` objects (instead of a `PlottableAxSpan` with a `vertical` property)
* `PlotHLine()` and `PlotVLine()` now return `PlottableHLine` and `PlottableVLine` objects (instead of a `PlottableAxLine` with a `vertical` property)
* MultiPlot now has a `GetSubplot()` method which returns the Plot from a row and column index (#242) _Thanks @Resonanz and @StendProg_
* Created `DataGen.Range()` to make it easy to create double arrays with evenly spaced data (#259)
* Improved support for display scaling (#273) _Thanks @zrolfs_
* Improved event handling (#266, #238) _Thanks @StendProg_
* Improved legend positioning (#253) _Thanks @StendProg_

## ScottPlot 4.0.18
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-02-07_
* Added `Plot.SetCulture()` for improved local culture formatting of numerical and DateTime axis tick labels (#236) _Thanks @teejay-87_

## ScottPlot 4.0.17
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-02-06_
* Added `mouseCoordinates` property to WinForms and WPF controls (#235) _Thanks @bukkideme_
* Fixed rendering bug that affected horizontal lines when anti-aliasing was turned off (#232) _Thanks @StendProg_
* Improved responsiveness while dragging axis lines and axis spans (#228) _Thanks @StendProg_

## ScottPlot 4.0.16
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-02-02_
* Improved support for MacOS and Linux (#211, #212, #216) _Thanks @hexxone and @StendProg_
* Fixed a bug affecting the `ySpacing` argument in `Plot.Grid()` (#221) _Thanks @teejay-87_
* Enabled `visible` argument in `Title()`, `XLabel()`, and `YLabel()` (#222) _Thanks @ckovamees_
* AxisSpan: Edges are now optionally draggable (#228) _Thanks @StendProg_
* AxisSpan: Can now be selectively removed with `Clear()` argument
* AxisSpan: Fixed bug caused by zooming far into an axis span (#226) _Thanks @StendProg_
* WinForms control: now supports draggable axis lines and axis spans
* WinForms control: Right-click menu now has "copy image" option (#220)
* WinForms control: Settings screen now has "copy CSV" button to export data (#220)
* WPF control: now supports draggable axis lines and axis spans
* WPF control: Configure() to set various WPF control options
* Improved axis handling, expansion, and auto-axis (#219, #230) _Thanks @StendProg_
* Added more options to `DataGen.Cos()`
* Tick labels can be hidden with `Ticks()` argument (#223) _Thanks @ckovamees_

## ScottPlot 4.0.14
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-01-24_
* Improved `MatchAxis()` and `MatchLayout()` (#217) _Thanks @ckovamees and @StendProg_

## ScottPlot 4.0.13
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-01-21_
* Improved support for Linux and MacOS _Thanks @hexxone_
* Improved font validation (#211, #212) _Thanks @hexxone and @StendProg_

## ScottPlot 4.0.11
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-01-19_
* User controls now have a `cursor` property which can be set to allow custom cursors. (#187) _Thanks @gobikulandaisamy_
* User controls now have a `mouseCoordinates` property which make it easy to get the X/Y location of the cursor. (#187) _Thanks @gobikulandaisamy_

## ScottPlot 4.0.10
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2020-01-18_
* Improved density colormap (#192, #194) _Thanks @StendProg_
* Added linear regression tools and cookbook example (#198) _Thanks @bclehmann_
* Added `maxRenderIndex` to Signal to allow partial plotting of large arrays intended to be used with live, incoming data (#202) _Thanks @StendProg and @plumforest_
* Made _Shift + Left-click-drag_ zoom into a rectangle light middle-click-drag (in WinForms and WPF controls) to add support for mice with no middle button (#90) _Thanks @JagDTalcyon_
* Throw an exception if `SaveFig()` is called before the image is properly sized (#192) _Thanks @karimshams and @StendProg_
* `Ticks()` now has arguments for `FontName` and `FontSize` (#204) _Thanks Clay_
* Fixed a bug that caused poor layout due to incorrect title label size estimation (#205) _Thanks Clay_
* `Grid()` now has arguments to selectively enable/disable horizontal and vertical grid lines (#206) _Thanks Clay_
* Added tool and cookbook example to make it easier to plot data on a log axis (#207) _Thanks @senged_
* Arrows can be plotted using `plt.PlotArrow()` (#201) _Thanks Clay_

## ScottPlot 4.0.9
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-12-03_
* Use local regional display settings when formatting the month tick of DateTime axes. (#108) _Thanks @FadyDev2_
* Debug symbols are now packaged in the NuGet file

## ScottPlot 4.0.7
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-12-01_\
* Added WinForms support for .NET Framework 4.7.2 and 4.8
* Fixed bug in WinForms control that only affected .NET Core 3.0 applications (#189, #138) _Thanks @petarpetrovt_

## ScottPlot 4.0.6
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-11-29_\
* fixed bug that affected the settings dialog window in the WinForms control. (#187) _Thanks @gobikulandaisamy_

## ScottPlot 4.0.5
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-11-27_
* improved spacing for non-uniformly distributed OHLC and candlestick plots. (#184) _Thanks @Luvnet-890_
* added `fixedLineWidth` to `Legend()` to allow the user to control whether legend lines are dynamically sized. (#185) _Thanks @ab-tools_
* legend now hides lines or markers of they're hidden in the plottable
* DateTime axes now use local display format (#108) _Thanks @FadyDev2_

## ScottPlot 4.0.4
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-11-24_
* `PlotText()` now supports a background frame (#181) _Thanks @Luvnet-890_
* OHLC objects can be created with a double or a DateTime (#182) _Thanks @Minu476_
* Improved `AxisAuto()` fixes bug for mixed 2d and axis line plots

## ScottPlot 4.0.3
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-11-23_
* Fixed bug when plotting single-point candlestick (#172) _Thanks @Minu476_
* Improved style editing of plotted objects (#173) _Thanks @Minu476_
* Fixed pan/zoom axis lock when holding CTRL or ALT (#90) _Thanks @FadyDev2_
* Simplified the look of the user controls in designer mode
* Improved WPF control mouse tracking when using DPI scaling
* Added support for manual tick positions and labels (#174) _Thanks @Minu476_
* Improved tick system when using DateTime units (#108) _Thanks @Padanian, @FadyDev2, and @Bhandejiya_
* Created `Tools.DateTimesToDoubles(DateTime[] array)` to easily convert an array of dates to doubles which can be plotted with ScottPlot, then displayed as time using `plt.Ticks(dateTimeX: true)`.
* Added an inverted sign flag to allow display of an axis with descending units. (#177) _Thanks Bart_

## ScottPlot 4.0.2
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-11-09_
* Multi-plot figures: Images with several plots can be created using `ScottPlot.MultiPlot()`
* `ScottPlot.DataGen` functions which require a `Random` can accept null (they will create a `Random` if null is given)
* `plt.MatchAxis()` and `plt.MatchLayout()` have been improved
* `plt.PlotText()` now supports rotated text using the `rotation` argument. (#160) _Thanks @gwilson9_
* `ScottPlot.WinForms` user control has new events and `formsPlot1.Configure()` arguments to make it easy to replace the default functionality for double-clicking and deploying the right-click menu (#166). _Thanks @FadyDev2_
* All plottables now have a `visible` property which makes it easy to toggle visibility on/off after they've been plotted. _Thanks @Nasser_

## ScottPlot 4.0.1
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-11-03_
* ScottPlot now targets .NET Standard 2.0 so in addition to .NET Framework projects it can now be used in .NET Core applications, ASP projects, Xamarin apps, etc.
* The WinForms control has its own package which targets both .NET Framework 4.6.1 and .NET Core 3.0 _Thanks @petarpetrovt_
* The WPF control has its own package targeting .NET Core 3.0 _Thanks @petarpetrovt_
* Better layout system and control of padding _Thanks @Ichibot200_
* Added ruler mode to `plt.Ticks()` _Thanks @Ichibot200_
* `plt.MatchLayout()` no longer throws exceptions
* Eliminated `MouseTracker` class (tracking is now in user controls)
* Use NUnit (not MSTest) for tests

## ScottPlot 3.1.6
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-10-20_
* Reduced designer mode checks to increase render speed _Thanks @StendProg_
* Fixed cursor bug that occurred when draggable axis lines were used _Thanks @Kamran_
* Fully deleted the outdated `ScottPlotUC`
* Fixed infinite zoom bug caused by calling AxisAuto() when plotting a single point (or perfectly straight horizontal or vertical line)
* Added `ToolboxItem` and `DesignTimeVisible` delegates to WpfPlot control to try to get it to appear in the toolbox (but it doesn't seem to be working)
* Improved figure padding when axes frames are disabled _Thanks @Ichibot200_
* Improved rendering of ticks at the edge of the plottable area _Thanks @Ichibot200_
* Added `AxesChanged` event to user control to make it easier to sync axes between multiple plots
* Disabled drawing of arrows on user control in designer mode

## ScottPlot 3.1.5
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-10-06_
* WPF user control improved support for display scaling _Thanks @morningkyle_
* Fixed bug that crashed on extreme zoom-outs _Thanks @morningkyle_
* WPF user control improvements (middle-click autoaxis, scrollwheel zoom)
* ScottPlot user control has a new look in designer mode. Exceptions in user controls in designer mode can crash Visual Studio, so this risk is greatly reduced by not attempting to render a ScottPlot _inside_ Visual Studio.

## ScottPlot 3.1.4
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-09-22_
* middle-click-drag zooms into a rectangle drawn with the mouse
* Fixed bug that caused user control to crash Visual Studio on some systems that used DPI scaling. (#125, #111) _Thanks @ab-tools and @bukkideme_
* Fixed poor rendering for extremely small plots
* Fixed bug when making a scatter plot with a single point (#126). _Thanks @bonzaiferroni_
* Added more options to right-click settings menu (grid options, legend options, axis labels, editable plot labels, etc.)
* Improved axis padding and image tightening
* Greatly refactored the settings module (no change in functionality)

## ScottPlot 3.1.3
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-08-25_
* FormsPlot: middle-click-drag zooms into a rectangle
* FormsPlot: CTRL+scroll to lock vertical axis
* FormsPlot: ALT+scroll to loch horizontal axis
* FormsPlot: Improved (and overridable) right-click menu
* Ticks: rudimentary support for date tick labels (`dateTimeX` and `dateTimeY`)
* Ticks: options to customize notation (`useExponentialNotation`, `useOffsetNotation`, and `useMultiplierNotation`)

## ScottPlot 3.1.0
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-08-19_
* `ScottPlotUC` was renamed to `FormsPlot`
* `ScottPlotWPF` was renamed to `WpfPlot`
* The right-click menu has improved. It responds faster and has improved controls to adjust plot settings.
* Plots can now be saved in BMP, PNG, JPG, and TIF format
* Holding `CTRL` while click-dragging locks the horizontal axis
* Holding `ALT` while click-dragging locks the vertical axis
* Minor ticks are now displayed (and can be turned on or off with `Ticks()`)
* Legend can be accessed for external display with `GetLegendBitmap()`
* anti-aliasing is turned off while click-dragging to increase responsiveness (#93) _Thanks @StendProg_
* `PlotSignalConst` now has support for generics and improved performance using single-precision floating-point math. _Thanks @StendProg_
* Legend draws more reliably (#104, #106) _Thanks @StendProg_
* `AxisAuto()` now has `expandOnly` arguments
* Axis lines with custom lineStyles display properly in the legend

## ScottPlot 3.0.9
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-08-12_
* New Plot Type: `PlotSignalConst` for extremely large arrays of data which are not expected to change after being plotted. Plots generated with this method can be much faster than `PlotSignal`. (#70) _Thanks @StendProg_
* Greatly improved axis tick labels. Axis tick labels are now less likely to overlap with axis labels, and it displays very large and very small numbers well using exponential notation. (#47, #68) _Thanks @Padanian_
* Parallel processing support for `SignalPlot` (#72) _Thanks @StendProg_
* Every `Plot` function now returns a `Plottable`. When creating things like scatter plots, text, and axis lines, the returned object can now be used to update the data, position, styling, or call plot-type-specific methods.
* Right-click menu now displays ScottPlot and .NET Framework version
* Improved rendering of extremely zoomed-out signals 
* Rendering speed increased now that `Format32bppPArgb` is the default PixelFormat (#83) _Thanks @StendProg_
* `DataGen.NoisySin()` was added
* Code was tested in .NET Core 3.0 preview and compiled without error. Therefore, the next release will likely be for .NET Core 3.0 (#85, #86) _Thanks @petarpetrovt_
* User controls now render graphs with anti-alias mode off (faster) while the mouse is being dragged. Upon release a high quality render is performed.

## ScottPlot 3.0.8
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-08-04_
* WPF User Control: A ScottPlotWPF user control was created to allow provide a simple mouse-interactive ScottPlot control to WPF applications. It is not as full-featured as the winforms control (it lacks a right-click menu and click-and-drag functions), but it is simple to review the code (<100 lines) and easy to use.
* New plot type: `plt.AxisSpan()` shades a region of the graph (semi-transparency is supported)
* Ticks: Vertical ticks no longer overlap with vertical axis label (#47) _Thanks @bukkideme_
* Ticks: When axis tick labels contain very large or very small numbers, scientific notation mode is engaged
* Ticks: Horizontal tick mark spacing increased to prevent overlapping
* Ticks: Vertical tick mark spacing increased to be consistent with horizontal tick spacing
* Plottable objects now have a `SaveCSV(filename)` method. Scatter and Signal plot data can be saved from the user control through the right-click menu.
* Added `lineStyle` arguments to Scatter plots
* Improved legend: ability to set location, ability to set shadow direction, markers and lines are now rendered in the legend
* Improved ability to use custom fonts
* Segoe UI is now the default font for all plot components

## ScottPlot 3.0.7
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-07-27_
* New plot type: `plt.PlotStep()`
* New plot type `plt.PlotCandlestick()`
* New plot type `plt.PlotOHLC()`
* `plt.MatchPadding()` copies the data frame layout from one ScottPlot onto another (useful for making plots of matching size)
* `plt.MatchAxis()` copies the axes from one ScottPlot onto another (useful for making plots match one or both axis)
* `plt.Legend()` improvements: The `location` argument allows the user to place the legend at one of 9 different places on the plot. The `shadowDirection` argument allows the user to control if a shadow is shown and at what angle.
* Custom marker shapes can be specified using the `markerShape` argument.

## ScottPlot 3.0.6
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-06-30_
* Bar plot: The plot module now has a `Bar()` method that lets users create various types of bar plots
* Histogram: The new `ScottPlot.Histogram` class has tools to create and analyze histogram data (including cumulative probability)
* Step plot: Scatter plots can now render as step plots. Use this feature by setting the `stepDisplay` argument with `PlotScatter()`
* Manual grid spacing: Users can now manually define the grid density by setting the `xSpacing` and `ySpacing` arguments in `Grid()`
* Draggable axis lines: Axis lines can be dragged with the mouse if the `draggable` argument is set to `true` in `PlotHLine()` and `PlotHLine()`. Draggable axis line limits can also be set by defining additional arguments.
* Using the scrollwheel to zoom now zooms to the cursor position rather than the center of the plot area
* `ScottPlot.DataGen.RandomNormal()` was created to create arbitrary amounts of normally-distributed random data
* Fixed bug causing axis line color to appear incorrectly in the legend
* `AxisAuto()` is now called automatically on the first render. This means users no longer have to call this function manually for most applications. This simplifies quickstart programs to just: instantiate plot, plot data, render (now 3 lines in total instead of 4).
* Throw exceptions if scatter, bar, or signal data inputs are null (rather than failing later)

## ScottPlot 3.0.5
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-06-23_
* Improved pan and zoom performance

## ScottPlot 3.0.4
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-06-23_
* Bar graphs: New `plotBar()` method allow creation of bar graphs. By customizing the `barWidth` and `xOffset` arguments you can push bars together to create grouped bar graphs. Error bars can also be added with the `yError` argument.
* Scatter plots support X and Y error bars: `plotScatter()` now has arguments to allow X and Y error bars with adjustable error bar line width and cap size.
* Draggable axis lines: `plotHLine()` and `plotVLine()` now have a `draggable` argument which lets those axis lines be dragged around with the mouse (#11) _Thanks @plumforest_
* Fixed errors caused by resizing to 0px
* Fixed a capitalization inconsistency in the `plotSignal` argument list
* `axisAuto()` now includes positions of axis lines (previously they were ignored)
* Fixed an that caused SplitContainer splitters to freeze (#23) _Thanks @bukkideme_

## ScottPlot 3.0.3
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-05-29_
* Update NuGet package to depend on System.Drawing.Common

## ScottPlot 3.0.2
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-05-28_
* Changed target from .NET Framework 4.5 to 4.7.2 (#15) _Thanks @plumforest_

#### ScottPlot 3.0.1
_Published on [NuGet](https://www.nuget.org/profiles/ScottPlot) on 2019-05-28_
* First version of ScottPlot published on NuGet
