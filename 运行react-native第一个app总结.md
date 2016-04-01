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
    <pre>
    在android开发中，js代码导成资源不会自动去将js文件打包成index.android.bundle并放到项目android/app/src/main/assets/目录
    
    1.在创建android/app/src/main目录下创建assets文件夹
    
    2.通过命令
    <b>curl "http://localhost:8081/index.android.bundle?platform=android" -o "android/app/src/main/assets/index.android.bundle"</b>
    在assets文件夹下生成index.android.bundle文件
    </pre>
    
    <a href="https://segmentfault.com/a/1190000003915315">参考1</a>
    </li>
    <li>
        生成签名apk <a href="https://facebook.github.io/react-native/docs/signed-apk-android.html#content">参考</a>
    </li>
</ul>

