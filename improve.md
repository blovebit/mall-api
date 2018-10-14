# 接口修改文档

## 10-14

- /rest/v2/order/getTaskList 订单数据 [接口文档](./api/getTaskList.md)
  - 订单没有户型图时，返回数据 layout_pic 为 null
  - 需要配置一张默认图片，

## 10-13 接口待改进

- /rest/v2/user/getUserInfo  获取用户基本信息 [接口文档](./api/getUserInfo.md)
  - 如果是公司
  - 返回数据 增加公司id

- /rest/v2/company/getCompanyName  公司名模糊查询 [接口文档](./api/getCompanyName.md)
  - 返回数据 增加公司id

- /rest/v2/ad/getPromotionList  获取装修公司活动列表 [接口文档](./api/getPromotionList.md)
  - 返回500