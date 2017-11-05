# Heading
* [remote link without fragment, ok](https://github.com/mattias-p/linky/blob/master/example_site/path/to/other.md)
* [remote link without fragment, fixed by --follow](http://github.com/mattias-p/linky/blob/master/example_site/path/to/other.md)
* [remote link with fragment, ok](https://github.com/mattias-p/linky/blob/master/example_site/path/to/other.md#existing)
* [remote link with fragment, not fixed by --follow](http://github.com/mattias-p/linky/blob/master/example_site/path/to/other.md#non-existing)
* [relative link without fragment, ok](other.md)
* [relative link without fragment, broken](non-existing.md)
* [relative link with fragment, ok](other.md#heading)
* [relative link with fragment, broken](other.md#non-existing)
* [in-document link with fragment, ok](#heading)
* [in-document link with fragment, broken](#non-existing)