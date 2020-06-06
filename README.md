# TrilateralX 
![TrilateralLogo](https://user-images.githubusercontent.com/20134338/83942319-5052a200-a7ea-11ea-8e44-76f49d5251fc.png)

### TrilateralX is a collection of mini libraries used with [trilateral3](https://github.com/nanjizal/trilateral3) to provide 2D GraphicsLayer vector graphics. Setups can allow manipulation of 2D shapes and extrusion within 3D.  

<sub><sub>The Valknut / Borromorean rings in the logo are ancient gemanic and nordic origins [Stora Hammars stones](https://en.wikipedia.org/wiki/Valknut#/media/File:Sacrificial_scene_on_Hammars_-_Valknut.png)</sub></sub>  
<sub><sub>Indicates the Triangle nature of the library, and the different parts used together.</sub></sub>  
<sub><sub>Pride flag + Black and White skin - dislocate the symbol from white nationalists, and indicate support of diversity and creativity.</sub></sub>  

### TrilateralX is Trilateral3 + helper libraries..  

TrilateralX is based around Trilateral3 a lite weight triangle drawing engine.
- Abstracted core is not tied to a specific GL/CPU render implementation, and the drawing and coloring can be rewired.
- Decoupled, where possible from its helper libraries, so you can implement and extend use cases. 
- Processes user friendly draw commands ( or svg paths ) to triangles, drawing them normally directly to Float32Array/s.
- Triangle access via abstracts over the Float32Array.

## Creating triangles

- [PencilNodule](https://nanjizal.github.io/trilateral3/pages/trilateral3/nodule/PenNodule.html) helps setup the [Pen](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/Pen.html) for a default interleave data approach, setting the [DrawAbstract](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/DrawAbstract.html)
- [Sketch](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/Sketch.html) with [Pen](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/Pen.html) inside accepts normal draw commands, [moveTo](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/Sketch.html#moveTo), [lineTo](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/Sketch.html#lineTo),[quadTo](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/Sketch.html#quadTo), [quadThru](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/Sketch.html#quadThru), [curveTo](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/Sketch.html#curveTo), [plotCoord](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/Sketch.html#plotCoord), ( and aiString wip).
- [SvgPath](https://github.com/nanjizal/justPath) with sketch inside allows you to draw SVG path data.
- ScaleContext, ScaleTranslateContext,TranslationContext can be used with SvgPath to transform draw commands during drawing.

## Accessing triangles and colors

Trilateral3 uses the [Pen](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/Pen.html) to control the drawing and editing process.  
- Set the [pos](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/Pen.html#poss) so you can modify triangle coordinates and color via the [pen.triangleCurrent](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/TriangleAbstract.html) and via the [pen.color3current](https://nanjizal.github.io/trilateral3/pages/trilateral3/drawing/Color3Abstract.html) to write directly on the data Array. 
- Currently positions will be returned in GPU dimensions often ( -1 -> 1 ) since the triangleCurrent always points to the current triangle you can create local setters getters to transform x,y,z into screen positions.
- When creating [Shaper](https://nanjizal.github.io/trilateral3/pages/trilateral3/shape/Shaper.html) shapes, or [Regular](https://nanjizal.github.io/trilateral3/pages/trilateral3/shape/Regular.html) shapes, or draw commands you can use the length or [IndexRange](https://nanjizal.github.io/trilateral3/pages/trilateral3/shape/IndexRange.html
) returned to help later iterate through the related triangles when modifying them.
