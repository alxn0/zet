# Scanning to OCR PDF in linux from the command line

This solution relies on tesseract open-source text recognition engine
(OCR)[^1]. 

First we need to install `tesseract` with language files for French and
English

```
sudo apt install tesseract-ocr tesseract-ocr-fra tesseract-ocr-eng
```

Then we can create a simple pipe with `scanimage`
```
scanimage --format=png --resolution=300 | tesseract -l fra --dpi 300 pdf > scan.pdf
```

> --resolution and --mode and not scanimage parameters, but ones for the
> scanner backend. May change with different backend.

[^1]: https://tesseract-ocr.github.io/
