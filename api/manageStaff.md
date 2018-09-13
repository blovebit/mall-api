# （公  司）员工操作: manageStaff

- 09-13 参数is_incumbent增加状态0，不改变状态。

## 参数

    {
        'staff_id_list': Array, // 员工们的id集合
        'is_incumbent': 1||2 // 1:入职;2.离职。0为不改变
        'coin': //公司分配给设计师的虚拟币数量
    }

## 返回数据

    {
        "message": "操作成功!",
        "status": 200
    }

## 说明

- 员工离职其账户的益币员工不予退回