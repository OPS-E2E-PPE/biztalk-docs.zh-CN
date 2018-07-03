---
title: 如何验证消息的活动状态 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities, verifying status
- PeopleSoft Integration Broker
- verifying message status in PeopleSoft
- messages, verifying status
ms.assetid: b8cee6f9-0f65-4228-a87a-3f3aca6182bf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8af3a77b9bb169e394571444c7eb7e3984f7f7c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013038"
---
# <a name="how-to-verify-activity-status-of-a-message"></a>如何验证消息的活动状态
使用 PeopleSoft Integration Broker 创建 PeopleSoft HTTP 主机和端口发送事件。 通过执行以下步骤确保消息处于活动状态并且已被路由。  
  
### <a name="to-verify-that-a-message-is-active-and-routed-correctly"></a>验证消息是否处于活动状态并被正确路由  
  
1. 单击**启动**，依次指向**程序**，指向**PeopleSoft 应用程序名称**，然后选择**应用程序设计器**。  
  
2. 上**PeopleSoft 登录**屏幕中，输入**用户 ID**并**密码**，然后单击**确定**。  
  
    ![](../core/media/psadapter-24-task-userpass.gif "PSAdapter_24_Task_UserPass")  
  
    ![](../core/media/psadapter-25-task-emptydesigner.gif "PSAdapter_25_Task_EmptyDesigner")  
  
3. 在应用程序设计器上**文件**菜单，依次指向**打开**，然后选择**消息**。  
  
    ![](../core/media/psadapter-26-task-filemessage.gif "PSAdapter_26_Task_FileMessage")  
  
4. 在中**打开定义**屏幕上，在**名称**字段中，输入`LOCATION_SYNC`，然后单击**打开**。  
  
    ![](../core/media/psadapter-27-task-locationsync.gif "PSAdapter_27_Task_LocationSync")  
  
5. 在中**定义匹配选择条件**部分中，双击**LOCATION_SYNC**消息以查看属性。  
  
    ![](../core/media/psadapter-28-task-locationproperties.gif "PSAdapter_28_Task_LocationProperties")  
  
6. 在应用程序设计器中，右键单击**LOCATION_TBL**，然后选择**消息属性**。  
  
    ![](../core/media/psadapter-29-task-loctionmenu.gif "PSAdapter_29_Task_LoctionMenu")  
  
7. 上**消息属性**屏幕上，单击**使用**选项卡。  
  
    验证以下内容，然后依次**确定**。  
  
   1. **消息：** Active  
  
   2. **消息通道：** ENTERPRISE_SETUP  
  
   3. **默认版本：** VERSION_1  
  
      ![](../core/media/psadapter-30-task-messageuse.gif "PSAdapter_30_Task_MessageUse")  
  
8. 退出 Application Designer。  
  
    这可确保消息处于活动状态、使用 VERSION_1 并流经 PeopleSoft 中的 ENTERPRISE_SETUP 通道。  
  
9. 配置 Integration.Gateway.properties 文件以与 PeopleSoft 应用程序通信。  
  
     验证是否设置了以下属性：  
  
    -   **ig.isc.serverurl:** //server:9000  
  
    -   **ig.isc.userid:** PS 的 ID  
  
    -   **ig.isc.password:** PS 的密码  
  
    -   **ig.isc.toolsrel:** 特定版本  
  
## <a name="see-also"></a>请参阅  
 [创建 PeopleSoft HTTP 主机和端口](../core/creating-a-peoplesoft-http-host-and-port.md)