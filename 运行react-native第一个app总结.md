#运行第一个react-native

1.android sdk找不到问题

    在项目AwesomeProject/android文件夹下添加local.properties(内容<b>sdk.dir = android-sdk-linux路径</b>)

2.在AwesomeProject/目录想运行react-native start启动服务

    启动http://localhost:8081/服务

3.进入debugging模式修改debug server host & port for device 访问react-native启动的服务

    app需访问http://localhost:8081/index.android.bundle?platform=android地址

