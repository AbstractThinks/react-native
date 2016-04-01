#运行第一个react-native

1.android sdk找不到问题

    在项目AwesomeProject/android文件夹下添加local.properties(内容<b>sdk.dir = android-sdk-linux路径</b>)

2.在AwesomeProject/目录想运行react-native start启动服务

    启动http://localhost:8081/服务

3.进入debugging模式修改debug server host & port for device 访问react-native启动的服务

    app需访问http://localhost:8081/index.android.bundle?platform=android地址


4.在实际生产中，是将所有js打成一个bundle文件，作为android的资源，放在assets目录下面。而assets下的文件是会在安装时，随工程一并安装到移动端本地的。这样apk安装好后，RN会负责去加载。
<ul>
    <li>
    将js代码导成资源（android不会自动去将js文件打包成index.android.bundle并放到项目android/app/src/main/assets/目录（无assets，需自己手动创建）下，所以需要手动去打包文件（curl "http://localhost:8081/index.android.bundle?platform=android" -o "android/app/src/main/assets/index.android.bundle"））
        <a href="https://segmentfault.com/a/1190000003915315">参考1</a>
        <a href="http://www.liaohuqiu.net/cn/posts/react-native-android-package/">参考2</a>
        <a href="http://react-china.org/t/react-native-android-dev-server/2653">参考3</a>
        <a href="http://www.csdn.net/article/2015-09-30/2825835-react-native-2">参考4</a>
    </li>
    <li>
        生成签名apk <a href="https://facebook.github.io/react-native/docs/signed-apk-android.html#content">参考</a>
    </li>
<ul>

