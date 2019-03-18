.. index::
   single: Komplexní stylování

.. _slozity:


Komplexní stylování
--------------------

SLD nám umožňuje vytvářet i složitější stylováni. 
 - linie s outlinou
 - stylování na základě zoomu
 - stylování na základě atributu

Línie s okrajem
===============

SLD nemá možnost stylovat linii s okrajem. Vykreslíme ji tak, že přes sebe nakreslíme dvě linie. Spodní linie má šírku větší jako vrchní. 

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
       <Name>default_line</Name>
       <UserStyle>
         <Title>Default Line</Title>
         <FeatureTypeStyle>
           <Rule>
             <Name>rule1</Name>
             <Title>Cerna linie</Title>
             <Abstract>A solid black line with a 2 pixel width</Abstract>
             <LineSymbolizer>
               <Stroke>
                 <CssParameter name="stroke">#000000</CssParameter>
                 <CssParameter name="stroke-width">
                  <ogc:Literal>2</ogc:Literal>
                 </CssParameter>
               </Stroke>
             </LineSymbolizer>
           </Rule>
         </FeatureTypeStyle>
         <FeatureTypeStyle>
           <Rule>
             <Name>rule2</Name>
             <Title>Blue Line</Title>
             <Abstract>A solid blue line with a 1 pixel width</Abstract>
             <LineSymbolizer>
               <Stroke>
                 <CssParameter name="stroke">#003EBA</CssParameter>
                 <CssParameter name="stroke-width">
                  <ogc:Literal>1</ogc:Literal>
                 </CssParameter>
               </Stroke>
             </LineSymbolizer>
           </Rule>
         </FeatureTypeStyle>
       </UserStyle>
     </NamedLayer>
   </StyledLayerDescriptor>

Stejným způsobem můžeme vykreslit i linií typickou pro železnici

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
       <Name>default_line</Name>
       <UserStyle>
         <Title>Default Line</Title>
         <FeatureTypeStyle>
           <Rule>
             <Name>rule1</Name>
             <Title>Cerna linie</Title>
             <Abstract>A solid black line with a 2 pixel width</Abstract>
             <LineSymbolizer>
               <Stroke>
                 <CssParameter name="stroke">#000000</CssParameter>
                 <CssParameter name="stroke-width">
                  <ogc:Literal>2</ogc:Literal>
                 </CssParameter>
               </Stroke>
             </LineSymbolizer>
           </Rule>
         </FeatureTypeStyle>
         <FeatureTypeStyle>
           <Rule>
             <Name>rule2</Name>
             <Title>Blue Line</Title>
             <Abstract>A solid blue line with a 1 pixel width</Abstract>
             <LineSymbolizer>
               <Stroke>
                 <CssParameter name="stroke">#FFFFFF</CssParameter>
                 <CssParameter name="stroke-width">
                  <ogc:Literal>1</ogc:Literal>
                 </CssParameter>
                 <CssParameter name="stroke-dasharray">5 2</CssParameter>
               </Stroke>
             </LineSymbolizer>
           </Rule>
         </FeatureTypeStyle>
       </UserStyle>
     </NamedLayer>
   </StyledLayerDescriptor> 

V příkladě stylování pro železnici jsme použili i parametr pro přerušovanou čáru. Je to parametr `stroke-dasharray`. První číslo určuje délku dílku v barvě a druhé číslo určí délku mezery. 

Stylování na základě zoomu
==========================

V SLD dále můžeme nastavit různý styl pro různý zoom. Slouží na to parametry `MaxScaleDenominator` a `MinScaleDenominator`. Tyto dva parametri určují rozmezí v kterém se použije definice stylu. 

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
       <Name>default_line</Name>
       <UserStyle>
         <Title>Default Line</Title>
         <FeatureTypeStyle>
           <Rule>
             <Name>Large</Name>
             <MaxScaleDenominator>8000</MaxScaleDenominator>
              <PointSymbolizer>
                <Graphic>
                  <Mark>
                    <WellKnownName>circle</WellKnownName>
                    <Fill>
                      <CssParameter name="fill">#FF0000</CssParameter>
                    </Fill>
                  </Mark>
                  <Size>12</Size>
                </Graphic>
              </PointSymbolizer>
            </Rule>
            <Rule>
              <Name>Medium</Name>
              <MinScaleDenominator>8000</MinScaleDenominator>
              <MaxScaleDenominator>16000</MaxScaleDenominator>
              <PointSymbolizer>
                <Graphic>
                  <Mark>
                    <WellKnownName>circle</WellKnownName>
                    <Fill>
                      <CssParameter name="fill">#00FF00</CssParameter>
                    </Fill>
                  </Mark>
                  <Size>8</Size>
                </Graphic>
              </PointSymbolizer>
            </Rule>
            <Rule>
              <Name>Small</Name>
              <MinScaleDenominator>16000</MinScaleDenominator>
              <PointSymbolizer>
                <Graphic>
                  <Mark>
                    <WellKnownName>circle</WellKnownName>
                    <Fill>
                      <CssParameter name="fill">#0000FF</CssParameter>
                    </Fill>
                  </Mark>
                  <Size>4</Size>
                </Graphic>
              </PointSymbolizer>
            </Rule>
          </FeatureTypeStyle>
        </UserStyle>
     </NamedLayer>
   </StyledLayerDescriptor>

V zoomech 0 až 8000 se body zobrazí červenou barvou, v zoomech 8000 až 16000 se body zobrazí zelenou a v zoomech větších jako 16000 jsou body modré.

Stylování na základě atributu
=============================

Stylování na základě atributu si ukážeme na příkladě kartogramu v další kapitole. 



