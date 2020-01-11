react-native脚手架 npm install -g react-native-cli

创建项目   npx react-native init 项目名

andriod -> app -> src -> main -> andriodManifest.xml 的 <application>标签家加 android:networkSecurityConfig="@xml/network_security_config"

新建文件夹 xml 到 andriod -> app -> src -> main -> res  

新建文件 network_security_config.xml 到上面 xml 文件夹里

内容  <?xml version="1.0" encoding="utf-8"?>
<network-security-config>
    <base-config cleartextTrafficPermitted="true">
        <trust-anchors>
            <certificates src="system" />
        </trust-anchors>
    </base-config>
</network-security-config>

app.js  引入 import { WebView } from 'react-native-webview';

更改 
  const App: () => React$Node = () => {
  return (
    <>
    <WebView
      source={{ uri: 'http://temp6.testqu.com/' }}
    />
  </>
  );
};

依赖  yarn add react-native-webview

项目启动   yarn react-native run-android   或  yarn android

安卓打包   yarn buildandroid

ios打包   yarn buildios
