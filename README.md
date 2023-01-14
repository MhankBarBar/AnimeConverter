# AnimeConverter

This is a python library for converting images to anime style. It uses the QQ anime style model to convert the images.

## Installation

```bash
python3 -m pip install requirements.txt
```

## Usage

```python
from AnimeConverter import AnimeConverter

converter = AnimeConverter()

# convert image from url
img = converter.to_anime("https://images.unsplash.com/photo-1518806118471-f28b20a1d79d")

# convert image from file path
img = converter.to_anime("path/to/image.jpg")

# convert image from base64
img = converter.to_anime("data:image/jpeg;base64,/9j/4AAQSkZJRgA...")

# Save the converted image
img.save("path/to/converted_image.jpg")
```

## Result

[Before](https://i.postimg.cc/RhdSdKcS/Ureha-cos-nahida.jpg) | [After](https://i.postimg.cc/xjpTXyT5/Ureha-cos-nahida-converted.jpg)
## Parameters

The `to_anime` method takes three optional parameters:

* **img** (required): image url or base64 or local path
* **qqmode** (optional, default: 'global'): qqmode, must be 'global' or 'china'
* **proxy** (optional, default: None): proxy url, must be a string or None, like 'https://' or 'socks5://'

## Exceptions

* **ValueError**: if proxy is not a string or None, like 'https://' or 'socks5://'
* **FileNotFoundError**: if image path is not found
* **requests**.exceptions.RequestException: if the request failed

## Notes

* This library is a wrapper for QQ's anime image processing API.
* This library requires an internet connection in order to work.
* This library is using the **PIL** library for image processing.
* This library is built based on the feature provided by https://h5.tu.qq.com/ and may change at any time.
