# @nonsugarless/manage-webp
"@nonsugarless/manage-webp" is a wrapper of [webp-converter](https://www.npmjs.com/package/webp-converter) that allows you manage WebP Images more easily.

# Features
You can not only convert images to WebP Images manually but also convert images and delete unnecessary WebP Images automatically.

# Installation
```bash
npm install @nonsugarless/manage-webp
```
# Usage
## Convert all images
```bash
$ mwebp convert
```

## Start to watch images directory
 ```bash
$ mwebp watch
```
WebP Images will be converted automatically when images are added, changed and deleted.

## Delete converted WebP Images
```bash
$ mwebp clean
```
Delete converted WebP Images whose original one no longer exists in `originalDir`

```bash
$ mwebp clean --all
```
Delete *all* WebP Images from `destDir`

# Default configuration

|Prop                     |Default                  |Description                                                                                                             |
|-------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------|
|`destDir`                |"./htdocs/img/"          |Path to output images directory from project root                                                                       |
|`originalDir`            |"./htdocs/img/"          |Path to input images directory from project root                                                                        |
|`targetExt`              |".+(jpg\|jpeg\|png\|gif)"|Extension of convert files                                                                                               |
|`excludeFileNames`       |["apple-touch-icon.png"] |Array of filenames that you don't want to convert                                                                        |
|`excludeDirNames`        |[]                       |Array of relative path from `originalDir` that you don't want to convert                                                |
|`webpConverterOption`    |"-q 85"                  |[WebP convert options](https://developers.google.com/speed/webp/docs/cwebp#options)                                     |
|`webpConverterGifOption` |"-q 85"                  |[Gif WebP convert options](https://developers.google.com/speed/webp/docs/cwebp#options)                                 |

# Optional configuration
You can use an optional configuration `.managewebprc` file in JSON or YAML format or `managewebp.config.js` file exporting a JS object by setting it project root directory.
```bash
{
	"destDir": "./dest/img/",
	"originalDir": "./src/img/",
	"targetExt": ".+(jpg|png|gif)",
	"excludeFileNames": ["apple-touch-icon.png", "og-image.png"],
	"excludeDirNames": ["foo/bar"], // ignore all files below ./dest/img/foo/bar/
	"webpConverterOption": "-q 75 -sharp_yuv -m 5 -mt",
	"webpConverterGifOption": "-q 90 -m 5 -mt"
}
```

# License
[MIT](https://en.wikipedia.org/wiki/MIT_License)
