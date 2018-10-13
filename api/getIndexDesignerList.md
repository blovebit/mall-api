# （平台首页）推荐设计师列表: getIndexDesignerList

- 09-26 新增返回 level_name

## 参数

    {
        'is_recommend': // 默认为空，获取全部；1为获取推荐的。
        'is_index': // 默认为空，获取全部。1为获取index首页的。
        'is_hot': // 默认为空，获取全部。1为获取热门的。
        'page': // 页码
        'size': // 页长
    }

## 返回数据

    {
        "designer_list|8": [
            {
                "id": int, // 设计师id
                "name": "", // 设计师名字
                "level": int, // 设计师等级
                "level_name": "首席设计师", // 等级称谓：首席设计师等，设计师等级表获取
                "work_years": int, // 从业年限
                "concept": "", // 设计师理念
                "avatar": { // 头像路径
                    "ori":"", //原图
                     "big": "", // 大图PC
                     "mid": "", // 中途wap
                     "sml": "", // 小图
                 }, 
                "case_num": int,// 案例数
                "like_num": int,// 喜欢数
            },
            // ...
        ],
        "item_total": int, // 数据总条数
        "message": "数据获取成功!",
        "status": 200
    }
