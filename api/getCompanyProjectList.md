# （公  司）查看工地列表: getCompanyProjectList

- 10-19 增加一个阶段id字段

## 参数

    {
        'process': // 默认全部 1:施工中；2：已竣工；
        'start_time': // 开工时间；
        'end_time': // 结束时间；
        'step_id': // 节点；
        'keywords': // 查询关键字；
        'page': //当前页
        'size': //每页数量
    }

## 返回数据

    {
        'project_list': [
            {
                'project_id': 工地id
                'village': // 小区名称
                'costomer_name': // 业主姓名
                'area': // 面积
                'unit': // 户型
                'style': // 风格
                "complete_status": "", // 施工状态
                "current_step": int, // 当前施工进度（大阶段nodeid）
                'province': // 省
                'city': // 市
                'region': // 区
                'address': // 地址
                'cover':{ //封面图
                    'ori_path': // 原始图路径
                    'big_path': // 大图路径
                    'mid_path': // 中图路径
                    'sml_path': // 小图路径
                }
            }
            // ...
        ],
        "item_total": int, // 数据总条数
        "message": "数据获取成功!",
        "status": 200
    }
