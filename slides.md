# Cartographers On Your Hub

JupyterDay

Benjamin Szeghy

---

## What is GeoJupyter

<div style="display: flex; gap: 1em; align-items: center; font-size: 0.65em; text-align: left;">
<div style="flex: 3;">

GeoJupyter is an open and collaborative community-driven effort to reimagine geospatial interactive computing experiences for education, research, and industry.

We aim to combine the approachability and playfulness of desktop GIS tools, the flexibility and reproducibility of coding-driven GIS methods, and the collaborative and storytelling power of Jupyter to enable more researchers, educators, and learners to confidently engage with geospatial data.

</div>
<div style="flex: 1; text-align: center;">
<img src="media/geojupyter_logo.png" alt="GeoJupyter logo" style="height: 170px; margin: 0;">
<p style="font-size: 0.5em; margin: 0;">Logo by Isabel Paredes</p>
<img src="media/qr_geojupyter.svg" alt="QR code for geojupyter.org" style="height: 150px; margin: 0.5em 0 0;">
<p style="font-size: 0.6em; margin: 0;">geojupyter.org</p>
</div>
</div>

--

## JupyterGIS

<div style="display: flex; gap: 1em; align-items: center; font-size: 0.45em; text-align: left;">
<div style="flex: 3;">

JupyterGIS is an in-browser, collaborative Geographical Information System (GIS). It is built on top of Project Jupyter but independently useable.

As flagship project of the open GeoJupyter community it aims to enable organizations, researchers, students, anyone interested to easily explore, use and work with geospatial data.

- Real-time collaboration
- QGIS interoperability
- Python API
- Many data formats
- Grammar-driven symbology
- Storymaps
- AI skills

</div>
<div style="flex: 2; text-align: center;">
<img src="media/jupytergis.png" alt="JupyterGIS application" style="margin: 0;">
<img src="media/qr_jupytergis.svg" alt="QR code for jupytergis.readthedocs.io" style="height: 150px; margin: 0.5em 0 0;">
<p style="margin: 0;">jupytergis.readthedocs.io</p>
</div>
</div>

---

## A cartographers workflow

<img src='media/illustrator_flipbook.png' style="max-height: 450px; margin: 0;">

A cartographer's most important tool is a graphic design software

--

### Recieve data from scientific team

<img src='media/Artboard 1.svg'>

--

### Do basic filtering, cropping or similar in a GIS tool

<img src='media/Artboard 2.svg'>

--

### Export to SVG or AIX file

<img src='media/Artboard 3.svg'>

--

### Style into a completed map in Illustrator

<img src='media/Artboard 4.svg'>

--

<div style="display: flex; gap: 1em; align-items: center; justify-content: center;">
<img src='media/bay_layout.png' style="max-height: 500px; max-width: 48%; margin: 0; object-fit: contain;">
<img src='media/before-you-are-here-stlt-wilmott-2024.jpg' style="max-height: 500px; max-width: 48%; margin: 0; object-fit: contain;">
</div>

*Before You Are Here*, Prof. Clancy Wilmott

---

## JupyterGIS is ready

JupyterGIS is more than good enough today to cover the needs of the average cartographer

--

With tools like StratusGeo and similar, the scientists that cartographers collaborate with are already natively working in JupyterHub environments.

TODO: add in StratusGeo (cryocloud) graphics

--

### In this presentation, I will present two things:
- An end-to-end example cartographic workflow using JupyterGIS 
- A new widget, **ipyd3geo**, that acts as a low-friction bridge for cartographers between Jupyter and graphic design software

---

## The workflow

start in StratusGeo

--

open a new JupyterGIS file. in a sidecar notebook, load an icesat2 raster from s3. display it in jupytergis

--

use pandas and rasterio to generate topo lines

--

add back to JGIS and remove the raster.

---

## Introducing ipyd3geo
A cartographers bridge between Jupyter and Vector Graphics editing software

<div style="display: flex; gap: 1em; align-items: center;">
<div style="flex: 4; text-align: center;">
<img src="media/ipyd3geo_docs.png" alt="ipyd3geo documentation front page" style="max-height: 420px; margin: 0;">
<p style="font-size: 0.45em; margin: 0;">ipyd3geo.readthedocs.io</p>
</div>
<div style="flex: 1; text-align: center;">
<img src="media/qr_ipyd3geo.svg" alt="QR code for the ipyd3geo GitHub repository" style="height: 150px; margin: 0;">
<p style="font-size: 0.45em; margin: 0;">github.com/geojupyter/prototype-ipyd3geo</p>
</div>
</div>

--

## Benefits of D3 Geo over other JS map renderers

### 2 "party tricks":
- Best in class projection support
- Renders maps directly to DOM, so exporting to SVG is super easy

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

---

Lastly, the cool part. I can load this svg into LightBurn...

<img src='media/lightburn.jpg' alt = 'map loaded up into a lightburn workstation'>

--

And laser cut our map into keychains for you all to take home with you today!

<img src='media/laser.jpg'>

---

## Conclusions

- While JupyterGIS was designed with scientific end users in mind, I posit that a large core user base will be cartographers.
- Cartographers do not need the most powerful, or industry standard, GIS software. For them, lower friction collaboration with scientific colleagues and easier integration with graphic design workflows is more important than the latest and greatest data tools.

--

- JupyterGIS, especially when paired with JupyterAI, already provides tools that are more than good enough to enable the collaboration. Better yet, it allows cartographers to co-locate with scientific partners that already live on a hub.
- ipyd3geo, while still in early stages and no garantee of further development, provides an easy bridge between JupyterGIS and graphic design software.

--

- Further, I hope to start a conversation about non-scientific uses for Jupyter at large. What niche places can they find in our community?
    - Can we find other small missing "bridges" that bring more people into the community?

---

## Questions or Feedback?

<div style="display: flex; gap: 1em; justify-content: space-around; align-items: flex-start; text-align: center;">
<div style="flex: 1;">
<img src="media/sessionize.png" alt="QR code for the Sessionize feedback page" style="height: 200px; margin: 0;">
<p style="font-size: 0.45em; margin: 0;">Session feedback</p>
</div>
<div style="flex: 1;">
<img src="media/qr_geojupyter.svg" alt="QR code for geojupyter.org" style="height: 200px; margin: 0;">
<p style="font-size: 0.45em; margin: 0;">geojupyter.org</p>
</div>
<div style="flex: 1;">
<img src="media/qr_ipyd3geo.svg" alt="QR code for the ipyd3geo GitHub repository" style="height: 200px; margin: 0;">
<p style="font-size: 0.45em; margin: 0;">github.com/geojupyter/prototype-ipyd3geo</p>
</div>
</div>

<div style="display: flex; gap: 1.5em; justify-content: center; align-items: center; margin-top: 1em;">
<img src="media/geojupyter_logo.png" alt="GeoJupyter logo" style="height: 100px; margin: 0;">
<img src="media/qmss_logo.svg" alt="Columbia QMSS logo" style="height: 50px; margin: 0;">
<img src="media/gsas_logo.jpg" alt="Columbia GSAS logo" style="height: 85px; margin: 0;">
</div>