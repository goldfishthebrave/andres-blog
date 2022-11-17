---
title: 'Notes for Andre because I Love Him'
smartdown: true
header: 'none'
---


### CAD files

You can add cadd files.  This is not an actual file.  It's generated with code, but I think you can export your blender files to auto cad and display them with jscad here.  I can help you figure it out.
```openjscad/playable/autoplay
// title      : Transparency
// author     : Rene K. Mueller
// license    : MIT License
// description: showing transparent objects
// file       : transparency.jscad

function main () {
  var o = [];
  for (var i = 7; i >= 0; i--) { // reverse order for seeing through all cylinders (see https://www.opengl.org/wiki/Transparency_Sorting)
    // hsl to rgb, creating rainbow [r,g,b]
    o.push(
      cylinder({r: 3, h: 20}).setColor(
        hsl2rgb(i / 8, 1, 0.5).concat(1 / 8 + i / 8) // and add to alpha to make it [r,g,b,a]
      ).translate([(i - 3) * 7.5, 0, 0])
    );
  }
  o.push(color('red', cube(5)).translate([-4, -10, 0]));
  o.push(color('red', 0.5, cube(5)).translate([4, -10, 0]));
  return o;
}
```




