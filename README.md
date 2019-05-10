English | [简体中文](./README.zh-CN.md)

<div align="center">

  # react-native-map-linking

  ##### `跳转第三方地图应用进行导航`，android支持(高德地图、百度地图、腾讯地图)，ios支持(高德地图、百度地图、腾讯地图、Apple地图)

</div>

[![npm version](https://img.shields.io/npm/v/@iwubida/react-native-map-linking.svg?style=flat)](https://www.npmjs.com/package/@iwubida/react-native-map-linking)

## 例子：调用API传入`起点坐标`和`终点坐标`后可跳转第三方地图应用进行导航

- 当未安装任何第三方地图应用时，提示推荐下载列表（ios自带Apple地图）

<img src="/resource/android-no-map.jpg" height="400px">

- 选择其中一个后跳转下载地址页面（👇分别是(高德地图、百度地图、腾讯地图)跳转的页面）

<p float="left">

<img src="/resource/android-install-gaode.jpg" height="400px">

<img src="/resource/android-install-baidu.jpg" height="400px">

<img src="/resource/android-install-qq.jpg" height="400px">

</p>

- 当系统有安装第三方地图应用时，只显示`已有`的应用列表
<p float="left">

<img src="/resource/android-list.jpg" height="400px">

<img src="/resource/ios-list.png" height="400px">

</p>
- 点击列表项后跳转相应的地图应用进行导航 （👇分别是(高德地图、百度地图、腾讯地图)的导航页面）

<p float="left">

<img src="/resource/android-gaode.jpg" height="400px">

<img src="/resource/android-baidu.jpg" height="400px">

<img src="/resource/android-qq.jpg" height="400px">

</p>

## 安装

yarn

```shell
yarn add @iwubida/react-native-map-linking
```

npm install

```shell
npm install @iwubida/react-native-map-linking
```

## 使用

```javascript
import MapLinking from '@iwubida/react-native-map-linking';

const startLocation = {
  lng: 106.534892,
  lat: 29.551891,
  title: '李子坝抗战遗址公园'
};

const destLocation = {
  lng: 106.27613,
  lat: 29.972084,
  title: '合川区邮政局(重庆市南园路198号)'
};

MapLinking.planRoute(startLocation, destLocation);

```

如果需要先兼容腾讯地图需要初始化传入`腾讯地图开发者key`

```javascript
import MapLinking from '@iwubida/react-native-map-linking';

componentDidMount() {
  MapLinking.init({ tmapKey: 'OZRBZ-GD3RQ-KZV5T-GEBD7-7WBX7-UBB7O' });
}

```
