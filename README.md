English | [简体中文](./README.zh-CN.md)

# react-native-map-linking

##### Go to third-party Map App for navigation, Android mobile stand by Gaode Map and BaiDu Map and Tencent Map, IOS mobile stand by  Gaode Map and BaiDu Map and Tencent Map and Apple Map.

[![npm version](https://img.shields.io/npm/v/@iwubida/react-native-map-linking.svg?style=flat)](https://www.npmjs.com/package/@iwubida/react-native-map-linking)

## Example：Call the API to pass the `starting location info` and `end location info` to jump to the specified map app for navigation. 

- Prompt recommended download list when no third-party map app is installed (IOS comes with Apple map)

<img src="/resource/android-no-map.jpg" height="400px">

- Select one of them to jump to the download address page (👇the following are the pages of Gao De Map, Baidu Map, Tencent Map)

<p float="left">

<img src="/resource/android-install-gaode.jpg" height="400px">

<img src="/resource/android-install-baidu.jpg" height="400px">

<img src="/resource/android-install-qq.jpg" height="400px">

</p>

- When the system has a third-party map application installed, only the list of `existing app` is displayed.

<p float="left">

<img src="/resource/android-list.jpg" height="400px">

<img src="/resource/ios-list.png" height="400px">

</p>

- Click on the list item and jump to the corresponding map application to navigate (the following are the navigation pages of Gao De Map, Baidu Map, Tencent Map)

<p float="left">

<img src="/resource/android-gaode.jpg" height="400px">

<img src="/resource/android-baidu.jpg" height="400px">

<img src="/resource/android-qq.jpg" height="400px">

</p>

## Install

yarn

```shell
yarn add @iwubida/react-native-map-linking
```

npm install

```shell
npm install @iwubida/react-native-map-linking
```

## Usage

```javascript
import MapLinking from '@iwubida/react-native-map-linking';
import React, { PureComponent } from 'react';
import { TouchableOpacity, Text } from 'react-native';

class Demo extends PureComponent {
  handleChange = () => {
    // starting location info
    const startLocation = {
      lng: 106.534892,
      lat: 29.551891,
      title: '李子坝抗战遗址公园'
    };

    // end location info
    const destLocation = {
      lng: 106.27613,
      lat: 29.972084,
      title: '合川区邮政局(重庆市南园路198号)'
    };

    MapLinking.planRoute({ startLocation, destLocation });
  };

  render() {
    return (
      <TouchableOpacity onPress={this.handleChange}>
        <Text>start navigation</Text>
      </TouchableOpacity>
    );
  }
}

export default Demo;

```

If you need `to be compatible with Tencent map`, you need to initialize the incoming `Tencent map developer key`. [Application URL](https://lbs.qq.com/console/key.html)

```javascript
import MapLinking from '@iwubida/react-native-map-linking';

componentDidMount() {
  MapLinking.init({ tmapKey: 'OB4BZ-D4W3U-B7VVO-4PJWW-6TKDJ-WPB77' });
}

```

## Parameter support description

planRoute API is supports following properties

```javascript
import MapLinking from '@iwubida/react-native-map-linking';

MapLinking.planRoute({ startLocation, destLocation, mode, type });
```

| Name | Type | Default | Description |
| :-: | :-: | :-: | :- |
| startLocation | object | null | Starting location info |
| destLocation | object | null | End location info |
| mode | string | 'ride' | Navigation mode ['drive','bus','ride', 'walk'] |
| type | string | 'gcj02' | coordinate type ['gcj02', 'wgs84'] |

startLocation 与 destLocation is supports following properties

| Name | Type | Description |
| :-: | :-:  | :- |
| lng | number | longitude |
| lat | object | latitude |
| title | string | address |
