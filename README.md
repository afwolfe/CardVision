# CardVision

## Purpose

While the Wallet app provides exports for Apple Cards at the end of each month, many of us like to handle our budgets on a more frequent basis. However, the Wallet app provides no mechanism for this. This package uses Apple's Vision framework to read Wallet screenshots and export transactions to CVS files.

## Supported Plaforms

* macOS 10.15+
* iOS 13+

## Requirements

* Xcode 11+
* No external dependancies!

## Installation

Use Swift Package Manager.

## Example

```
import CardVision

let filePath = "path_to_directory_of_images"

let csvData = FileManager()
    .images(inPath: filePath)
    .allTransactions()
    .filtered(isDeclined: false)
    .csvData
```

## Limitations

* Screenhots must be cropped such that only transaction information, without icon, is shown as in the following example:

![Example Screenshot Cropping](RepositoryImages/ExampleCroppinog.jpg)

* The library does not attempt to deduplicate transactions that show up in multiple screenshots.

## Contributions

Contributions are welcome. Some areas that need some help:

* Real error handling
* API documentation
* Tests and test data
* Address limitations

## Liscense

[MIT](Liscense)
