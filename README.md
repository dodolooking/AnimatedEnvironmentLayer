# AnimatedEnvironmentLayer

An arcgis js api layer that can display data from GRIB2 files as animated particles.
Uses a canvas to render the particles.

Demo page here: [http://animatedenvironmentlayer.azurewebsites.net/index.html](http://animatedenvironmentlayer.azurewebsites.net/index.html)

GRIB files are a common format for meteorologcical data. See here for more info: [https://en.wikipedia.org/wiki/GRIB](https://en.wikipedia.org/wiki/GRIB). 

Things such as wind, currents, waves etc can be modelled, anything with a velocity and direction. There's two wind files and one wave file used as test data included in the repo.

You can use grib files that contain a direction and velocity set of data. Standard use is wind data that has u and v components, but you can use a number of different grib types as long as one is direction and one is velocity and it will convert them to u and v datasets. See the swell dataset for an example of this.

Supports scan mode 0 and 64.

Can change the particle density based on current map zoom dynamically. Using one particle mutiplier value can make the animation quite dense when you zoom in close, so use the dynamic particleMultiplier parameter to cater for this.


The layer requires the GRIB files to be converted to json for use. This tool is used to do that conversion:
[https://github.com/cambecc/grib2json](https://github.com/cambecc/grib2json)

# Credit
This is essentially just an arcgis and typescript port of this awesome project -

[https://github.com/danwild/leaflet-velocity](https://github.com/danwild/leaflet-velocity), so check that out.

That project takes inspiration from the following two projects which are well worth checking out as well!

[https://github.com/Esri/wind-js](https://github.com/Esri/wind-js)

[https://github.com/cambecc/earth](https://github.com/cambecc/earth)

@danwild also has this project which could help with downloading new data files.

[https://github.com/danwild/wind-js-server](https://github.com/danwild/wind-js-server)

# Usage

If you want to run the repo locally, just do an npm install

There's no @types package for dojo v11.x yet, but there is an npm package 'dojo-typings'. Even the dojo-typings package doesn't go as high as 1.12.x which arcgis now uses. Had to just include a reference to the dojo types in a custom index.d.ts file.

You could just copy the typescript file `./typescript/animatedEnvironmentLayer.ts` and compile it your own project.
Alternatively you could use precompiled amd module `./ael/animatedEnvironmentLayer.js` if you're not using typescript.

# Notes

Doesn't work with 3d yet...will work on it as I'd like 3d support. I'm no expert with webgl though so it could be a while, if ever. Help is welcome!




