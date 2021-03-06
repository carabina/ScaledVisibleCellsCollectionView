# ScaledVisibleCellsCollectionView

[![CI Status](http://img.shields.io/travis/ikemai/ScaledVisibleCellsCollectionView.svg?style=flat)](https://travis-ci.org/ikemai/ScaledVisibleCellsCollectionView)
[![Version](https://img.shields.io/cocoapods/v/ScaledVisibleCellsCollectionView.svg?style=flat)](http://cocoapods.org/pods/ScaledVisibleCellsCollectionView)
[![License](https://img.shields.io/cocoapods/l/ScaledVisibleCellsCollectionView.svg?style=flat)](http://cocoapods.org/pods/ScaledVisibleCellsCollectionView)
[![Platform](https://img.shields.io/cocoapods/p/ScaledVisibleCellsCollectionView.svg?style=flat)](http://cocoapods.org/pods/ScaledVisibleCellsCollectionView)

ScaledVisibleCellsCollectionView is check visible cells position.
And setting cell's scale and alpha.

## Demo

### Horizontal ( center / right / left )
![Gif](https://github.com/ikemai/assets/blob/master/ScaledVisibleCellsCollectionView/horizontal_center.gif) ![Gif](https://github.com/ikemai/assets/blob/master/ScaledVisibleCellsCollectionView/horizontal_left.gif) ![Gif](https://github.com/ikemai/assets/blob/master/ScaledVisibleCellsCollectionView/horizontal_right.gif)

### Vertical ( center / top / bottom )
![Gif](https://github.com/ikemai/assets/blob/master/ScaledVisibleCellsCollectionView/vertical_center.gif) ![Gif](https://github.com/ikemai/assets/blob/master/ScaledVisibleCellsCollectionView/vertical_top.gif) ![Gif](https://github.com/ikemai/assets/blob/master/ScaledVisibleCellsCollectionView/vertical_bottom.gif)

## Usage

#### Cocoapods
To run the example project, clone the repo, and run `pod install` from the Example directory first.
Add the following to your `Podfile`:

* swift
```Ruby
pod "ScaledVisibleCellsCollectionView"
use_frameworks!
```
* swift2.0
```Ruby
pod 'ScaledVisibleCellsCollectionView', :git => "https://github.com/ikemai/ScaledVisibleCellsCollectionView.git", :branch => "swift-2.0"
use_frameworks!
```
Note: the `use_frameworks!` is required for pods made in Swift.

### Example

* Set propertis

```swift
let collectionView = ScaledVisibleCellsCollectionView(frame: view.bounds)
collectionView.setScaledDesginParam(scaledPattern: .VerticalCenter, maxScale: 1.2, minScale: 0.5, maxAlpha: 1.0, minAlpha: 0.5)
view.addSubview(collectionView)
```

* Set scale

```swift
func scrollViewDidScroll(scrollView: UIScrollView) {
collectionView.scaledVisibleCells()
}
```

### Variable


* Set Scroll direction & position is the most large cell

```swift
private var scaledPattern: SC_ScaledPattern = .VerticalCenter
```

```swift
public enum SC_ScaledPattern {
case HorizontalCenter
case HorizontalLeft
case HorizontalRight
case VerticalCenter
case VerticalBottom
case VerticalTop
}
```

* Set Scale

```Swift
private var maxScale: CGFloat = 1.0
private var minScale: CGFloat = 0.5
```

* Set Alpha

```Swift
private var maxAlpha: CGFloat = 1.0
private var minAlpha: CGFloat = 0.5
```


### Function

* Set property ( * Please always set )

```swift
func setScaledDesginParam(scaledPattern pattern: SC_ScaledPattern, maxScale: CGFloat, minScale: CGFloat, maxAlpha: CGFloat, minAlpha: CGFloat)
```

* Set scale for visible cells ( * Please call at any time )

```swift
func scaledVisibleCells()
```

## Author

ikemai

## License

ScaledVisibleCellsCollectionView is available under the MIT license. See the LICENSE file for more info.
