# 公司获取订单列表: getCompanyMyTaskList

- 公司查看设计枪弹列表按抢单时间倒叙
- 从设计师与订单关联表查

## 参数

    {
        "level": int, // 等级筛选
        'start_time': //开始时间 时间戳
        'end_time': //结束时间 时间戳
        "page": //页码
        "size": //每页数量
        "status": // 空：全部；1：订单进行中；2：订单已完结；此状态需从设计师与订单关联表中查看
    }


## 返回数据

    {
       "tasklist": [ //array订单列表
            {
                "id": 1, // 订单id
                "sn": "", // 订单编号11为数字的字符串
                "level": 1, // 订单等级，1，2，3，4，5，6
                "free": true, // 免费订单，false为付费订单
                "budget": 1, // 设计预算
                "unit": "", // 户型 "n室n厅n厨n卫n阳台"
                "area": 1, // 面积
                "style": "", // 风格
                "village": "", // 小区名
                "create_tiem": int,// 抢单时间
                "step_id": 1, // 当前步骤id，设计师与订单关联表
                "step_title": "", // 当前步骤标题
                "designer": {
                    "name": "", // 名字
                    "id": int, // 设计师id
                }
            }
        ]
        "item_total": int, // 数据总条数
        "message": "列表获取成功",
        "status": 200
    }
