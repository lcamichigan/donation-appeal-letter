# Donation Appeal Letter

[![Build status](https://ci.appveyor.com/api/projects/status/njbi2ne90pj81idb?svg=true)](https://ci.appveyor.com/project/lcamichigan/donation-appeal-letter)

This is a collection of resources for creating donation appeal letters for
[Sigma Zeta of ΛΧΑ](https://lcamichigan.com).

## Contents

* [Getting Started](#getting-started)
* [About the Envelope](#about-the-envelope)

## Getting Started

To create a donation appeal letter, you need:

* [Adobe InDesign](https://www.adobe.com/products/indesign.html). Visit
  https://www.adobe.com/creativecloud/plans.html for more information.

* Envelope.idml and Letter.idml. The easiest way to get these files is to
  download them from
  https://ci.appveyor.com/project/lcamichigan/donation-appeal-letter/build/artifacts,
  but you can also [create your own](https://github.com/lcamichigan/make-idml).

* These fonts:

  | Font                                                         | Download URL                                                             |
  |--------------------------------------------------------------|--------------------------------------------------------------------------|
  | [Damion](https://fonts.google.com/specimen/Damion)           | https://github.com/google/fonts/raw/master/ofl/damion/Damion-Regular.ttf |
  | [Gillius](http://arkandis.tuxfamily.org/adffonts.html)       | http://arkandis.tuxfamily.org/fonts/Gillius-Collection-20110312.zip      |
  | [Libertinus](https://github.com/libertinus-fonts/libertinus) | https://github.com/libertinus-fonts/libertinus/releases/latest           |

## About the Envelope

The envelope includes an embedded image of a cross and crescent created using a
[cross-and-crescent package](https://github.com/lcamichigan/cross-and-crescent)
in LaTeX. To create this image,
[install](https://github.com/lcamichigan/cross-and-crescent#installing) the
cross-and-crescent package, and then enter in PowerShell or Terminal

```sh
pdflatex -jobname logo '\documentclass{standalone}\usepackage{cross-and-crescent}\begin{document}\begin{tikzpicture}[scale=45bp/8cm]\crossAndCrescentSetMacros\draw[line width=0.5bp]\crossAndCrescentPath\end{tikzpicture}\end{document}'
```
