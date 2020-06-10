# Hitomezashi Patterns

SVG Hitomezashi pattern generator... Hopfully.

Sashiko is a form of decorative embroidery from japan.  
It has two main styles this project will attempt to emulate the Hitomezashi style [Sashiko Wikipedia](https://en.wikipedia.org/wiki/Sashiko).

In hitomezashi, the pattern emerges from the alignment of single stitches made on a grid.

## Context

I was introduced to this pattern by my math unit coordinator, who was showing us some 'mindful activities to stay sane' during the pandemic.
The pattern was introduced to us in the final week before the exam period and We were [referred to this](https://arbitrarilyclose.com/2020/03/29/mathartchallenge-day-14-hitomezashi-stitching-suggested-by-katherine-seaton/) for more details.
I had assigned myself approximately 15 hours(over several days) to get enough working before the end of semester so I could send this to her while it was still relevant.

## Decisions

I looked into several ways the grid and pattern could be generated in a webpage.  
Ease of getting up and running was a major influence, as at the start of the project I had very little time.

1. HTML Table  
   Controlling cell colour, line colour and line visibility with javascript.  
   This seemed too hacky and well outside of what table was designed to do.
2. HTML5 Grid  
   The problem I was having was getting the hight and width of a cell, grid and constrain it to a desired specification. I.E. a 5 x 5 box that had 20px square cells, that wouldn't resize and re-flow with the viewport.
3. A HTML5 Canvas  
   This looked promising initially but In the examples I found flood fill performance was always brought up as a potential issue.
4. SVG  
   SVG provides simple paths and polygons that can be itterated over and manipulated.  
   SVG was also the first option where I was able to actually get something to render that was close to what is wanted in a short time (see [basicStarter.svg](./basicStarter.svg)).  
   Another reason that encouraged this choice was that there is a potential to transform the [individual paths into a polygon](https://stackoverflow.com/questions/15972912/converting-svg-path-to-polygon-in-javascript).  
   As well to gain experience javascript manipulate the a DOM.  
   Performance was ignored, well not investigated as time was an issue.
