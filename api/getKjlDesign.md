# 获取设计师酷家乐绑定订单数据: getKjlDesign

## 说明

- 用于设计师上传初稿获取酷家乐设计信息显示

## 参数

    {
        'order_id': //订单id
        'designer_id': //设计师id
    }  

## 返回数据
  
    {
        "content":{
            "desid":    //酷家乐案例id  
            "simg":    //酷家乐小图
            "img":     //酷家乐大图
            "vr_link": //3D链接地址
        }
        "message": "操作成功!",
        "status": 200
    }


  