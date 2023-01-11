# 12 Ways To Reduce Carbon Footprints as a Full Stack Developer


![Photo by [Noah Buscher](https://cdn.hashnode.com/res/hashnode/image/upload/v1630750454649/DRixoSz2v.html) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)](https://cdn-images-1.medium.com/max/6000/0*EsNtJNcgTorVxyzy)*Photo by [Noah Buscher](https://unsplash.com/@noahbuscher?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)*

We had an interesting presentation about Digital Sustainability at [Dynamo](https://dyna.mo/?utm_source=blog_ricardo_dantas&utm_campaign=sustainability&utm_medium=social&utm_term=sustainability&utm_content=sustainability) recently that made me think about what I could do to reduce my ecological footprint in my day-to-day job as a full stack developer. That inspired me to write this post.
> *The simplest way to define ecological footprint would be to call it the impact of human activities measured in terms of the area of biologically productive land and water required to produce the goods consumed and to assimilate the wastes generated. More simply, it is the amount of the environment necessary to produce the goods and services necessary to support a particular lifestyle.*
> — [WWF](https://wwf.panda.org/discover/knowledge_hub/teacher_resources/webfieldtrips/ecological_balance/eco_footprint/)

Did you know that the IT industry’s greenhouse gas emissions are [predicted to reach 14%](https://www.bbc.com/future/article/20200305-why-your-internet-habits-are-not-as-clean-as-you-think) of global emissions by 2040? And that if the internet was a country, [it would be the 7th largest polluter](https://www.sustainablewebmanifesto.com/#citation)? It’s impressive, isn’t it?

Thinking about all the approaches I have used during my career to optimize web apps, e-commerce, and portals projects, I have concluded that the lighter and faster the application loads to the user, the more efficient energy consumption the application will have. So here are some tips you could use on your next project.

## Measure

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1630750456218/ezk1MJK5G.png)

You can use tools like [WebsiteCarbon.com](https://www.websitecarbon.com/) to measure how eco-friendly your website is. In addition, you can use [Safari's Lighthouse on DevTools](https://webkit.org/blog/8970/how-web-content-can-affect-power-usage/) to measure its energy impact. Then, use the following tips to form an attack plan to solve the possible issues.

## Choose Renewable Energy Host Providers

Host providers and data centers may not look like they use a lot of power, but they have thousands of computers to process data and the room gets very warm. They need to keep the air cool, so air conditioning systems are a must for this industry and those systems consume a lot of energy.

[The Green Web Foundation](https://www.thegreenwebfoundation.org/) is doing a fantastic job by [providing a list](https://www.thegreenwebfoundation.org/directory/) of the most eco-friendly host providers in the world. Consider picking one of them for your next project.

## Stop daemons and Servers When You’re Not Using Them

When developers are coding apps they usually need several processes running on their local machines, in order to test and avoid crashing the live version of the app. However, eventually they will switch projects and forget to stop some of those background processes. As a result, they keep running forever or until someone notices a high consumption of memory or processing.

By stopping unused servers and background processes you can drastically (depending on the type of process) reduce your memory, processing, and power consumption.

## Use Dark Mode

If you’re using an OS that supports Dark Mode, or if you have apps that allow you to switch their theme to use darker colors, consider using it. Darker colors are [better for the eyes ](https://www.wired.com/story/give-yourself-to-dark-mode-side/)and can save battery and energy on both smartphones and laptops.

## Turn Your Camera Off

In these difficult times, everyone is using tools like Google Meets, MS Teams, and Zoom for online meetings. This behavior has become part of our day-to-day.

[Research](https://www.sciencedaily.com/releases/2021/01/210114134033.htm) has revealed that one hour of video calling or Netflix streaming emits 150 to 1,000 grams of carbon dioxide. By turning your camera off during video calls, you can reduce your carbon footprint by 96%.

## Optimize Fonts

By optimizing your font files you can reduce file sizes by up to 97%.

* Use modern web font formats such as WOFF and WOFF2. These formats use higher compression methods compared to TTF, OFT, and SVG file formats.

* Give the browser the best chance at getting fonts right by preloading required fonts.

* Subset your fonts to include only the characters that are required.

## Use CDN and Server That Are Near to Your Users

Using CDNs and servers that are nearer to your users will reduce traffic on telecom networks, which will considerably reduce the energy consumption used by their infra-structure.

## Use AMP (Accelerated Mobile Pages)

[AMP](https://amp.dev/) makes content load faster on mobile devices by removing unnecessary code and file weight, rendering a minimalist version of the original web page.

## Use Static Web Pages

Using server-side rendering solutions like WordPress will process the information to send back to the user each time someone tries to load a page. That causes the server to use more energy. You can use [static generator tools](https://jamstack.org/generators/) to help you to distribute content that does not need to be fetched from databases every single pageview. You can also make it even better by using caching on the client side.

## Do Not Use GIFs

GIF animations are fun but they create significantly larger file sizes, consuming a lot of traffic and energy. The good news is, you can replace them with the `&lt;video&gt;` element.

```html
<video autoplay loop muted playsinline>
  <source src="/saving-energy.webm" type="video/webm">
  <source src="/saving-energy.mp4" type="video/mp4">
</video>
```

*Note: The order of the `&lt;source&gt;` tag matters! Specify the WebM `&lt;source&gt;` first otherwise the browser will skip it and will play the mp4 version.*

Use the Lighthouse tab, available in the DevTools to check your website for GIFs that can be converted to videos. If you have any GIFs that can be converted, you should see a suggestion to “Use video formats for animated content” in the report.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1630750458091/k7-meaCJu.png)

## Optimize Images

Images are the biggest contributors to page weight. The larger the image files you use, the more data needs to be transferred and the more energy is used. You can use some techniques and tools to solve this problem.

### Use the WebP format

WebP images are smaller than JPEG and PNG, usually, it reaches a 25–35% reduction in file size. This decreases page sizes and improves performance. Using the approach below you make sure the browser will render the right image, even if it does not support WebP.

```html
<!-- 
The browser uses the first listed source that's in 
a format it supports. If the browser does not support 
any of the formats listed in the <source> tags, it 
falls back to loading the image specified by the <img> tag.
-->
<picture>
  <source type="image/webp" srcset="green-environment.webp">
  <source type="image/jpeg" srcset="green-environment.jpg">
  <img src="green-environment.jpg" alt="">
</picture>
```

### Lazy load images

You can do it natively! The most popular Chromium-powered browsers (Chrome, Edge, Opera) and Firefox support the `loading`attribute on the image element. The implementation for Safari [is in progress](https://bugs.webkit.org/show_bug.cgi?id=200764). You also can check the availability of this feature on [caniuse.com](https://caniuse.com/#feat=loading-lazy-attr). Browsers that do not support the `loading` attribute simply ignore it without side-effects.

```html
<img src="image.png" loading="lazy" alt="…" width="200" height="200"/>
```

Check more details about the lazy loading attributes on the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/Performance/Lazy_loading).

### Image optimization tools

You can use tools like [TinyPNG](https://tinypng.com/), [TinyJPG](https://tinyjpg.com/), [SvgHero](https://svghero.app/?utm_source=blog_ricardo_dantas&utm_campaign=sustainability&utm_medium=social&utm_term=sustainability&utm_content=sustainability), and [ShortPixel](https://shortpixel.com/). You can also use packages like [image-webpack-loader](https://github.com/tcoopman/image-webpack-loader) , [gulp-imagemin](https://github.com/sindresorhus/gulp-imagemin) or [grunt-contrib-imagemin](https://github.com/gruntjs/grunt-contrib-imagemin).

## Stop Using Google Search

The artist [**Joana Moll **created** **a** **project](http://www.janavirgin.com/CO2/) in which users can know how many kilograms of CO2 are emitted by Google search since you access the website.

There is a nice alternative to Google: [Ecosia](https://www.ecosia.org/) search engine! Ecosia is not only [an eco-friendly search engine](https://blog.ecosia.org/why-carbon-neutral-is-not-enough-ecosia-has-built-its-own-solar-plants/) but also [privacy-friendly](https://info.ecosia.org/privacy).

## Conclusion

Reducing the footprint of tech is not only all about reducing energy consumption, it’s a win-win game!

* The companies get to optimize their resources consumption and their costs

* The user has a better experience with faster and lighter apps

* The environment will have a significant reduction of pollution.

**Do you know some more tips to make it even more eco-friendly?** Feel free to share in the comments area!

## Get Engaged

* [ClimateAction.Tech](https://climateaction.tech)

* [Sustainable Web Manifesto](https://www.sustainablewebmanifesto.com)


## Resources

* [Open Sustainable Technology](https://opensustain.tech/)

* [How Web Content Can Affect Power Usage](https://webkit.org/blog/8970/how-web-content-can-affect-power-usage/)

* [17 ways to make your website more energy efficient](https://www.wholegraindigital.com/blog/website-energy-efficiency/)

* [Ecoping.earth](https://ecoping.earth/indexes/world/gatsby/)

* [Ecograder](https://ecograder.com)

* [web.dev](https://web.dev/)