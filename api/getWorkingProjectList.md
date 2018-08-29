# （平台/公司/设计师）获取在建工地列表: getWorkingProjectList

- 08-17 增加字段："house_type"(跃层"||"平层"||"别墅)、"name"工地名

## 参数

    {
        "company_id": // 公司id，默认为空。
        "designer_id": // 设计师id，默认为空。
        "keyword": // 用户查询的关键字，默认为空。
        "process": // 默认全部 1:施工中；2：已竣工；
        "isrecommend": // 默认为空，获取全部；1为获取推荐的。
        "isindex": // 默认为空，获取全部。1为获取index的。
        "style": // 风格id。
        "unit": // 户型id。
        "page":
        "size":
    }

## 返回数据

    {
        "project_list": [
            {
                "id": id, // 工地id
                "name": "", // 工地名
                "village": "", // 小区名称
                "costomer_name": "", // 业主姓名
                "designer": {
                    "id": int, // 设计师id
                    "name": "", // 设计师名字
                    "avatar": "", // 头像路径 120px左右那个图
                },
                "foreman": {
                    "id": int, // 工长id
                    "name": "", // 工长名字
                },
                "supervisor": {  // 监理
                    "id": int, // 监理id
                    "name": "", // 监理名字
                },
                "area": int, // 面积
                "unit": "", // 户型
                "style": "", // 风格
                "house_type": "", // "跃层"||"平层"||"别墅"
                "cost": int, // 造价
                "complete_status": "", // 施工状态
                "current_step": int, // 当前施工进度（大阶段nodeid）
                "location": {
                    "province": "", // 省
                    "city": "", // 市
                    "region": "", // 区
                    "address": "", // 地址
                    "longitude": "", // 经度
                    "latitude": "", // 纬度
                },
                "fans_num": int, // 关注数
                "cover": { // 封面图
                    "big": "", // 大图PC
                    "mid": "", // 中途wap
                }
            }
            // ...
        ],
        "item_total": int, // 数据总条数
        "message": "列表获取成功!",
        "status": 200
    }
