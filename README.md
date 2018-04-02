# Upload Formdata

## 功能 ：
* 多图上传
* 选中图片实时浏览
* 点击图片删除

> 这是从我项目上拆下来的，可能不能直接移植到你的项目中，你只需要看懂其中的思路即可。（菜鸡一枚，写的不好别见怪）

## 我的思路
* 1 : 给定一个input，然后通过@change事件，传入父节点和祖父节点。通过js获取到图片文件

* 2 : 将获取到的图片文件存入 filesArray中，传给后端的时候传整个filesArray即可

* 3 : 对图片的大小，格式进行判断

* 4 : 如果this.count + fileList.length <= 9 (图片数量 + 当前选中的图片数量 <= 9) ，通过window.URL.createObjectURL得到一个blob类型，然后push 进我们要在页面上显示出来的数组PicArray

* 5 : 选中一张后，将file 的 value设为空值，图片到了9 张，“ + ” 不显示

* 6 : PicArray数组有值，说明有图片，这时候 v-for出来即可

* 7 : 删除一张图片的时候，由于这张图片在PicArray数组中，所以将这张图片在数组里的下标存到vuex中。

* 8 : 在点击遮布罩实现删除时候，对PicArray 进行splice操作即可，删除了PicArray中的图片，同时也要删除filesArray中的图片，不然只是前端的删除，实际上还是把这张图片传到后端去了哦~

# 页面展示

![Image](https://github.com/PDKSophia/upload-formdata/raw/master/images/a.gif)

# 其他信息

【重要的不是copy代码，而是理解思路】

其他演示地址 ： http://www.pengdaokuan.cn/DuApp/#/circle/send


免费开源使用。

版权所有Copyright © 2018 by PDK (https://github.com/PDKSophia)

All rights reserved。
