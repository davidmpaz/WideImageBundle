About WideImage library
================================

WideImage, a PHP image manipulation library
Copyright 2007-2011 Gasper Kozak

For documentation, please visit http://wideimage.sourceforge.net/


    This file is part of WideImage.
		
    WideImage is free software; you can redistribute it and/or modify
    it under the terms of the GNU Lesser General Public License as published by
    the Free Software Foundation; either version 2.1 of the License, or
    (at your option) any later version.
		
    WideImage is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU Lesser General Public License for more details.
		
    You should have received a copy of the GNU Lesser General Public License
    along with WideImage; if not, write to the Free Software
    Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA  02110-1301  USA

About WideImageBundle
================================

## Bundle Installation

Installation is quick and easy. Ultimately, the WideImageBundle files should be downloaded to the
`vendor/wideimage` directory.

This can be done in several ways, depending on your preference. The first
method is the standard Symfony2 method.

**Using the vendors script**

Add the following lines in your `deps` file:

```
[wideimage]
    git=git@github.com:davidmpaz/WideImageBundle.git
    target=bundles/wideimage
```

Now, run the vendors script to download the bundle:

``` bash
$ php bin/vendors install
```

**Using submodules**

If you prefer instead to use git submodules, then run the following:

``` bash
$ git submodule add git=git@github.com:davidmpaz/WideImageBundle.git vendor/wideimage
$ git submodule update --init
```

**Downloading the library**

Just download the files and put them under `vendor/wideimage` directory.


## Configure the Autoloader

Add the `WideImage_` prefix to your autoloader:

``` php
<?php
// app/autoload.php

$loader->registerPrefixes(array(
    // ...
    'WideImage_'       => __DIR__.'/../vendor/wideimage/lib',
));
```

## Using the Bundle

After configuring it, all you need to do is instantiate WideImage_WideImage objects, so you can have lines like this in your code:

``` php
// ...
$wi = new \WideImage_WideImage();
$img = $wi->load($original_image);
$img->rotate(90)->saveToFile($rotated_image);
// ...
