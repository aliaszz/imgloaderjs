# ImgLoader

## Overview

ImgLoader 一个简单易用的图片加载管理器, 可以对图片进行批量加载等操作.

## 使用

```javascript
import ImgLoader from "imgloaderjs";

const imgsTarget = [];
const loader = new ImgLoader();
imgsTarget[0] = loader.addImage(logo1);
imgsTarget[1] = loader.addImage(logo2);
imgsTarget[2] = loader.addImage(logo3);

loader.addCompletionListener((res) => {
  const logoZone = [];
  for (let i = 0; i < imgsTarget.length; i++) {
    const rect = getRect(imgsTarget[i]);
    const imageData = Util.getImageData(context, imgsTarget[i], rect);
    logoZone.push(new ImageZone(imageData, rect.x, rect.y));
  }

  this.init(imgsTarget, logoZone);
});

loader.start();
```

## License

ImgLoader is released under the MIT License. http://www.opensource.org/licenses/mit-license
