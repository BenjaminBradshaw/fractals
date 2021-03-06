# Fractal exploration in Jypter notbooks visualised with Plotly
Fractal are calculated by repeatedly iterating relatively simple functions at each point on the complex plane. 
The value of each coordinate (pixel) is by default the iteration count that function reaches before it escapes the origin region. 
This is implemented by checking if the orbit of the iterated point Z exceeds a radius of 2 on the complex plan (calculated as if abs(z) > 2 ).

## Fractals included in this project:
- Mandelbrot
  > z = z ** power + c +shift
  ![alt text](https://raw.githubusercontent.com/BenjaminBradshaw/fractals/master/20200910-124134.jpeg "Mandelbrot")
  
- Burning ship
  >  z = (abs(z.real) + abs(z.imag)* 1j) ** power + c +shift
![alt text](https://raw.githubusercontent.com/BenjaminBradshaw/fractals/master/20200910-140517.jpeg "Burning ship")

- Newton chain
  > z = z - (z ** power-c)/(3*z ** (power-1))
  ![alt text](https://raw.githubusercontent.com/BenjaminBradshaw/fractals/master/Newton%5E2.0%2B0.0(-0.4062%2C-0.0617)%2C(0.0533%2C0.2755)orbit_distance_logorbit_distance20200912-101201.jpeg "Newton chain")
## Visualisation style
Using iteration count as the pixel value is the standard way to view fractals, it leads to a thin complex region separating the stable (interior) and unstable (exterior) regions. More interesting effect can be achieved by displaying properties of the orbits themselves. This project offers a few ways to do this individually on the interior and exterior regions of the fractals.
![alt text](https://raw.githubusercontent.com/BenjaminBradshaw/fractals/master/20200910-201450.jpeg "Exterior orbit distance")

## Plotly display 
Fractals are visualised using the Plotly Heatmap chart https://plotly.com/python/heatmaps/ this gives access to zoom, smoothing and colormap options reducing the amount of visualisation code needed. The FigureWidget class is utilised to let the selected zoom region be used for the next calculation area when the display cell is rerun. Early prototype of this project had the plot automatically recalculate on zoom in but the more complex and higher resolution plots don’t recalculate quick enough for this to be a real time interaction. This project is predominately used to generate high resolution fractal images for feeding in the Style Transfer projects  (https://github.com/BenjaminBradshaw/Fast-Style-Transfer-for-Arbitrary-Styles) so large complex imagery has been prioritised over zoom speed. But recalculation typically sits under a minute (which just builds the excitement of fractal exploration 😊). A large number of colour maps are available as part of Plotly and were a widget option in early versions of this project but I've decided that Icefire is *objectively* the best so have removed the selection box, but inferior options can be found here: https://plotly.com/python/builtin-colorscales/.

## Export
The main aim of this project is to produce high (and arbitrary) resolution fractal images. Exports can be as a HTML file (https://benjaminbradshaw.github.io/fractals/burningship.html) or as an image named with all the parameters needed to reproduce it (I find that with any generative art project parameter file names are the only way to keep track of files). 

