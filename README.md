
# react-native-thumbnail
Get thumbnail from local media. Currently, it only supports for video.

## Getting started

`$ npm install react-native-thumbnail --save`

### Mostly automatic installation

`$ react-native link react-native-thumbnail`

### Manual installation


#### iOS

1. In XCode, in the project navigator, right click `Libraries` ➜ `Add Files to [your project's name]`
2. Go to `node_modules` ➜ `react-native-thumbnail` and add `RNThumbnail.xcodeproj`
3. In XCode, in the project navigator, select your project. Add `libRNThumbnail.a` to your project's `Build Phases` ➜ `Link Binary With Libraries`
4. Run your project (`Cmd+R`)<

#### Android

1. Open up `android/app/src/main/java/[...]/MainActivity.java`
  - Add `import com.reactlibrary.RNThumbnailPackage;` to the imports at the top of the file
  - Add `new RNThumbnailPackage()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-thumbnail'
  	project(':react-native-thumbnail').projectDir = new File(rootProject.projectDir, 	'../node_modules/react-native-thumbnail/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      compile project(':react-native-thumbnail')
  	```

## Usage 소소한 기능 확장
```javascript
import RNThumbnail from 'react-native-thumbnail';

// 기본 설정인 0초, 품질 100% 로 Thumbnail을 가져온다.
RNThumbnail.get(filepath).then((result) => {
  console.log(result.path); // thumbnail path
})

// 1초(마이크로초 단위)후의 영상 스냅샷을 80% 품질로 가져온다.
RNThumbnail.get(filepath, 1000000, 80).then((result) => {
  console.log(result.path); // thumbnail path
})
```
