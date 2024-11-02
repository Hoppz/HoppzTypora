> 修改 `mavlink` `sysID` 到 `3 bytes`





需要修改的内容

1. `mavlink` 源代码
    * 消息的定义
    * 组帧，解帧的函数
2. `ardupilot` 的源代码
3. `QGC` 中的源代码





## 1、mavlink 源码修改

大部分地面站和自动驾驶仪所采用的`通用消息集`定义于 [common.xml](https://mavlink.io/zh/messages/common.html)中 。

>  `generator/C`

`sysid`

`system_id`





> `message_definitions`

`mavlink - cpp - ardupilotmega.xml` 编译出来的需要的文件夹

* ardupilotmega

* common
* csAirLink
* cubepilot
* icarous
* minimal
* standard
* uAvionix

> common.xml

`gcs_system_id`

`target_system`

`target` 5694

`destination_system`  7703

`id_or_mac`

`usa_id` 7793



> generator/

`generator` 除了从 `.xml`  中生成代码，还有一些自动编码，解码的代码是写死的（有一些参数的名称通过占位符变化），这些也是要改的

 

> 报错 common
>
> 这几个都是需要257 字节以上的 payload 
>
> 1. mavlink_test_file_transfer_protocol
> 2. mavlink_test_v2_extension
> 3. mavlink_test_logging_data
> 4. mavlink_test_logging_data_acked
> 5. mavlink_test_play_tune_v2
> 6. mavlink_test_open_drone_id_message_pack





> 报错 ardupilotmega
>
> 1. 
