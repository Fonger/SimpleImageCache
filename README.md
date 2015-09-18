SimpleImageCache
================

Simple image downloading and caching class for Swift apps. Compatible with iOS7+.
Tested with Xcode 6.x (Swift 1.2) Xcode 7.0 (Swift 2.0)

Full explanation is in: http://dinethmendis.com/blog/swift-image-cache-compatible-with-ios7

Usage:

```
SimpleCache.sharedInstance.getImage(request) { image, error in
	if let err = error {
		// thou shall handle errors
	} else if let fullImage = image {
		imageView.image = fullImage
	}
}
```

If you are downloading in a cell, the ```prepareForReuse()``` function should do:

```
override func prepareForReuse() {
	...
	SimpleCache.sharedInstance.cancelImage(requestUrl)
}
```
	
Loading cached data only:

```
SimpleCache.sharedInstance.getImageFromCache(itemUrl) { image, error in
	...
}
```
