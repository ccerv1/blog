{
  "title": "Topographic Colormaps",
  "date": "09/13/2021"
}
---
#### Working with custom color palettes and digital elevation models to render beautiful topographic prints in Python 
*This post is also available on [Medium](https://medium.com/@carlcervone/topographic-colormaps-a565602dd1c6).*

---

![Nine prints from the Topoloco Project](https://miro.medium.com/max/1400/1*592-TYzvnUcjzxRvm25JXQ.png)

I’ve always enjoyed playing with maps.

As a kid, I would pore over the ski mountain maps of [James Niehues](https://jamesniehues.com/), memorizing the trail names and verticals. His maps inspired me to hand-draw my own (fictional) ski resort maps.

For my senior project in high school, I programmed a ski resort simulation. It was basically [Rollercoaster Tycoon](https://www.rollercoastertycoon.com/) for ski resorts. It allowed the user (me) to cut trails, install lifts, and view summary statistics for a randomly generated mountain.

This project brought me back to those early days of map making. However, instead of trying to create a realistic rendition of a fictional landscape, this project renders an actual topography with a unique color palette.

The project uses the Python [elevation library](https://pypi.org/project/elevation/) to pull images from the [NASA Shuttle Radar Topography Mission Global 1 arc second number (SRTM 30m)](https://lpdaac.usgs.gov/products/srtmgl1nv003/) data catalog. Then, a script ingests the image, arranges the elevation data, and renders them with a [contour plot](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.contour.html).

![An unfilled contour map of Yosemite National Park](https://miro.medium.com/max/1400/1*DmN4zhB8aBn2RqaOeWGvPQ.png)

Next, the script maps the elevation values to a color palette. Each image has its own custom linear segmented colormap ([LSC](https://matplotlib.org/stable/tutorials/colors/colormap-manipulation.html)), comprised of two complementary colors from [Tobias van Schneider](https://medium.com/u/7ee29b787e9?source=post_page-----a565602dd1c6--------------------------------)’s wonderful [colors catalog](https://access.mymind.com/colors). I’m still experimenting with randomly choosing the color bases as well as algorithms for selecting complementary colors.

The footer at the bottom of each image shows the colormap and the distribution of elevations contained in the image (in meters).

![The colormap and elevation distribution](https://miro.medium.com/max/1400/1*vxNuh16vWKk5ua9niQSENA.png)

I’ve also created a version that turns a sequence of plots into an animated gif.

![Gif version of the Yosemite topographic map](https://miro.medium.com/max/1400/1*qpEyUhF3cl2_I3rRpOyjFg.gif)

I especially enjoy the gif renderings of craters and volcanos. Here’s a reversed gif of the Nyiragongo volcano in the Democratic Republic of Congo, which [erupted](https://www.youtube.com/watch?v=oFkPERI6rgA) earlier this year and is on my bucket list of volcanos to climb.

![Nyiragongo — an active volcano in the DR Congo](https://miro.medium.com/max/1400/1*JwwVqHgOKGcvtBxRjVes6Q.gif)

Mauna Kea, the highest point in Hawaii, is less symmetric and more gently sloped — and less foreboding in real life too.

![Mauna Kea — a 4000+ meter shield volcano](https://miro.medium.com/max/1400/1*Dgt21KpjUvxtHWMBvUwM4Q.gif)

Here’s the Great Rift Valley, around the same region in Ethiopia as [this beautiful map](https://www.esri.com/arcgis-blog/products/arcgis-pro/mapping/how-to-make-this-map-of-the-rift-valley/) made by [John Nelson](https://twitter.com/john_m_nelson),

![A portion of the Great Rift Valley in Ethiopia](https://miro.medium.com/max/1400/1*0i9U4MzxF0H-0Y2nVVYu2g.gif)

I lived in Ethiopia for five years. My favorite topography there, at least from the ground perspective, is the Semien Mountains, in the northwest of the country. ([These photos](https://www.gettyimages.com/photos/simien-mountains-national-park) are incredible.) It was hard to get a good contrast in the image because the elevation distribution is bimodal; it might be a good candidate for a more complex colormap assignment.

![The Semien Mountains in Ethiopia](https://miro.medium.com/max/1400/1*1S9yxF4wZotJkBUH2VarTw.gif)

I’ve created an Instagram account [@topoloco\_art](https://www.instagram.com/topoloco_art/) for these images. Follow along if you like them and DM me if you have any places or palettes you want to try out!
