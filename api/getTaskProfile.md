# 获取订单信息: getTaskProfile

- 订单详情页
- 09-26 返回新增 burning
- 09-07 增加返回字段 project_budget，装修预算

## 参数

    {
        "id": // 订单id
    }

## 返回数据

    {
        "profile": {
            "id": 1, // 订单id
            "sn": "", // 订单编号11为数字的字符串
            "level": 1, // 订单等级，1，2，3，4，5，6
            "free": true, // 免费订单，false为付费订单
            "burning": 1, // 信息费（需要消耗益币数）
            "budget": 1, // 设计预算
            "project_budget": 1, // 装修预算
            "unit": "", // 户型 "n室n厅n厨n卫n阳台"
            "area": 1, // 面积
            "style": "", // 风格
            "house_status": "", // "旧房翻新"||"新房"
            "house_type": "", // "跃层"||"平层"||"别墅"
            "village": "", // 小区名
            "info": "", // 备注
            "province": "", // 省份
            "city": "", // 市
            "region": "", // 区
            "release_time": int,// 审核通过时间
            "create_tiem": int,// 创建时间
            "remain_time": int,// 订单剩余时间戳
            "step_id": 1, // 当前步骤id，订单表
            "step_title": "", // 当前步骤标题
            "step_discript": "", // 当前步骤描述
            "deposit":""   //定金金额
            "is_deposit":""   //定金支付状态
             "retainage":""   //尾款金额
            "is_retainage":""   //尾款支付状态
            "is_quota":""   //设计费是否定额
            "layout_pic": { // 户型图路径
                "ori": "", // 原
                "big": "", // 大
                "mid": "", // 中
                "sml": "", // 小
            },
            "max-need": int, // 最大抢单人数
            "designer": [ // 订单当前设计师们
                {
                    "name": "", // 名字
                    "id": int, // 设计师id
                    "avatar": "", // 头像路径 120px左右那个图
                    "level": 1, // 设计师等级，1，2，3，4，5，6
                    "step_id": 1, // 当前步骤id，设计师与订单的关联表
                    "step_title": "", // 当前步骤标题
                    "step_discript": "", // 当前步骤描述
                }
            ]
        },
        "message": "详情获取成功!",
        "status": 200
    }

step相关的字段是**订单主表**的数据，designer下的step相关字段是**设计师与订单的关联表**的数据