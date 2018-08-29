# 获取公司简要信息 getCompanyProfile

- [获取公司列表](./getCompanyList.md) 的单个版

## 参数

    {
        "id": int // 公司id
    }

## 返回数据

    {
        'company': [
            {
                'id': int, // 公司ID
                'name': "", // 公司名
                "level": int, // 公司等级，1，2，3，4，5，6
                'design_case': int, // 设计案例数
                'project_case': int, // 施工案列数
                'aftermarket_case': int, // 售后案列数
                'credit_level': int, // 信用级别
                'location': {
                    'province': "", // 省
                    'city': "", // 市
                    'region': "", // 区
                    'address': "", // 地址
                    'longitude': "", // 经度
                    'latitude': "", // 纬度
                },
                'phone': "", // 公司电话
                'fan_num': "", // 关注人数
                'praise': int, // 口碑值
                'design_score': int, // 设计总评分
                'project_score': int, // 工地总评分
                'quality_score': int, // 工程质量总评分
                'service_score': int, // 服务总评分
                'total_score': int, // 公司总评分
                "avatar": {// 头像路径 120px左右那个图
                    "ori": "", // 原图PC
                    "big": "", // 大图PC
                    "mid": "", // 中图wap  
                    "sml": "", // 小图wap     
                },
                "logo": "", // logo路径 
                'back_image': {
                    "ori": "", // 原图PC
                    "big": "", // 大图PC
                    "mid": "", // 中图wap  
                    "sml": "", // 小图wap     
                },
            },
            // ...
        ],
        "message": "数据获取成功!",
        "status": 200
    }