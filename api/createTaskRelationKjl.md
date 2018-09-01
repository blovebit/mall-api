# 关联设计订单与酷家乐: createTaskRelationKjl

- 设计师设计订单关联酷家乐案例id，用于初稿的户型图，以及生成3D链接

## 参数

    {
        'designer_id' Int, // 设计师ID
        'order_id': varchar, // 订单id
        'kjl_case_id': String, // 酷家乐案例id
    }

## 返回数据

    {
        "message": "关联成功!",
        "status": 200
    }

## 说明
