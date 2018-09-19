# 获取案例详情: getCaseDetail

- 09-19 修改 room_list 结构，添加 part
- 案列详情页展示

## 参数

    {
        "id": int, // 案例id
    }

## 返回

    {
        "case_detail":{
            "id": int, // 案例id
            "name": "", // 案例name,也许是小区名
            "style": "", // 风格
            "unit": "", // 户型
            "house_type": "", // "跃层"||"平层"||"别墅"
            "area": int, // 面积
            "cost": int, // 案例造价
            "funs_num": int, // 赞数
            "cover": { // 封面图
                "ori":"", //原图
                 "big": "", // 大图PC
                 "mid": "", // 中途wap
                 "sml": "", // 小图
            },
            "designer": { // 设计师
                "id": int,
                "name": "",
                "avatar": {// 头像路径 120px左右那个图
                    "ori":"", //原图
                     "big": "", // 大图PC
                     "mid": "", // 中途wap
                     "sml": "", // 小图
                }, 
            },
            "3d": { // 3d全景
                "href": "", // 案例3d全景页链接
                "cover": { // 3d封面图
                    "ori":"", //原图
                     "big": "", // 大图PC
                     "mid": "", // 中途wap
                     "sml": "", // 小图
                }
            },

09-19 修改 room_list 结构，添加 part

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
        },
        "message": "列表获取成功!",
        "status": 200
    }