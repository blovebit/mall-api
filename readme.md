# 益装网api需求

目录条目前的数字表示最后更改的日期，若无，表示至初稿后还未更新  
**避免浪费效率，建议先实现更新过的文档，没更新过的文档大都不完整或有缺陷**   
8月30号沟通后，日期统一更改为8-30

## 页面展示类

- 08-30 [登录/注册](./api/login.md): login,register

- 获取获取订单信息

  - 08-30 [任务大厅获取订单列表](./api/getTaskList.md): getTaskList
  - 08-30 [获取我的订单列表](./api/getMyTaskList.md): getMyTaskList
  - 09-07 [获取订单信息](./api/getTaskProfile.md): getTaskProfile
  - 08-30 [获取公司订单列表](./api/getCompanyMyTaskList.md): getCompanyMyTaskList
  - 08-30 [获取订单进度与设计](./api/getTaskProcess.md): getTaskProcess
  - 09-07 [获取各进度的设计详情](./api/getTaskDetail.md): getTaskDetail  
    这两个接口分别从不同维度查询订单设计详情，  
    前者以 **设计师** 为查询条件，查询该订单该设计师的 各个进度的稿件详情  
    后者以 **进度** 为查询雕件，查询该订单该进度的 各个设计师的稿件详情
  - 08-30 [获取评价选项](./api/getReviewOption.md): getReviewOption
  - [获取设计师未开始订单列表](./api/noStartTask.md): getNoStartTask
  <!-- - [设计师获取订单进度详情](./api/getDesignerTaskProcess.md): getDesignerTaskProcess -->
  <!-- - [(用户)获取订单设计详情](./api/getTaskDraft.md): getTaskDraft -->
  <!-- - [(公司)查看订单详情](./api/getCompanyTaskDetail.md): getCompanyTaskDetail -->

- 获取用户信息相关

  - 08-30 [获取公司列表](./api/getCompanyList.md): getCompanyList
  - 08-30 [获取公司简要信息](./api/getCompanyProfile.md): getCompanyProfile  
  - 08-30 [获取公司资料信息](./api/getCompanyDetail.md): getCompanyDetail
  - 08-30 [公司名模糊查询](./api/getCompanyName.md): getCompanyName
  - 08-30 [查看员工列表](./api/getStaffList.md): getStaffList
  - 08-30 [首页推荐设计师列表](./api/getIndexDesignerList.md): getIndexDesignerList
  - 08-30 [获取员工详情](./api/getStaffDetail.md): getStaffDetail
  - 09-08 [获取用户信息](./api/getUserInfo.md): getUserInfo
  <!-- - [查看工地列表](./api/getCompanyProjectList.md): getCompanyProjectList -->
  - 08-30 [获取在建工地列表](./api/getWorkingProjectList.md): getWorkingProjectList
  - 08-30 [获取案例列表](./api/getCaseList.md): getCaseList
  - 08-30 [获取案例详情](./api/getCaseDetail.md): getCaseDetail
  - 08-30 [获取活动列表](./api/getPromotionList.md): getPromotionList
  - 08-30 [获取活动详情](./api/getPromotionDetail.md): getPromotionDetail
  - 08-30 [获取益币操作日志](./api/getCoinLog.md): getCoinLog
 

## 数据操作类

- 通用操作

  - [上传图片](./api/uploadPicture.md): uploadPicture
  - [删除图片](./api/deletePicture.md): deletePicture
  - [喜欢点赞](./api/like.md): like
  - [吐槽](./api/discuss.md): discuss
  - [获取吐槽](./api/getDiscussList.md): getDiscussList
  - [所有个人用户提交认证操作](api/personageCertificate.md): certificate
  - [公司提交认证操作](api/companyCertificate.md): certificate
  - [认证专用上传图片](./api/certificateUpload.md): certificateUpload
  - [充值](./api/recharge.md): recharge
  - [设计师拒单操作](./api/rejectTask.md): rejectTask
  - [设计师上传原创案例操作](./api/createCase.md): createCase
  - [设计师订单关联酷家乐案例id操作](./api/createTaskRelationKjl.md): createTaskRelationKjl


- 订单操作相关

  - [创建订单](./api/createTask.md): createTask
  - [用户完善订单信息(未定)](./api/improveTask.md): improveTask
  - [(设计师)抢单](./api/grabTask.md): grabTask
  - [提交方案](./api/commitDraft.md): commitDraft
  - 08-30 [用户选择设计方案](./api/chooseTaskDraft.md): chooseTaskDraft
  - [(用户)评价](./api/commentTask.md): commentTask
  - [(公司)审核设计师的设计](./api/reviewDraft.md): reviewDraft

- 公司管理操作

  - [公司管理员工状态](./api/manageStaff.md): manageStaff
  - [员工离职申请](./api/laborTurnover.md): laborTurnover
  - [公司审核员工离职申请](./api/auditLaborTurnover.md): auditLaborTurnover
  - [设计师发起公司变更操作](./api/changeMyCompany.md): changeMyCompany
  - [公司提交活动操作](./api/createPromotion.md): createPromotion
  - [(公司)上传活动封面图](./api/uploadCover.md): uploadCover