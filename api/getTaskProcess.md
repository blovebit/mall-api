# 获取订单进度与设计: getTaskProcess

- 以 设计师 和 订单 为查询条件，查询 **设计师与订单的关联表**  
  返回 订单的 **进度信息** 及 **施工图交付凭证、尾款支付凭证、终稿、定金支付凭证、初稿** 的操作数据
- 09-21 返回数据 增加了每一步的操作时间
- 09-20 返回数据做了详细的说明和示例

## 参数

    {
        "task_id": 1, // 订单ID
        "designer_id": 1 // 设计师ID
    }

## 返回数据

    {
        "process": {
            "vr_url": "", // 3d案例的链接
            "step_id": 1, // 当前步骤id，设计师与订单的关联表

以下数据 step_list 为拉取的 订单所有步骤 的列表，具体多少步骤 从步骤配置表获取  
在其中一些步骤，需要额外返回 操作数据（初稿数据，终稿数据等）

            'step_list':[

步骤0 - 发布并审核(7)

                {
                    "step_id": 0, // 步骤id
                    "step_title": "发布", // 当前步骤标题
                    "step_discript": "", // 当前步骤描述
                    "time": 11354546489, // 操作时间(发布时间)
                },

步骤1 - 抢单(8)

                {
                    "step_id": 1,
                    "step_title": "抢单",
                    "step_discript": "",
                    "time": 11354546489, // 操作时间(抢单时间)
                },

步骤2 - 上传初稿(9)

                {
                    "step_id": 2,
                    "step_title": "上传初稿",
                    "step_discript": "",
                    "time": 11354546489, // 操作时间

> 额外返回 **初稿** 的操作数据

                    "first_draft": {
                        "process_id": 1, // 进度id
                        "photo":{ // 初稿图片
                            "ori": "", // 大图PC
                            "big": "", // 大图PC
                            "mid": "", // 中图wap
                            "sml": "", // 中图wap
                        },
                        "explain": "", // 设计说明
                        "deposit": "", // 定金金额
                        "choose_status": 1, // 用户选择状态，0待选择，1选择，2淘汰
                        "audit_status": 1, // 公司审核状态，0待审核，1通过，2不通过
                        "time": 11354546489, // 上传时间
                    }
                },

步骤3 - (公司)审核初稿(10)

                {
                    "step_id": 3,
                    "step_title": "",
                    "step_discript": "",
                    "time": 11354546489, // 操作时间
                },

步骤4 - (用户)选初稿(11)

                {
                    "step_id": 4,
                    "step_title": "选初稿",
                    "step_discript": "",
                    "time": 11354546489, // 操作时间
                },

步骤5 - 支付定金（上传支付凭证）(12)

                {
                    "step_id": 5,
                    "step_title": "支付定金",
                    "step_discript": "",
                    "time": 11354546489, // 操作时间

> 额外返回 **支付凭证** 的操作数据

                    "first_reception": {
                        "photo":{ // 凭证图片
                            "ori": "", // 大图PC
                            "big": "", // 大图PC
                            "mid": "", // 中图wap
                            "sml": "", // 中图wap
                        },
                        "amount": 1, // 金额
                        "time": 11354546489, // 上传时间
                    }
                },

步骤6 - (平台)审核定金支付凭证(13)

                {
                    "step_id": 6,
                    "step_title": "审核定金支付凭证",
                    "step_discript": "",
                    "time": 11354546489, // 操作时间
                },

步骤7 - 上传终稿(14)

                {
                    "step_id": 7,
                    "step_title": "上传终稿",
                    "step_discript": "",
                    "time": 11354546489, // 操作时间

> 额外返回 **终稿** 的操作数据

                    "final_draft": {
                        "process_id": 1, // 进度id
                        "room_list|8": [ // 房间列表
                            {
                                "name": "", // 房间名称 客厅，餐厅，卧室2、儿童房、玄关、书房、厨房，卫生间，阳台等
                                "explain": "", // 说明
                                "part": [ // 局部
                                    {
                                        "name": "", // 局部名，电视墙，浴室柜等(房间的局部)
                                        "photo": {  // 图片
                                            "ori": "",
                                            "big": "",
                                            "mid": "",
                                            "sml": "",
                                        }
                                    },
                                    // ..
                                ],
                            }
                            // ...
                        ],
                        "explain": "", // 设计说明
                        "retainage": "", // 尾款金额
                        "practical_area": //户型实际面积
                        "practical_style": //设计实际风格
                        "charge": //设计师的收费标准
                        "design_budget": //客户的设计预算（如果师定额设计）
                        "is_quota": //是否定额设计标记
                        "choose_status": 1, // 用户选择状态，0待选择，1选择，2淘汰
                        "audit_status": 1, // 公司审核状态，0待审核，1通过，2不通过
                        "time": 11354546489, // 上传时间
                    }
                },

步骤8 - (公司)审核终稿(15)

                {
                    "step_id": 8,,
                    "step_title": "审核终稿",
                    "step_discript": "",
                    "time": 11354546489, // 操作时间
                },

步骤9 - (用户)选择终稿(16)

                {
                    "step_id": 9,
                    "step_title": "选择终稿",
                    "step_discript": "",
                    "time": 11354546489, // 操作时间
                },

步骤10 - 支付尾款(上传支付凭证)(17)

                {
                    "step_id": 10,
                    "step_title": "支付尾款",
                    "step_discript": "",
                    "time": 11354546489, // 操作时间

> 额外返回 **上传支付凭证** 的操作数据

                    "final_reception": {
                        "photo":{ // 凭证图片
                            "ori": "", // 大图PC
                            "big": "", // 大图PC
                            "mid": "", // 中图wap
                            "sml": "", // 中图wap
                        },
                        "amount": 1, // 金额
                        "time": 11354546489, // 上传时间
                    }
                },

步骤11 - (平台)审核尾款支付凭证(18)

                {
                    "step_id": 11,
                    "step_title": "审核尾款支付凭证",
                    "step_discript": "",
                    "time": 11354546489, // 操作时间
                },

步骤12 - 交付施工图给用户（上传交付凭证供平台审核）(19)

                {
                    "step_id": 12,
                    "step_title": "上传施工图凭证",
                    "step_discript": "",
                    "time": 11354546489, // 操作时间

> 额外返回 **施工图交付凭证** 的操作数据

                    "cad_reception": {
                        "photo":{ // 凭证图片
                            "ori": "", // 大图PC
                            "big": "", // 大图PC
                            "mid": "", // 中图wap
                            "sml": "", // 中图wap
                        },
                        "audit_status": 1, // 公司审核状态，0待审核，1通过，2不通过
                        "time": 11354546489, // 上传时间
                    }
                },

步骤13 - (平台审核施工图通过自动完结)审核完结(80)

                {
                    "step_id": 13,
                    "step_title": "审核完结",
                    "step_discript": "",
                    "time": 11354546489, // 操作时间
                },
            ]
        },
        "message": "获取数据成功!",
        "status": 200
    }
