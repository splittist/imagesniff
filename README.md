# Imagesniff

Simple information about popular image types.

### Functions

*function* **IMAGE-TYPE** `thing`

When `thing` is a string it is interpreted as a pathname, or thing can be a pathname, or a stream or sequence of octets.

Returns three values `tag`, `mime-type` and `extension`, where 

* `tag` is one of: `:bmp`, `:gif87a`, `:gif89a`, `:tiff-be` (big-endian), `:tiff-le` (little-endian), `:png`, `:jfif` or `:exif`; 

* `mime-type` is an appropriate mime-type (e.g. "image/gif"); and 

* `extension` is an appropriate file extension (e.g. "gif").

*function* **IMAGE-DIMENSIONS** `thing`

When `thing` is a string it is interpreted as a pathname, or `thing` can be a pathname or a stream or sequence of octets.

Returns 

* `nil` if it doesn't recognise the image format, or 

* four values: `width`, `height`, `horizontal-resolution` and `vertical-resolution`

### Note

The library `binary-io` unconditionally includes MMAP when SBCL is used, although this is not available on Windows. Changing the reader conditonals to `#+(and sbcl (not win32))` fixes the problem.
