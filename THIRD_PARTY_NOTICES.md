# Third-party notices

Xưởng Art bundles the following third-party components.

## ONNX Runtime Web 1.20.1 — `vendor/ort/`

https://github.com/microsoft/onnxruntime — MIT License

```
MIT License

Copyright (c) Microsoft Corporation

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## JSZip 3.10.1 — `vendor/jszip.min.js`

https://github.com/Stuk/jszip — dual licensed under the MIT License or GPLv3; used here under the MIT License. See `vendor/JSZIP_LICENSE.markdown`.

## U²-Net models — `models/`

- U²-Net by Xuebin Qin et al., https://github.com/xuebinqin/U-2-Net — Apache License 2.0.
  Paper: Qin, X., Zhang, Z., Huang, C., Dehghan, M., Zaiane, O. R., & Jagersand, M. (2020). *U²-Net: Going deeper with nested U-structure for salient object detection.* Pattern Recognition, 106.
- ONNX exports `u2netp.onnx` and `silueta.onnx` (a size-reduced U²-Net) as distributed by rembg, https://github.com/danielgatis/rembg (MIT License).
- `models/silueta.part1.bin` and `models/silueta.part2.bin` are the unmodified `silueta.onnx` split in two; the page joins them back together before loading.
