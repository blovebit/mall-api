# 获取用户信息: getUserInfo

- 10-13 如果是公司，新增返回 公司id company_id
- 09-18 如果是设计师，新增返回 订单统计数据 task_statistics
- 09-08 如果是公司，新增返回 staff_applicant 新员工入职申请数量

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
            "level_name": int, // 用户等级名称
            "avatar": "", // 头像路径 120px左右那个图
            "coin": {// 益币相关
                "total": int, // 益币数量
                "today_reduce": int, // 益币当日支出数量
                "today_add": int, // 益币当日收入数量
                "month_reduce": int, // 益币当月支出数量
                "month_add": int, // 益币当月收入数量
            },

            "integral": int, // 积分
            "new_msn": int, // 新消息数目，此时不要更新消息已读状态，获取消息详情之后再更新

if --- 如果设计师

            "fans": int, // 粉丝数
            "new_task": int, // 有新的预约，等待接单或拒单操作，的订单数目。此时不要更新订单的查看状态，操作之后才更新
            "task_statistics": { // 订单统计数据
                "on_going": int, // 进行中
                "end": int, // 已完结
                "cancel": int, // 已取消
            },

endif ----------

if ---- 如果为公司

            "company_id": int, // 公司ID
            "fans": int, // 粉丝数
            "staff_applicant": int, // 新员工入职申请数量
            "is_deposit": int, // 是否缴纳保证金
            "is_credit": int, // 是否信用认证

endif -----------

        },
        "message": "获取数据成功!",
        "status": 200
    }
