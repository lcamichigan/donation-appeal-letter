# Donation Appeal Letter

[![Build status](https://ci.appveyor.com/api/projects/status/njbi2ne90pj81idb?svg=true)](https://ci.appveyor.com/project/lcamichigan/donation-appeal-letter)

This is a collection of resources for creating donation appeal letters for
[Sigma Zeta of ΛΧΑ](https://lcamichigan.com).

## Contents

* [Getting Started](#getting-started)
* [Creating InDesign Files](#creating-indesign-files)
* [About the Envelope](#about-the-envelope)

## Getting Started

To create a donation appeal letter, you need:

* [Adobe InDesign](https://www.adobe.com/products/indesign.html). Visit
  https://www.adobe.com/creativecloud/plans.html for more information.

* Envelope.idml and Letter.idml. The easiest way to get these files is to
  download them from
  https://ci.appveyor.com/project/lcamichigan/donation-appeal-letter/build/artifacts,
  but you can also [create your own](#creating-indesign-files).

* These fonts:

  | Font                                                                | Download URL                                                             |
  |---------------------------------------------------------------------|--------------------------------------------------------------------------|
  | [Damion](https://fonts.google.com/specimen/Damion)                  | https://github.com/google/fonts/raw/master/ofl/damion/Damion-Regular.ttf |
  | [Gillius](http://arkandis.tuxfamily.org/adffonts.html)              | http://arkandis.tuxfamily.org/fonts/Gillius-Collection-20110312.zip      |
  | [Linux Libertine](http://libertine-fonts.org) (OpenType version)    | http://mirrors.ctan.org/fonts/libertine.zip                              |

## Creating InDesign Files

Creating InDesign IDML files from the files in this repository requires the free
[Zip](http://www.info-zip.org/Zip.html) utility. To install Zip on Windows:

1. Click ftp://ftp.info-zip.org/pub/infozip/win32/zip300xn-x64.zip to download
   zip300xn-x64.zip.

2. Right-click zip300xn-x64.zip, choose Extract All, and then click Extract to
   extract a folder named zip300xn-x64.

3. Right-click zip300xn-x64.zip in the zip300xn-x64 folder you just extracted,
   choose Extract All, and then click Extract to extract another folder named
   zip300xn-x64.

4. Move this second zip300xn-x64 folder to C:\Program Files.

Zip is included with macOS.

To create InDesign files, first download this repository as a ZIP archive. To do
this, click
[here](https://github.com/lcamichigan/donation-appeal-letter/archive/master.zip).
Unzip the archive wherever you wish. Then, `cd` to the
[Envelope IDML](Envelope%20IDML) folder and enter in PowerShell

```powershell
& "$env:ProgramFiles\zip300xn-x64\zip" -X0 ..\Envelope.idml mimetype
& "$env:ProgramFiles\zip300xn-x64\zip" --recurse-paths --no-dir-entries -X9 ..\Envelope.idml * --exclude mimetype
Set-Location '..\Letter IDML'
& "$env:ProgramFiles\zip300xn-x64\zip" -X0 ..\Letter.idml mimetype
& "$env:ProgramFiles\zip300xn-x64\zip" --recurse-paths --no-dir-entries -X9 ..\Letter.idml * --exclude mimetype
```

or in Command Prompt

```batch
"%ProgramFiles%\zip300xn-x64\zip" -X0 ..\Envelope.idml mimetype
"%ProgramFiles%\zip300xn-x64\zip" --recurse-paths --no-dir-entries -X9 ..\Envelope.idml * --exclude mimetype
cd "..\Letter IDML"
"%ProgramFiles%\zip300xn-x64\zip" -X0 ..\Letter.idml mimetype
"%ProgramFiles%\zip300xn-x64\zip" --recurse-paths --no-dir-entries -X9 ..\Letter.idml * --exclude mimetype
```

or in Terminal

```sh
zip -X0 ../Envelope.idml mimetype
zip --recurse-paths --no-dir-entries -X9 ../Envelope.idml * --exclude *.DS_Store mimetype
cd '..\Letter IDML'
zip -X0 ../Letter.idml mimetype
zip --recurse-paths --no-dir-entries -X9 ../Letter.idml * --exclude *.DS_Store mimetype
```

## About the Envelope

The envelope includes an embedded image of a cross and crescent created using a
[cross-and-crescent package](https://github.com/lcamichigan/cross-and-crescent)
in LaTeX. To create this image,
[install](https://github.com/lcamichigan/cross-and-crescent#installing) the
cross-and-crescent package, and then enter in PowerShell or Terminal

```sh
latex -jobname logo -output-format pdf '\documentclass{standalone}\usepackage{cross-and-crescent}\begin{document}\begin{tikzpicture}[scale=45bp/8cm]\crossAndCrescentSetMacros\draw[line width=0.5bp]\crossAndCrescentPath\end{tikzpicture}\end{document}'
```
