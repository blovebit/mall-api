# 任务大厅获取订单列表 getTaskList

- 任务大厅展示
- 09-18 返回数据 max-need 改为 max_need
- 09-16 返回数据增加用户(业主)名,user_name, 如果未电话号码,需要隐藏中间四位(*号代替)
- 08-23 增加返回字段info，客户的备注信息
- 08-22 增加返回字段step_title，以及设计师的进度字段

## 参数

    {
        'page': Int, // 分页参数
        'size': Int, // 每页数据量
        'order_status': Int, // 按订单状态筛选；默认为空，不筛选；1为招标中；2为已结标；
        'sort_by_time': Int, // 按审核时间排序；默认为空，不排序；1为倒序；2为正序；
        'sort_by_level': Int, // 按订单等级排序；默认为空，不排序；1为倒序；2为正序；
        'level': array, // 按等级筛选可抢单；默认为空，不筛选；[1，2，3，4，5，6]
    }

## 返回数据

    {
        'tasklist': [ //array订单列表
            {
                'id': 1, // 订单id
                'user_name': "", // 业主姓名, 如果未电话号码,需要隐藏中间四位(*号代替).
                'sn': '', // 订单编号11为数字的字符串
                'level': 1, // 订单等级，1，2，3，4，5，6
                'free': true, // 免费订单，false为付费订单
                'budget': 1, // 设计预算
                'unit': '', // 户型 "n室n厅n厨n卫n阳台"
                'area': 1, // 面积
                'style': '', // 风格
                'house_status': '', // '旧房翻新'||'新房'
                'house_type': '', // '跃层'||'平层'||'别墅'
                'village': '', // 小区名
                "info": "", // 备注
                'province': '', // 省份
                'city': '', // 市
                'region': '', // 区
                'release_time': int,// 审核通过时间
                'create_tiem': int,// 创建时间
                'remain_time': int,// 订单剩余时间戳
                "step_id": 1, // 当前步骤id，订单表
                "step_title": "", // 当前步骤标题
                "step_discript": "", // 当前步骤描述
                'layout_pic': { // 户型图路径
                    'ori': '', // 原
                    'big': '', // 大
                    'mid': '', // 中
                    'sml': '', // 小
                },
                "max_need": int, // 最大抢单人数
                'designer': [ // 订单当前设计师们
                    {
                        "name": "", // 名字
                        "id": int, // 设计师id
                        'avatar': '', // 头像路径 120px左右那个图
                        'level': 1, // 设计师等级，1，2，3，4，5，6
                        "step_id": 1, // 当前步骤id，设计师与订单的关联表
                        "step_title": "", // 当前步骤标题
                        "step_discript": "", // 当前步骤描述
                    }
                ]
            }
        ]
        "item_total": int, // 数据总条数
        "message": "列表获取成功",
        "status": 200
    }

step相关的字段是**订单主表**的数据，designer下的step相关字段是**设计师与订单的关联表**的数据