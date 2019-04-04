.. index::
   single: Stylování rastrů

.. _rstyle:

Stylování rastrů
---------------------
V kapitole Stylování jsme se věnovali stylování vektorů. Stylování rastrů si přebereme teď. 

Jednoduchý styl
===============

Styl `raster` je jednoduchý styl, v kterém pro rastr nastavujeme jenom transparentnost. 

.. code-block:: xml

  <?xml version="1.0" encoding="UTF-8"?>
  <StyledLayerDescriptor version="1.0.0" 
   xsi:schemaLocation="http://www.opengis.net/sld StyledLayerDescriptor.xsd" 
   xmlns="http://www.opengis.net/sld" 
   xmlns:ogc="http://www.opengis.net/ogc" 
   xmlns:xlink="http://www.w3.org/1999/xlink" 
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <!-- a Named Layer is the basic building block of an SLD document -->
    <NamedLayer>
      <Name>default_raster</Name>
      <UserStyle>
      <!-- Styles can have names, titles and abstracts -->
        <Title>Default Raster</Title>
        <Abstract>A sample style that draws a raster, good for displaying imagery</Abstract>
        <!-- FeatureTypeStyles describe how to render different features -->
        <!-- A FeatureTypeStyle for rendering rasters -->
        <FeatureTypeStyle>
          <Rule>
            <Name>rule1</Name>
            <Title>Opaque Raster</Title>
            <Abstract>A raster with 100% opacity</Abstract>
            <RasterSymbolizer>
              <Opacity>1.0</Opacity>
            </RasterSymbolizer>
          </Rule>
        </FeatureTypeStyle>
      </UserStyle>
    </NamedLayer>
  </StyledLayerDescriptor>

RasterSymbolizer
^^^^^^^^^^^^^^^^

`RasterSymbolizer` slouží k vykreslování rastrů. 

Opacity
^^^^^^^

V `Opacity` nastavuje transparentnost rastru. Hodnoty pro `Opacity` jsou od 0 do 1, kde 0 je úplně transparentní a 1 není transparentní vůbec. 

Styl pro DEM
============

.. code-block:: xml

  <?xml version="1.0" encoding="UTF-8"?>
  <StyledLayerDescriptor version="1.0.0"
   xmlns="http://www.opengis.net/sld" 
   xmlns:ogc="http://www.opengis.net/ogc"
    xmlns:xlink="http://www.w3.org/1999/xlink" 
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.opengis.net/sld http://schemas.opengis.net/sld/1.0.0/StyledLayerDescriptor.xsd">
    <NamedLayer>
      <Name>gtopo</Name>
      <UserStyle>
        <Name>dem</Name>
        <Title>Simple DEM style</Title>
        <Abstract>Classic elevation color progression</Abstract>
        <FeatureTypeStyle>
          <Rule>
            <RasterSymbolizer>
              <Opacity>1.0</Opacity>
              <ColorMap>
                <ColorMapEntry color="#AAFFAA" quantity="0" label="values" />
                <ColorMapEntry color="#00FF00" quantity="1000"/>
                <ColorMapEntry color="#FFFF00" quantity="1200" label="values" />
                <ColorMapEntry color="#FF7F00" quantity="1400" label="values" />
                <ColorMapEntry color="#BF7F3F" quantity="1600" label="values" />
                <ColorMapEntry color="#000000" quantity="2000" label="values" />
              </ColorMap>
            </RasterSymbolizer>
          </Rule>
        </FeatureTypeStyle>
      </UserStyle>
    </NamedLayer>
  </StyledLayerDescriptor>

ColorMap
^^^^^^^^

`ColorMap` slouží k nastavění stylu pro hodnoty rastru.`ColorMapEntry color` určuje jakou barvou se má rozpětí hodnot vykreslit, `quantity` určuje maximální hodnotu rozpětí a `label` určuje popisek rozpětí. Takže řádek  `<ColorMapEntry color="#FFFF00" quantity="1200" label="values" />` nám říka že hodnoty rastru 1000-1200 se vykreslí barvou #FFFF00 a s popiskem values



