# 幻灯片制作


Markdown Preview Enhanced 使用 [reveal.js](https://github.com/hakimel/reveal.js) 来渲染漂亮的幻灯片。

[点击这里](https://rawgit.com/shd101wyy/markdown-preview-enhanced/master/docs/presentation-intro.html) 查看相关的介绍。

You can easily create beautiful presentation by running command

`Markdown Preview Enhanced: Insert New Slide`

Or just insert to your markdown file

![presentation](https://user-images.githubusercontent.com/1908863/28202176-caf103c4-6839-11e7-8776-942679f3698b.gif)


## Presentation Front-Matter

你可以通过 `front-matter` 来设置你的幻灯片。  
你需要将你的设置写在 `presentation` 部分下。  
例如：

```markdown
---
presentation:
  width: 800
  height: 600
---

<!-- slide -->

在这里编写你的幻灯片。。。
```

这个幻灯片将会拥有 `800x600` 的大小。




### 设置


```yaml
---
presentation:
  # presentation 主题
  # === 可选的主题 ===
  # "beige.css"
  # "black.css"
  # "blood.css"
  # "league.css"
  # "moon.css"
  # "night.css"
  # "serif.css"
  # "simple.css"
  # "sky.css"
  # "solarized.css"
  # "white.css"
  # "none.css"
  theme: white.css

  # The "normal" size of the presentation, aspect ratio will be preserved
  # when the presentation is scaled to fit different resolutions. Can be
  # specified using percentage units.
  width: 960
  height: 700

  # Factor of the display size that should remain empty around the content
  margin: 0.1

  # Bounds for smallest/largest possible scale to apply to content
  minScale: 0.2
  maxScale: 1.5

  # Display controls in the bottom right corner
  controls: true

  # Display a presentation progress bar
  progress: true

  # Display the page number of the current slide
  slideNumber: false

  # Push each slide change to the browser history
  history: false

  # Enable keyboard shortcuts for navigation
  keyboard: true

  # Enable the slide overview mode
  overview: true

  # Vertical centering of slides
  center: true

  # Enables touch navigation on devices with touch input
  touch: true

  # Loop the presentation
  loop: false

  # Change the presentation direction to be RTL
  rtl: false

  # Randomizes the order of slides each time the presentation loads
  shuffle: false

  # Turns fragments on and off globally
  fragments: true

  # Flags if the presentation is running in an embedded mode,
  # i.e. contained within a limited portion of the screen
  embedded: false

  # Flags if we should show a help overlay when the questionmark
  # key is pressed
  help: true

  # Flags if speaker notes should be visible to all viewers
  showNotes: false

  # Number of milliseconds between automatically proceeding to the
  # next slide, disabled when set to 0, this value can be overwritten
  # by using a data-autoslide attribute on your slides
  autoSlide: 0

  # Stop auto-sliding after user input
  autoSlideStoppable: true

  # Enable slide navigation via mouse wheel
  mouseWheel: false

  # Hides the address bar on mobile devices
  hideAddressBar: true

  # Opens links in an iframe preview overlay
  previewLinks: false

  # Transition style
  transition: 'default' # none/fade/slide/convex/concave/zoom

  # Transition speed
  transitionSpeed: 'default' # default/fast/slow

  # Transition style for full page slide backgrounds
  backgroundTransition: 'default' # none/fade/slide/convex/concave/zoom

  # Number of slides away from the current that are visible
  viewDistance: 3

  # Parallax background image
  parallaxBackgroundImage: '' # e.g. "'https://s3.amazonaws.com/hakim-static/reveal-js/reveal-parallax-1.jpg'"

  # Parallax background size
  parallaxBackgroundSize: '' # CSS syntax, e.g. "2100px 900px"

  # Number of pixels to move the parallax background per slide
  # - Calculated automatically unless specified
  # - Set to 0 to disable movement along an axis
  parallaxBackgroundHorizontal: null
  parallaxBackgroundVertical: null

  # Parallax background image
  parallaxBackgroundImage: '' # e.g. "https://s3.amazonaws.com/hakim-static/reveal-js/reveal-parallax-1.jpg"

  # Parallax background size
  parallaxBackgroundSize: '' # CSS syntax, e.g. "2100px 900px" - currently only pixels are supported (don't use % or auto)

  # Number of pixels to move the parallax background per slide
  # - Calculated automatically unless specified
  # - Set to 0 to disable movement along an axis
  parallaxBackgroundHorizontal: 200
  parallaxBackgroundVertical: 50

  # Enable Speake Notes
  enableSpeakerNotes: false
---
```

## 自定义幻灯片样式

你可以添加 `id` 以及 `class` 到一个特定的幻灯片：

```markdown
<!-- slide id="my-id" class="my-class1 my-class2" -->
```

或者你也可以自定义第 `nth` 个幻灯片，编写你的 `less` 如下：

```less
.markdown-preview.markdown-preview {
  // 自定义 presentation 样式
  .reveal .slides {
    // 修改所有幻灯片
  }

  // 自定义 presentation 样式
  .slides > section:nth-child(1) {
    // 修改 `第 1 个幻灯片`
  }
}
```
## Element Attributes

Special syntax (through HTML comments) is available for adding attributes to Markdown elements. This is useful for fragments, among other things.

```
    - Item 1 <!-- .element: class="fragment" data-fragment-index="2" -->
    - Item 2 <!-- .element: class="fragment" data-fragment-index="1" -->
```

## Slide Attributes
Special syntax (through HTML comments) is available for adding attributes to the slide  elements generated by your Markdown.

```
  <!-- slide data-background="#ff0000" -->
    Markdown content
```

### Slide Visibility
When preparing a presentation it can sometimes be helpful to prepare optional slides that you may or may not have time to show. This is easily done by appending a few slides at the end of the presentation, however this means that the reveal.js progress bar and slide numbering will hint that there are additional slides.

To "hide" those slides from reveal.js' numbering system you can add a `data-visibility` attribute to the slide. （似乎未起作用）

```
<!-- slide  data-visibility="uncounted" -->
```


## Slide Backgrounds
Slides are contained within a limited portion of the screen by default to allow them to fit any display and scale uniformly. You can apply full page backgrounds outside of the slide area by adding a data-background attribute to your `slide` elements. Four different types of backgrounds are supported: color, image, video and iframe.

### Color Backgrounds
All CSS color formats are supported, including `hex values`, `keywords`, `rgba()` or `hsl()`.

```
<!-- slide data-background-color="aquamarine" -->
## 🐟

<!-- slide data-background-color="rgb(70, 70, 255)" -->
## 🐳
```
### Image Backgrounds
By default, background images are resized to cover the full page. Available options:

Attribute	| Default | Description
-- | -- | --
data-background-image	|	 | URL of the image to show. GIFs restart when the slide opens.
data-background-size	| cover	| See [background-size](https://developer.mozilla.org/docs/Web/CSS/background-size) on MDN.
data-background-position | center	| See [background-position](https://developer.mozilla.org/docs/Web/CSS/background-position) on MDN.
data-background-repeat	| no-repeat	| See [background-repeat](https://developer.mozilla.org/docs/Web/CSS/background-repeat) on MDN.
data-background-opacity	| 1	| Opacity of the background image on a 0-1 scale. 0 is transparent and 1 is fully opaque.

```
<!-- slide data-background-image="https://static.boredpanda.com/blog/wp-content/uploads/2017/11/My-most-popular-pic-since-I-started-dog-photography-5a0b38cbd5e1e__880.jpg" -->

## background Image <!-- .element: style={color:white}  -->

<!-- slide data-background-image="https://tse3-mm.cn.bing.net/th/id/OIP.S5j-APUCScnmR72MOfYtIwAAAA?pid=Api&w=464&h=350&rs=1"   data-background-size="500px" data-background-repeat="repeat"  -->
## This background image will be sized to 100px and repeated

```

### Video Backgrounds
Automatically plays a full size video behind the slide.

Attribute	| Default	| Description
-- | -- | --
data-background-video	|  | A single video source, or a comma separated list of video sources.
data-background-video-loop | false	| Flags if the video should play repeatedly.
data-background-video-muted	| false	| Flags if the audio should be muted.
data-background-size | cover	| Use `cover` for full screen and some cropping or `contain` for letterboxing.
data-background-opacity	| 1	| Opacity of the background video on a 0-1 scale. 0 is transparent and 1 is fully opaque.
```
<!-- slide  data-background-video="https://static.slid.es/site/homepage/v1/homepage-video-editor.mp4"  data-background-video-loop data-background-video-muted -->

## Video
```
### Iframe Backgrounds
Embeds a web page as a slide background that covers 100% of the reveal.js width and height. The iframe is in the background layer, behind your slides, and as such it's not possible to interact with it by default. To make your background interactive, you can add the `data-background-interactive` attribute.

Attribute	| Default	| Description
-- | -- | --
data-background-iframe	|  |	URL of the iframe to load
data-background-interactive	| false	| Include this attribute to make it possible to interact with the iframe contents. Enabling this will prevent interaction with the slide content.
```
<!-- slide  data-background-iframe="https://bing.com" data-background-interactive  -->
## Iframe
```
Iframes are lazy-loaded when they become visible. If you'd like to preload iframes ahead of time, you can append a data-preload attribute to the slide <section>. You can also enable preloading globally for all iframes using the preloadIframes configuration option.

### Background Transitions
We'll use a cross fade to transition between slide backgrounds by default. This can be changed using the backgroundTransition config option.

### Parallax Background
If you want to use a parallax scrolling background, set the first two properties below when initializing reveal.js (the other two are optional).(这个没有试验可用性，但是应该会使得场景时效)

```

  // Parallax background image
  parallaxBackgroundImage: '', // e.g. "https://s3.amazonaws.com/hakim-static/reveal-js/reveal-parallax-1.jpg"

  // Parallax background size
  parallaxBackgroundSize: '', // CSS syntax, e.g. "2100px 900px" - currently only pixels are supported (don't use % or auto)

  // Number of pixels to move the parallax background per slide
  // - Calculated automatically unless specified
  // - Set to 0 to disable movement along an axis
  parallaxBackgroundHorizontal: 200,
  parallaxBackgroundVertical: 50

```
Make sure that the background size is much bigger than screen size to allow for some scrolling. View example.

## Media
We provide convenient mechanics for autoplaying and lazy loading HTML media elements and iframes based on slide visibility and proximity. This works for `<video>`, `<audio>` and `<iframe>` elements.

### Autoplay
Add `data-autoplay` to your media element if you want it to automatically start playing when the slide is shown:

```
<!-- slide -->

video

<video data-autoplay src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4"></video>
```

If you want to enable or disable autoplay globally, for all embedded media, you can use the `autoPlayMedia` configuration option. If you set this option to true ALL media will autoplay regardless of individual data-autoplay attributes. If you set it to `autoPlayMedia: false` NO media will autoplay.


Note that embedded HTML `<video>`/`<audio>` and YouTube/Vimeo `iframes` are automatically paused when you navigate away from a slide. This can be disabled by decorating your element with a data-ignore attribute.

### Lazy Loading
When working on presentations with a lot of media or iframe content it's important to load lazily. Lazy loading means that reveal.js will only load content for the few slides nearest to the current slide. The number of slides that are preloaded is determined by the viewDistance configuration option.

To enable lazy loading all you need to do is change your src attributes to `data-src` as shown below. This is supported for image, video, audio and iframe elements.

```
  <img data-src="image.png">
  <iframe data-src="https://hakim.se"></iframe>
  <video>
    <source data-src="video.webm" type="video/webm" />
    <source data-src="video.mp4" type="video/mp4" />
  </video>
```

#### Lazy Loading Iframes
Note that lazy loaded iframes ignore the viewDistance configuration and will only load when their containing slide becomes visible. Iframes are also unloaded as soon as the slide is hidden.

When we lazy load a video or audio element, reveal.js won't start playing that content until the slide becomes visible. However there is no way to control this for an iframe since that could contain any kind of content. That means if we loaded an iframe before the slide is visible on screen it could begin playing media and sound in the background.

You can override this behavior with the `data-preload` attribute. The iframe below will be loaded according to the viewDistance.

```
  <iframe data-src="https://hakim.se" data-preload></iframe>
```

You can also change the default globally with the preloadIframes configuration option. If set to true ALL iframes with a data-src attribute will be preloaded when within the viewDistance regardless of individual data-preload attributes. If set to false, all iframes will only be loaded when they become visible.

### Iframes
Using iframes is a convenient way to include content from external sources, like a YouTube video or Google Sheet. reveal.js automatically detects YouTube and Vimeo embed URLs and autoplays them when the slide becomes visible.

If you add an `<iframe>` inside your slide it's constrained by the size of the slide. To break out of this constraint and add a full page iframe, you can use an iframe slide background.

#### Iframe Post Message
reveal.js automatically pushes two post messages to embedded iframes. slide:start when the slide containing the iframe is made visible and slide:stop when it is hidden.

``` 
// JavaScript inside of an iframe embedded within reveal.js
window.addEventListener( 'message', event => {
	if( event.data === 'slide:start' ) {
		// The slide containing this iframe is visible
	}
	else if( event.data === 'slide:stop' ) {
		// The slide containing this iframe is not visible
	}
} );
```

## Fragments

Fragments are used to highlight or incrementally reveal individual elements on a slide. Every element with the class&nbsp;`fragment`&nbsp;will be stepped through before moving on to the next slide.

The default fragment style is to start out invisible and fade in. This style can be changed by appending a different class to the fragment.

``` html
<p class="fragment">Fade in</p>
<p class="fragment fade-out">Fade out</p>
<p class="fragment highlight-red">Highlight red</p>
<p class="fragment fade-in-then-out">Fade in, then out</p>
<p class="fragment fade-up">Slide up while fading in</p>
```



| Name | Effect |
|------|--------|
| fade-out | Start visible, fade out |
| fade-up | Slide up while fading in |
| fade-down | Slide down while fading in |
| fade-left | Slide left while fading in |
| fade-right | Slide right while fading in |
| fade-in-then-out | Fades in, then out on the next step |
| fade-in-then-semi-out | Fades in, then to 50% on the next step |
| grow | Scale up |
| shrink | Scale down |
| strike | Strike through |
| highlight-red | Turn text red |
| highlight-green | Turn text green |
| highlight-blue | Turn text blue |
| highlight-current-red | Turn text red, then back to original on next step |
| highlight-current-green | Turn text green, then back to original on next step |
| highlight-current-blue | Turn text blue, then back to original on next step |

### [](https://revealjs.com/fragments/#nested-fragments)Nested Fragments

Multiple fragments can be applied to the same element sequentially by wrapping it, this will fade in the text on the first step, turn it red on the second and fade out on the third.

``` html
<span class="fragment fade-in">
  <span class="fragment highlight-red"> 
    <span class="fragment fade-out">   
        Fade in > Turn red > Fade out  
    </span>
  </span>
</span>
```


### [](https://revealjs.com/fragments/#fragment-order)Fragment Order

By default fragments will be stepped through in the order that they appear in the DOM. This display order can be changed using the&nbsp;`data-fragment-index`&nbsp;attribute. Note that multiple elements can appear at the same index.

``` language-html
<p class="fragment" data-fragment-index="3">Appears last</p>
<p class="fragment" data-fragment-index="1">Appears first</p>
<p class="fragment" data-fragment-index="2">Appears second</p>
```


### [](https://revealjs.com/fragments/#events)Events

When a fragment is either shown or hidden reveal.js will dispatch an event.

``` language-javascript
Reveal.on( 'fragmentshown', event => {
    // event.fragment = the fragment DOM element
} );
Reveal.on( 'fragmenthidden', event => {
    // event.fragment = the fragment DOM element
} );
```

## Internal links

You can create links from one slide to another. Start by giving your target slide a unique&nbsp;`id`attribute. Next, you can create an anchor with an href in the format&nbsp;`#/<id>`. Here's a complete working example:

``` language-html
<!-- slide -->
[Go to the last slide](#/grand-finale)

<!-- slide -->
## SLIDE 2

<!-- slide  id ="grand-finale" -->
[Back to the first](#/0)

## THE END
```
MPE 预览状态下似乎无法跳转,页面里页号跳转isOK，但`id`需要进一步测试


### [](https://revealjs.com/links/#numbered-links)Numbered Links

It's also possible to link to slides based on their slide index. The href format for an numbered link is&nbsp;`#/0`&nbsp;where 0 is the horizontal slide number. To link to a&nbsp;[vertical slide](https://revealjs.com/vertical-slides/)&nbsp;use&nbsp;`#/0/0`&nbsp;where the second number is the index of the vertical slide target.



### [](https://revealjs.com/links/#navigation-links)Navigation Links

You can add relative navigation links that work similarly to the built in directional control arrows. This is done by adding one of the following classes to any clickable HTML element inside of the&nbsp;`.reveal`&nbsp;container.

``` language-html
<button class="navigate-left">Left</button>
<button class="navigate-right">Right</button>
<button class="navigate-up">Up</button>
<button class="navigate-down">Down</button>

<!-- Previous vertical OR horizontal slide -->
<button class="navigate-prev">Prev</button>

 <!-- Next vertical OR horizontal slide -->
<button class="navigate-next">Next</button>
```

Each navigation element is automatically given an&nbsp;`enabled`&nbsp;class when it's a valid navigation route based on the current slide. For example, if you're on the first slide only&nbsp;`navigate-right`will have the&nbsp;`enabled`&nbsp;class since it's not possible to navigate towards the left.

## Themes
The framework comes with a few different themes included.

Name |	Effect
-- | --
black	| Black background, white text, blue links (default)
white	| White background, black text, blue links
league	| Gray background, white text, blue links
beige	| Beige background, dark text, brown links
sky	| Blue background, thin dark text, blue links
night	| Black background, thick white text, orange links
serif	| Cappuccino background, gray text, brown links
simple	| White background, black text, blue links
solarized	| Cream-colored background, dark green text, blue links
blood	| Dark background, thick white text, red links
moon	| Dark blue background, thick grey text, blue links



## Transitions

When navigating a presentation, we transition between slides by animating them from right to left by default. This transition can be changed by setting the&nbsp;`transition`&nbsp;config option to a valid&nbsp;[transition style](https://revealjs.com/transitions/#styles). Transitions can also be overridden for a specific slide using the&nbsp;`data-transition`&nbsp;attribute.

``` 

<!-- slide  data-transition="zoom" -->
## This slide will override the presentation transition and zoom!
<!-- slide  data-transition-speed="slow"  -->
## from three transition speeds: default, fast or slow!

```

### [](https://revealjs.com/transitions/#styles)Styles

This is a complete list of all available transition styles. They work for both slides and slide backgrounds.

| Name | Effect |
|------|--------|
| none | Switch backgrounds instantly |
| fade | Cross fade —&nbsp;_default for background transitions_ |
| slide | Slide between backgrounds —&nbsp;_default for slide transitions_ |
| convex | Slide at a convex angle |
| concave | Slide at a concave angle |
| zoom | Scale the incoming slide up so it grows in from the center of the screen |

### [](https://revealjs.com/transitions/#separate-in-out-transitions)Separate In-Out Transitions

You can also use different in and out transitions for the same slide by appending&nbsp;`-in`&nbsp;or&nbsp;`-out`to the transition name.

``` language-html
<!-- slide  data-transition="slide" -->
The train goes on …
<!-- slide data-transition="slide"  -->
and on …
<!-- slide  data-transition="slide-in fade-out" -->
and stops.
<!-- slide  data-transition="fade-in slide-out" -->
 (Passengers entering and leaving)
<!-- slide  data-transition="slide" -->
And it starts again.
```


### [](https://revealjs.com/transitions/#background-transitions)Background Transitions

We transition between slide backgrounds using a cross fade by default. This can be changed on a global level or overridden for specific slides. To change background transitions for all slides, use the&nbsp;`backgroundTransition`&nbsp;config option.

``` language-js
Reveal.initialize({  backgroundTransition: 'slide'});
```

Alternatively you can use the&nbsp;`data-background-transition`&nbsp;attribute on any&nbsp;`<section>`&nbsp;to override that specific transition.

## Vertical Slides


By default, all slides are aligned horizontally, but you can also create vertical slides by adding `vertical=true`.
For example:

```html
<!-- slide vertical=true -->
```

## Speaker View

reveal.js comes with a speaker notes plugin which can be used to present per-slide notes in a separate browser window. The notes window also gives you a preview of the next upcoming slide so it may be helpful even if you haven't written any notes. Press the »S« key on your keyboard to open the notes window.

A speaker timer starts as soon as the speaker view is opened. You can reset the timer by clicking on it.

To enable speaker notes, set front-matter as:

```yaml
---
presentation:
  enableSpeakerNotes: true
---

```

To add notes, simply set `data-notes` property:

```html
<!-- slide data-notes="Write your note here" -->
```

check [Reveal.js Speaker Notes](https://github.com/hakimel/reveal.js#speaker-notes) section for more information.

### Share and Print Speaker Notes
Notes are only visible to the speaker inside of the speaker view. If you wish to share your notes with others you can initialize reveal.js with the `showNotes` configuration value set to `true`. Notes will appear along the bottom of the presentations.

When `showNotes` is enabled notes are also included when you export to PDF. By default, notes are printed in a box on top of the slide. If you'd rather print them on a separate page, after the slide, set `showNotes: "separate-page"`.

### Speaker Notes Clock and Timers

The speaker notes window will also show:

* Time elapsed since the beginning of the presentation. If you hover the mouse above this section, a timer reset button will appear.
* Current wall-clock time
* (Optionally) a pacing timer which indicates whether the current pace of the presentation is on track for the right timing (shown in green), and if not, whether the presenter should speed up (shown in red) or has the luxury of slowing down (blue).

The pacing timer can be enabled by configuring the `defaultTiming` parameter in the Reveal configuration block, which specifies the number of seconds per slide. 120 can be a reasonable rule of thumb. Alternatively, you can enable the timer by setting `totalTime`, which sets the total length of your presentation (also in seconds). If both values are specified, `totalTime` wins and `defaultTiming` is ignored. Regardless of the baseline timing method, timings can also be given per slide `<section>` by setting the `data-timing` attribute (again, in seconds).