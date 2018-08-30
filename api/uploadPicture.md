# 上传图片: uploadPicture

- 用户创建任务，设计师上传设计稿，工地上传施工图等

## 参数

    {
        'scene': Int, // 图片场景；0：用户发布订单时上传户型图；1：设计师上传稿件时的方案图；2设计师上传原创案例
        'part_id': Int, // 房间id；此id与上传方案关联，户型图不需要
        'iamge_type': String, // 'image' || 'MP4'
        'width': Int, // 图片宽度 px
        'height': Int, // 图片高度 px
        'size': Int, // 图片大小 bye
        'info': String, // 设计师对房间设计的描述
        'process_id': Int, // 进度id；为空时新建进度；
        'case_id': Int, // 案例id；该id为设计师上传原创案例id；
    }

## 返回数据

    {
        // ... status, message
        'content': {
            'content': {
                'id': Int, // 如果请求体里面的secne为户型图，返回订单id；如果为方案图，返回进度id；
                'img_id': Int // 图片ID
                'ori_path': // 原始图路径
                'big_path': // 大图路径
                'mid_path': // 中图路径
                'sml_path': // 小图路径
            }
        }
    }

## 说明

- 每次调用接口，仅上传一张图片，需要根据processID关联该进度所有空间图片