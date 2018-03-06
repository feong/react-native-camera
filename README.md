# Diff with react-native-camera.
This is a git fork from react-native-camera with customzable barcode detection area of [iOS](https://developer.apple.com/documentation/avfoundation/avcapturemetadataoutput/1616291-rectofinterest).

这个库和社区的react-native-camera的库的区别是在iOS平台上增加了二维码可识别范围。

# How to use
```javascript
<RNCamera
    ref={ref => {
      this.camera = ref;
    }}
    style={styles.preview}
    type={RNCamera.Constants.Type.back}
    flashMode={RNCamera.Constants.FlashMode.on}
    permissionDialogTitle={"Permission to use camera"}
    permissionDialogMessage={
      "We need your permission to use your camera phone"
    }
    onBarCodeRead={data => console.log({ data })}
    barCodeDetectionArea={{ x: 0, y: 0, width: 0.5, height: 0.3 }}
/>
```

# Be careful
The detection area (x, y) is the right-top corner, and the (width) is the height of your screen and the (, height) is the width of  your screen. Please refer the apple API and the graqh following.

注意， 二维码的识别区域是右上角坐标系，垂直轴是x轴，水平轴是y轴。
![](https://i.loli.net/2018/03/06/5a9dfced73b27.jpg)

# TODO
* add Android support.
* change the detection area for natural use.