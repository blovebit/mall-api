# （平台/公司/设计师）获取案例列表: getCaseList

- 09-19 返回数据 增加room_list，audit
- 08-17 增加字段："house_type"(跃层"||"平层"||"别墅)、"name"工地名

## 参数

    {
        "company_id": // 公司id，为空查询全部
        "keyword": // 用户查询的关键字，默认为空。
        "designer_id": // 设计师id，为空查询全部
        "isrecommend": // 默认为空，获取全部；1为获取推荐的。
        "isindex": // 默认为空，获取全部。1为获取index的。
        "style": // 风格id
        "unit": // 户型id。
        "type": // 类型id。家装、工装、软装
        "page": //当前页
        "size": //每页数量
    }

## 返回数据

    {
        "case_list": [
            {
                "id": "", // 案例id
                "name": "", // 案例name
                "village": "", // 小区名称
                "costomer_name": "", // 业主姓名
                "address": "", // 小区地址
                "longitude": "", // 经度
                "latitude": "", // 纬度
                "style": "", // 案例风格
                "unit": "", // 案例户型
                "house_type": "", // "跃层"||"平层"||"别墅"
                "area": "", // 面积
                "cost": "", // 案例造价
                "funs_num": "", // 赞数
                "cover": { // 封面图
                    "ori":"", //原图
                    "big": "", // 大图PC
                    "mid": "", // 中途wap
                    "sml": "", // 小图
                },
                "designer": { // 设计师
                    "id": "", //
                    "name": "", //
                    "avatar": { // 头像路径 
                        "ori":"", // 原图
                        "big": "", // 大图PC
                        "mid": "", // 中途wap
                        "sml": "", // 小图
                    },
                },
                "image_num": int , // 图片张数,

09-19 增加room_list，audit

                "audit": 1, // 审核状态,0待审核，1通过，2不通过
                "room_list": [ // 房间列表
                    {
                        "name": "", // 房间名称 客厅，餐厅，卧室2、儿童房、玄关、书房、厨房，卫生间，阳台等
                        "explain": "@cparagraph", // 说明
                        "part": [ // 局部
                            {
                                "name": "@cname", // 局部名，电视墙，沙发、浴室柜等。
                                "photo": {  // 图片
                                    "ori": "", // 原图
                                    "big": "", // 大图
                                    "mid": "", // 中图
                                    "sml": "", // 小图
                                }
                            },
                            // ..
                        ],
                    }
                ]
            }
            // ...
        ],
        "item_total": int,//数据总条数
        "message": "列表获取成功!",
        "status": 200
    }
