## 抖音在线签名服务

>最新算法基于抖音19年初的android 2.9.0~3.9.0版本，请使用豌豆荚下载指定版本

> 任何疑问请发邮件到：[vsdouyin@yandex.com](vsdouyin@yandex.com)

### 第一步
创建一个私有的授权token，用于以后的所有操作

+ 点击 [https://sign.vsdouyin.com/api/token/gen/](http://sign.vsdouyin.com/api/token/gen/) 直接创建
+ 粘贴 token到文件`config.py` 的`API_TOKEN`配置项
+ 查看token的剩余可用次数（以下实例使用b7f5a12b0dfa11f6c1046a2abe65eb94作为token，使用时请替换为你自己的）
    + 使用命令`python3 1_info_token.py`
    +  其它语言调用请参考：
```bash
curl "https://sign.vsdouyin.com/api/token/info/b7f5a12b0dfa11f6c1046a2abe65eb94"
```

### 第二步
+ 使用命令`python3 2_gen_device.py` 生成设备值
+ 其它语言调用请参考python源码

### 第三步
+ 使用命令`python3 3_test_as_cp_mas.py`测试as\cp\mas签名
+ 其它语言调用请参考：
```bash
curl -X "POST" "https://sign.vsdouyin.com/api/653d33c/sign/b7f5a12b0dfa11f6c1046a2abe65eb94" \
     -H 'Content-Type: application/json' \
     -d $'{"url": "https://aweme.snssdk.com/aweme/v1/feed/?type=0&max_cursor=0&min_cursor=-1&count=6&volume=0.3333333333333333&pull_type=2&need_relieve_aweme=0&filter_warn=0&is_cold_start=0&js_sdk_version=1.2.2&app_type=normal&manifest_version_code=321&_rticket=1541682949911&ac=wifi&device_id=59121099964&iid=50416179430&os_version=8.1.0&channel=gray_3306&version_code=330&device_type=ONEPLUS%20A5000&language=zh&vid=C2DD3A72-18E8-490e-B58A-86AD20BB8035&resolution=1080*1920&openudid=27b34f50ff0ba8e26c5747b59bd6d160fbdff384&update_version_code=3216&app_name=aweme&version_name=3.3.0&os_api=27&device_brand=OnePlus&ssmix=a&device_platform=android&dpi=420&aid=1128"}'
```
+ http请求返回的header里面的times为token剩余的次数

## 第四步
+ 使用其他python文件测试具体功能

