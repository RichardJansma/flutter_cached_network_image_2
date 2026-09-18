# Cached network image
<!-- [![pub package](https://img.shields.io/pub/v/cached_network_image.svg)](https://pub.dartlang.org/packages/cached_network_image)
[![codecov](https://codecov.io/gh/Baseflow/flutter_cached_network_image/branch/main/graph/badge.svg?token=I5qW0RvoXN)](https://codecov.io/gh/Baseflow/flutter_cached_network_image)
[![Build Status](https://github.com/Baseflow/flutter_cached_network_image/workflows/app_facing_package/badge.svg?branch=develop)](https://github.com/Baseflow/flutter_cached_network_image/actions/workflows/app_facing_package.yaml) -->


A flutter library to show images from the internet and keep them in the cache directory.
  
        


## How to use
The CachedNetworkImage can be used directly or through the ImageProvider.
Both the CachedNetworkImage as CachedNetworkImageProvider have minimal support for web. It currently doesn't include caching.


With a placeholder:
```dart
CachedNetworkImage(
        imageUrl: "https://placeholder.photo/350x150.jpg",
        placeholder: (context, url) => CircularProgressIndicator(),
        errorWidget: (context, url, error) => Icon(Icons.error),
     ),
 ```
 
 Or with a progress indicator:
 ```dart
CachedNetworkImage(
        imageUrl: "https://placeholder.photo/350x150.jpg",
        progressIndicatorBuilder: (context, url, downloadProgress) => 
                CircularProgressIndicator(value: downloadProgress.progress),
        errorWidget: (context, url, error) => Icon(Icons.error),
     ),
 ```




````dart
Image(image: CachedNetworkImageProvider(url))
````


When you want to have both the placeholder functionality and want to get the imageprovider to use in another widget you can provide an imageBuilder:
```dart
CachedNetworkImage(
  imageUrl: "https://placeholder.photo/200x150.jpg",
  imageBuilder: (context, imageProvider) => Container(
    decoration: BoxDecoration(
      image: DecorationImage(
          image: imageProvider,
          fit: BoxFit.cover,
          colorFilter:
              ColorFilter.mode(Colors.red, BlendMode.colorBurn)),
    ),
  ),
  placeholder: (context, url) => CircularProgressIndicator(),
  errorWidget: (context, url, error) => Icon(Icons.error),
),
```


## How it works
The cached network images stores and retrieves files using the [flutter_cache_manager](https://pub.dartlang.org/packages/flutter_cache_manager). 


## FAQ
### My app crashes when the image loading failed. (I know, this is not really a question.)
Does it really crash though? The debugger might pause, as the Dart VM doesn't recognize it as a caught exception; the console might print errors; even your crash reporting tool might report it (I know, that really sucks). However, does it really crash? Probably everything is just running fine. If you really get an app crashes you are fine to report an issue, but do that with a small example so we can reproduce that crash.
						112 container
							113 text #  Cached network image
						114 text <!-- [![pub package](https://img.shields.io/pub/v/cached_network_image.svg)](https://pub.dartlang.org/packages/cached_network_image)
						115 text [![codecov](https://codecov.io/gh/Baseflow/flutter_cached_network_image/branch/main/graph/badge.svg?token=I5qW0RvoXN)](https://codecov.io/gh/Baseflow/flutter_cached_network_image)
						116 text [![Build Status](https://github.com/Baseflow/flutter_cached_network_image/workflows/app_facing_package/badge.svg?branch=develop)](https://github.com/Baseflow/flutter_cached_network_image/actions/workflows/app_facing_package.yaml) -->
						117 text A flutter library to show images from the internet and keep them in the cache directory.
						118 container
							119 text ##  How to use
						120 text The CachedNetworkImage can be used directly or through the ImageProvider.
						121 text Both the CachedNetworkImage as CachedNetworkImageProvider have minimal support for web. It currently doesn't include caching.
						122 text With a placeholder:
						123 container
							124 text ``` dart
						125 text CachedNetworkImage(
						126 text         imageUrl: "https://placeholder.photo/350x150.jpg",
						127 text         placeholder: (context, url) => CircularProgressIndicator(),
						128 text         errorWidget: (context, url, error) => Icon(Icons.error),
						129 text      ),
						130 container
							131 text ```
						132 text  Or with a progress indicator:
						133 container
							134 text ``` dart
						135 text CachedNetworkImage(
						136 text         imageUrl: "https://placeholder.photo/350x150.jpg",
						137 text         progressIndicatorBuilder: (context, url, downloadProgress) => 
						138 text                 CircularProgressIndicator(value: downloadProgress.progress),
						139 text         errorWidget: (context, url, error) => Icon(Icons.error),
						140 text      ),
						141 container
							142 text ```
						143 container
							144 text ```` dart
						145 text Image(image: CachedNetworkImageProvider(url))
						146 text ````
						147 text When you want to have both the placeholder functionality and want to get the imageprovider to use in another widget you can provide an imageBuilder:
						148 container
							149 text ``` dart
						150 text CachedNetworkImage(
						151 text   imageUrl: "https://placeholder.photo/200x150.jpg",
						152 text   imageBuilder: (context, imageProvider) => Container(
						153 text     decoration: BoxDecoration(
						154 text       image: DecorationImage(
						155 text           image: imageProvider,
						156 text           fit: BoxFit.cover,
						157 text           colorFilter:
						158 text               ColorFilter.mode(Colors.red, BlendMode.colorBurn)),
						159 text     ),
						160 text   ),
						161 text   placeholder: (context, url) => CircularProgressIndicator(),
						162 text   errorWidget: (context, url, error) => Icon(Icons.error),
						163 text ),
						164 text ```
						165 container
							166 text ##  How it works
						167 container
							168 text The cached network images stores and retrieves files using the  [ flutter_cache_manager ] ( https://pub.dartlang.org/packages/flutter_cache_manager ) . 
						169 container
							170 text ##  FAQ
						171 container
							172 text ###  My app crashes when the image loading failed. (I know, this is not really a question.)
						173 text Does it really crash though? The debugger might pause, as the Dart VM doesn't recognize it as a caught exception; the console might print errors; even your crash reporting tool might report it (I know, that really sucks). However, does it really crash? Probably everything is just running fine. If you really get an app crashes you are fine to report an issue, but do that with a small example so we can reproduce that crash.
				174 container focus-trap-help-panel
					175 text Use 
					176 text Control + Shift + m
					177 text  to toggle the 
					178 text tab
					179 text  key moving focus. Alternatively, use 
					180 text esc
					181 text  then 
					182 text tab
					183 text  to move to the next interactive element on the page.
			184 container
				185 button Attach files by dragging & dropping, selecting or pasting them. Styling with Markdown is supported, ID: blob-dragged-file-input
				186 text Attach files by  dragging & dropping,  selecting or pasting them.
				187 link Description: Styling with Markdown is supported, Value: docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

The focused UI element is 111 text entry area (settable) Editing README.md file contents Use Control + Shift + m to toggle the tab key moving focus. Alternatively, use esc then tab to move to the next interactive element on the page., Value: # Cached network image
<!-- [![pub package](https://img.shields.io/pub/v/cached_network_image.svg)](https://pub.dartlang.org/packages/cached_network_image)
[![codecov](https://codecov.io/gh/Baseflow/flutter_cached_network_image/branch/main/graph/badge.svg?token=I5qW0RvoXN)](https://codecov.io/gh/Baseflow/flutter_cached_network_image)
[![Build Status](https://github.com/Baseflow/flutter_cached_network_image/workflows/app_facing_package/badge.svg?branch=develop)](https://github.com/Baseflow/flutter_cached_network_image/actions/workflows/app_facing_package.yaml) -->


A flutter library to show images from the internet and keep them in the cache directory.
  
        


## How to use
The CachedNetworkImage can be used directly or through the ImageProvider.
Both the CachedNetworkImage as CachedNetworkImageProvider have minimal support for web. It currently doesn't include caching.


With a placeholder:
```dart
CachedNetworkImage(
        imageUrl: "https://placeholder.photo/350x150.jpg",
        placeholder: (context, url) => CircularProgressIndicator(),
        errorWidget: (context, url, error) => Icon(Icons.error),
     ),
 ```
 
 Or with a progress indicator:
 ```dart
CachedNetworkImage(
        imageUrl: "https://placeholder.photo/350x150.jpg",
        progressIndicatorBuilder: (context, url, downloadProgress) => 
                CircularProgressIndicator(value: downloadProgress.progress),
        errorWidget: (context, url, error) => Icon(Icons.error),
     ),
 ```




````dart
Image(image: CachedNetworkImageProvider(url))
````


When you want to have both the placeholder functionality and want to get the imageprovider to use in another widget you can provide an imageBuilder:
```dart
CachedNetworkImage(
  imageUrl: "https://placeholder.photo/200x150.jpg",
  imageBuilder: (context, imageProvider) => Container(
    decoration: BoxDecoration(
      image: DecorationImage(
          image: imageProvider,
          fit: BoxFit.cover,
          colorFilter:
              ColorFilter.mode(Colors.red, BlendMode.colorBurn)),
    ),
  ),
  placeholder: (context, url) => CircularProgressIndicator(),
  errorWidget: (context, url, error) => Icon(Icons.error),
),
```


## How it works
The cached network images stores and retrieves files using the [flutter_cache_manager](https://pub.dartlang.org/packages/flutter_cache_manager). 


## FAQ
### My app crashes when the image loading failed. (I know, this is not really a question.)
Does it really crash though? The debugger might pause, as the Dart VM doesn't recognize it as a caught exception; the console might print errors; even your crash reporting tool might report it (I know, that really sucks). However, does it really crash? Probably everything is just running fine. If you really get an app crashes you are fine to report an issue, but do that with a small example so we can reproduce that crash.
