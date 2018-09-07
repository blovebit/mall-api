# 获取订单设计详情 getTaskDetail

- 以 进度 和 订单 为查询条件，查询 **设计师与订单的关联表**  
  返回 订单当前进度 各设计师的设计详情

## 参数

    {
        "task_id": 1, // 订单ID
        "process_type": 1 // 1初稿，2终稿，3施工图凭证；默认为1
    }

## 返回数据

    {
        "drafts": [ // 根据查询参数里的process_type，返回每个设计师对应的稿件
            {
                "step_id": 1, // 步骤id,
                "3d_url": "", // 3d案例的链接
                "step_title": "", // 当前步骤标题
                "step_discript": "", // 当前步骤描述
                "designer": { // 设计师
                    "id": 1, // 设计师id
                    "name": "", // 设计师名
                },
                "process_id": 1, // 进度id

// if ---  如果查询参数 process_type 为终稿, 分房间返回 --

                "room_list|8": [ // 房间列表
                    {
                        "name": "", // 房间名称 客厅，餐厅，卧室2、儿童房、玄关、书房、厨房，卫生间，阳台等
                        "explain": "", // 说明
                        "photo": { // 图片
                            "ori": "", // 大图PC
                            "big": "", // 大图PC
                            "mid": "", // 中图wap
                            "sml": "", // 中图wap
                        }
                    }
                    // ...
                ],

// else --- 查询参数 process_type 为 初稿 或 施工图凭证

                "photo": { // 初稿图片
                    "ori": "", // 大图PC
                    "big": "", // 大图PC
                    "mid": "", // 中图wap
                    "sml": "", // 中图wap
                },

// end if --------------------------------------------

                "explain": "", // 设计说明
                "choose_status": 1, // 用户选择状态，0待选择，1选择，2淘汰
                "audit_status": 1, // 公司审核状态，0待审核，1通过，2不通过
                "time": 11354546489, // 上传时间
            }
        ]
        "message": "获取数据成功!",
        "status": 200
    }
