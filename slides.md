# Cartographers On Your Hub

JupyterDay

Benjamin Szeghy

---

## What is Geojupyter

---

## A cartographers workflow

A cartographer's most important tool is a graphic design software

--

### Recieve data from scientific team

--

### Do basic filtering, cropping or similar in a GIS tool

--

### Export to SVG or AIX file

--

### Style into a completed map in Illustrator

---

## JupyterGIS is ready

JupyterGIS is more than good enough today to cover the needs of the average cartographer

--

With tools like CryoCloud and similar, the scientists that cartographers collaborate with are already natively working in JupyterHub environments. 

--

### In this presentation, I will present two things:
- An end-to-end example cartographic workflow using JupyterGIS 
- A new widget, **ipyd3geo**, that acts as a low-friction bridge for cartographers between Jupyter and graphic design software

---

## The workflow

start in CryoCloud

--

open a new JupyterGIS file. in a sidecar notebook, load an icesat2 raster from s3. display it in jupytergis

--

use pandas and rasterio to generate topo lines

--

add back to JGIS and remove the raster.

--

use ipyd3geo's "from_jgis()" tool to load the layers

--

as a special extra step, conditionally style a couple specific topo line elevation levels to have specific colors. this will come in handy in a bit

--

ipyd3geo's output is dynamic. I can adjust the projection, centering, and zoom to match my taste. 

--

then, I download as svg. 

This is ipyd3geo's unique trick. Because it uses D3 as it's underlying rendering engine, everything is shown by directly manipulating the DOM, with no virtualizaiton. This means exporting vector art formats is basically free.

--

Now, I can load this into illustrator.

--

Here, those special stylings come in handy. I'll use the text on path tool to label their elevations.

--

Then, I'll add some typography and styling.

--

Lastly, the cool part. I can load this svg into Light Burn...

--

And laser cut our map into keychains for you all to take home with you today!

---

## Conclusions

- While JupyterGIS was designed with scientific end users in mind, I posit that a large core user base will be cartographers.
- Cartographers do not need the most powerful, or industry standard, GIS software. For them, lower friction collaboration with scientific colleagues and easier integration with graphic design workflows is more important than the latest and greatest data tools.

--

- JupyterGIS, especially when paired with JupyterAI, already provides tools that are more than good enough to enable the collaboration. Better yet, it allows cartographers to co-locate with scientific partners that already live on a hub.
- ipyd3geo, while still in early stages and no garantee of further development, provides an easy bridge between JupyterGIS and graphic design software.
- Further, I hope to start a conversation about non-scientific uses for Jupyter at large. What niche places can they find in our community?

---

## Questions or Feedback?

insert logos+qrcodes/links here