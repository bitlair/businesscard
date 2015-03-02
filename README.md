# businesscard
Design for the bitlair business card.
The card was designed in Inkscape, using the open fonts [Bitter](http://www.fontsquirrel.com/fonts/bitter) and [Aller](http://www.fontsquirrel.com/fonts/aller) The bitlair logo can be found [here](https://gist.github.com/801945/b760943bda39c90a82f2ce2a3ba09a345c7ae828).

## Design specifications
We ordered our cards from http://www.drukland.nl/. Their design specifications are listed [here](http://www.drukland.nl/aanleverspecificaties.html). 
- The dimensions are 85x55mm, excluding a 3mm border that will be removed in the printing process.
- The document has to be exported as a 300 DPI PDF with CMYK colours.
- Text can't be placed 5mm from the edge of the business card (or 8mm including the border).

## Steps to export from inkscape
1. Go to *file->Save As...* and save the card as a PDF.
2. In the dialog box, choose *PDF 1.5* and check *Convert text to paths*. Set the DPI to 300.
3. Convert the saved PDF to CMYK using the following command from the *ghostscript* package:
'''sh
gs -dSAFER -dBATCH -dNOPAUSE -dNOCACHE -sDEVICE=pdfwrite \
    -sColorConversionStrategy=CMYK -dProcessColorModel=/DeviceCMYK \
    -sOutputFile=single_cmyk.pdf single.pdf
'''