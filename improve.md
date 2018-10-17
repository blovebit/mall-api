# 接口修改文档

## 10-17

- /rest/v2/order/getTaskList 订单列表 [接口文档](./api/getTaskList.md)
  - 返回数据 增加 "burning": int, // 信息费（需要消耗益币数）

- /rest/v2/user/getIndexDesignerList 设计师列表 [接口文档](./api/getTaskList.md)
  - 返回数据 level返回了0 最低默认 应为 1
  - 返回数据 增加 level_name 等级相应的名称 “初级设计师、资深设计师等”

## 10-16

- /rest/v2/company/getStaffList 员工列表 [接口文档](./api/getStaffList.md)
  - 公司判断 如果没有查询参数 company_id， 用 token 判断

- /rest/v2/order/getTaskList 获取任务大厅列表 [接口文档](./api/getTaskList.md)
  - 查询条件 增加 是否过期（招标结束） 的字段 is_close ，查询相应的数据。
  - 返回数据 增加订单专员对订单的描述字段
  - 返回数据 默认按照审核通过时间 倒序

- /rest/v2/order/grabTask 抢单 [接口文档](./api/grabTask.md)
  - 抢单限制 一个公司（益装网平台除外）只允许一个设计师抢同一个单
  - 招标结束机制 抢单人数达到了订单设置的最大数，订单招标时间自动结束，不需要等时间到了才结束

- /rest/v2/company/auditLaborTurnover 员工管理
  - post数据 增加益币coin, 表示分配给公司员工改数量的益币
  - post数据 员工id改为多个值，允许批量操作

- 增加接口 getRelatedTel 用户在个人中心获取订单相关方的电话
  - 如：业主再我的订单页面 获取该订单设计师的电话
  - 如：设计师再我的订单中 获取业主的电话
  - 如：业主获取其订单设计师公司的电话
  - 需要鉴权，必须为订单相关方，且在订单信息费扣除成功后

## 10-15

- /rest/v2/order/getTaskProcess 订单进度与设计详情 [接口文档](./api/getTaskProcess.md)
  - 没有返回全部步骤

- /rest/v2/order/getMyTaskList 我的订单列表 [接口文档](./api/getMyTaskList.md)
  - 账号18328544304 传 role_id： 2 时 返回500
  - 账号18280195859 传 role_id： 3 时 返回400

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