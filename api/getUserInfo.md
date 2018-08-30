# 获取用户信息: getUserInfo

## 参数

    {
        "id": int, // 用户id
    }

## 返回数据

    {
        "info": {
            "name": "", // 用户名
            "role": {
                "id": int, // 角色id
                "remark": "",
                "name": "", // 角色名，需要查角色的积分配置表
                "roleSign": ""
            },
            "level": int, // 用户等级，1，2，3，4，5，6
            "avatar": "", // 头像路径 120px左右那个图
            "coin": {// 益币相关
                "total": int, // 益币数量
                "today_reduce": int, // 益币当日支出数量
                "today_add": int, // 益币当日收入数量
                "month_reduce": int, // 益币当月支出数量
                "month_add": int, // 益币当月收入数量
            }, 
           
            "integral": int, // 积分
            "fans": int, // 粉丝数
            "new_msn": int, // 新消息数目
            "new_task": int, // 新订单数目
            
            // 如果角色为公司添加以下字段
            
            "is_deposit": int, // 是否缴纳保证金
            "is_credit": int, // 是否信用认证
        },
        "message": "获取数据成功!",
        "status": 200
    }

## 说明

- 此时不要更新消息已读状态
- 此时不要更新订单的查看状态