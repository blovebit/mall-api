# 接口修改文档

## 10-15

- /rest/v2/order/getMyTaskList 我的订单列表 [接口文档](./api/getMyTaskList.md)
  - role_id 传2时 返回500
  - role_id 传3时 返回400

- /rest/v2/comment/getReviewOption 评价的选项 [接口文档](./api/getReviewOption.md)
  - 返回无数据

- 工地列表 [接口文档](./api/getWorkingProjectList.md)
  - 没有接口

## 10-14

- /rest/v2/order/getTaskList 订单数据 [接口文档](./api/getTaskList.md)
  - 订单没有户型图时，返回数据 layout_pic 为 null, 需要配置一张默认图片
  - 返回数据 增加订单招标总时间 total_time
  - 订单等级默认最低等级0 改为 1

## 10-13 接口待改进

- /rest/v2/user/getUserInfo  获取用户基本信息 [接口文档](./api/getUserInfo.md) **（核实已修改）**
  - 如果是公司
  - 返回数据 增加公司id

- /rest/v2/company/getCompanyName  公司名模糊查询 [接口文档](./api/getCompanyName.md)
  - 返回数据 增加公司id

- /rest/v2/ad/getPromotionList  获取装修公司活动列表 [接口文档](./api/getPromotionList.md)
  - 返回500