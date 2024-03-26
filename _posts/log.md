Id":"B1FFD2B8-27B4-BF63-5ECF-CBDEA249059D","name":""}]}  at apis/blue/blue.js:87
17:44:32.884 确认连接蓝牙:,  [Object] {"SN":"932460433","Mac":"8404BD36-C32D-2B60-3CC1-D01707F75A56"}  at pages/evses/evses.vue:281
17:44:32.897 stop discovery success,  [Object] {"code":0,"message":"ok"}  at apis/blue/blue.js:234
17:44:33.908 ble connection state change**************:,  [Object] {"connected":true,"deviceId":"8404BD36-C32D-2B60-3CC1-D01707F75A56"}  at apis/blue/blue.js:250
17:44:33.921 连接蓝牙成功:,  [Object] {"code":0,"message":"ok"}  at apis/blue/blue.js:118
17:44:34.930 ble connection state change**************:,  [Object] {"connected":true,"deviceId":"8404BD36-C32D-2B60-3CC1-D01707F75A56"}  at apis/blue/blue.js:250
17:44:35.953 device getBLEDeviceCharacteristics:,  [Object] [{"properties":{"indicate":false,"notify":false,"read":true,"write":false},"uuid":"0000C300...} at apis/blue/blue.js:312
17:44:35.963 连接蓝牙之后的处理:,  [Boolean] true  at apis/api.js:309
17:44:37.981 开始发送指令:,  [Object] {"start":"68","length":"","seq":"00","cmd":"01","sn":"39333234363034333300000000000000","da...} at common/models/protocol.js:126
17:44:37.990 数据组织完成:00013933323436303433330000000000000000000f424000000000000000006398498514 at common/models/protocol.js:146
17:44:37.991 data_code:,  00013933323436303433330000000000000000000f42400000000000000000639849851441 at common/models/protocol.js:152
17:44:38.000 发送命令的str字符串:682500013933323436303433330000000000000000000f42400000000000000000639849851441 at common/models/protocol.js:178
17:44:38.006 写蓝牙命令失败:,  [Object] {"code":10007,"message":"Error Domain=CBATTErrorDomain Code=13 \"The value's length is inva...} at apis/blue/blue.js:382
17:44:38.013 蓝牙写报文完成:,  [Object] {"code":10007,"message":"Error Domain=CBATTErrorDomain Code=13 \"The value's length is inva...} at apis/blue/blue.js:385
17:44:38.013 待解码的参数是************:,  683200023933323436303433330000000000000000000f42400100000008306398498592330a1a02000000000000000200010156 at common/models/protocol.js:189
17:44:38.020 解码后的数据值是:,  [Object] {"user":0,"userId":1000000,"authSign":1,"appointTime":0,"appointElectricity":0,"minElectric...} at common/models/protocol.js:346
17:44:38.026 ^^^^^^^^^^^^蓝牙设备握手返回的数据值:,  [Object] {"user":0,"userId":1000000,"authSign":1,"appointTime":0,"appointElectricity":0,"minElectric...} at apis/api.js:238
17:44:38.033 握手回调之后的参数:,  [Object] {"user":0,"userId":1000000,"authSign":1,"appointTime":0,"appointElectricity":0,"minElectric...} at apis/api.js:278
17:44:38.034 解码回来的数据值:,  [Object] {"user":0,"userId":1000000,"authSign":1,"appointTime":0,"appointElectricity":0,"minElectric...} at apis/blue/blue.js:288
17:44:38.039 连接的设备列表:,  [Object] [{"SN":"932460433","Mac":"8404BD36-C32D-2B60-3CC1-D01707F75A56","SettingCurrent":48}]  at pages/evses/evses.vue:116
17:44:38.044 开始发送指令:,  [Object] {"start":"68","length":"25","seq":"00","cmd":"64","sn":"39333234363034333300000000000000","...} at common/models/protocol.js:126
17:44:38.049 数据组织完成:00643933323436303433330000000000000093246043300000f4240 at common/models/protocol.js:146
17:44:38.049 response interceptors---------------,  [Object] {"data":{"ret":200,"msg":"success","data":"{\"sn\":\"932460433\",\"pile_model\":\"c9\",\"eq...} at apis/http/http.js:64
17:44:38.054 请求后台绑定设备:,  [Object] {"data":{"ret":200,"msg":"success","data":"{\"sn\":\"932460433\",\"pile_model\":\"c9\",\"eq...} at apis/http/evse.js:34
17:44:38.058 绑定后台设置成功:,  [Object] {"ret":200,"msg":"success","data":"{\"sn\":\"932460433\",\"pile_model\":\"c9\",\"equipment_...} at apis/api.js:374
 
