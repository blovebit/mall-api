# 获取益币操作详情: getCoinLog

- 获取益币所有变更日志  
  判断用户登陆状态

## 参数

    {
        "page": int, // 当前页
        "size": int, // 每页数量 默认6条
        'start_time': //开始时间 时间戳
        'end_time': //结束时间 时间戳
        'operator': //操作人名称模糊查询
    }

## 返回

    {
        "log":[
            {
                "id": int, // 日志id
                "operator_id": "", // 使用者id
                "operator_name": "", // 使用者名称
                 "handle_type": "", // 操作类型：1为充值，2为分配，3为消耗
                "handle_name": int, // 操作名称
                "coin_num": "", // 操作益币数量
                "moeny": "", // 金额(充值金额)
                "total_coin": "", // 账户当前总益币数
                "time": "", // 操作时间
                "pay_sn": "", // 充值编号
                "serial_number": string, // 流水号
                "pay_type": int, // 支付方式
            },
        ]
        "message": "列表获取成功!",
        "status": 200
    }