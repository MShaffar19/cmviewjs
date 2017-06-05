## CMview.js

A javascript interactive contact map viewer. Uses [NGL](https://github.com/arose/ngl) to interact with a 3D view of the protein.

CMview is based on SVG and powered by [D3](https://d3js.org/)

See it in action:

* [Web application](https://rcsb.github.io/cmviewjs/)

Demo
-----
### a)Creating cmcontroller object.
```js
//Span for displaying clicked atom information when clicking protein structure in NGL.
var spanfordisplay = "clickedatom";
//The div for NGL.
var nglvp = "nglviewport";
//The array to store ngl url for each PDB input. Should be in the format: "rcsb://PDBID.mmtf".
var nglurlist = ["rcsb://4knd.mmtf","rcsb://2i4a.mmtf"];
//The array to store chain for each PDB input.
var chainlist = ["A","A"];
//The array to store PDB ID for each PDB input.
var pdbidlist = ["4knd","2i4a"];
//The cutoff value for contact.
var cutoff = 8;
//The div for contact map. 
var cmsvgvp = "svgviewport";
//max length for cmviewport and max length for nglviewport.
var maxLength = 700;
//alignments array when using multiple sequence alignments.
var alignArr = ["--DVVVLQDSTFEQEVLKSDTPVLVDFWAVWCGPCKAIAPVVDDLAARYKGKLKVAKMDVDQHQGVPQQYGIRSIPTLLVFKGGRVVDTVIGADKTR-LEDSVKKAIG", "SEHTLAVSDSSFDQDVLKASGLVLVDFWAEWCGPCKMIGPALGEIGKEFAGKVTVAKVNIDDNPETPNAYQVRSIPTLMLVRDGKVIDKKVGALPKSQLKAWVESAQ-"];
var cmcontroller = new CMV.cmController(spanfordisplay, nglvp, nglurllist, chainlist, pdbidlist, cutoff, cmsvgnvp, maxLength, alignArr);

//Note: The order of the input for: nglurllist, chainlist, pdbidlist, and alignArr should be the same. (In this case: 0 is for 4knd, 1 is for 2i4a)
```

Note: Enabling both zoom and selection function at the same time will cause conflict.
### b)Enable zoom function
```js
cmcontroller.zoom(1);
```

### c)Disable zoom function
```js
cmcontroller.zoom(0);
```

### d)Enable selection function
```js
cmcontroller.brush(1);
```

### e)Disable selection function
```js
cmcontroller.brush(0);
```



