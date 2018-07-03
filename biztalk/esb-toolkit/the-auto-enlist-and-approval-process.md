---
title: 自动登记和审批流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfd3e72e-e28b-4ee3-bc4a-89ef3f64e6d5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39dae57d3265ed4e8a383c315276a7e8c510ce37
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968142"
---
# <a name="the-auto-enlist-and-approval-process"></a>自动登记和审批过程
可以配置 ESB 管理门户以两种方式发布 Microsoft BizTalk Server 终结点：  
  
- 它可以通过审批过程，管理员必须确认和审批注册请求的配置。  
  
- 这可以通过使用配置自动发布，其中在门户仪表板请求到通用描述、 发现和集成 (UDDI) 注册表而无需管理员干预。  
  
  以下两个过程中所述，还可以指定多个其他设置的门户中，UDDI 集成功能。  
  
### <a name="to-configure-auto-approval-and-publishing-in-the-esb-management-portal"></a>ESB 管理门户中配置自动审批和发布  
  
1.  请确保您登录到在门户中使用该帐户是 BizTalk Server Administrators 组的成员。  
  
2.  指向**管理员**在门户的主菜单上，选项卡，然后单击**注册表设置**以打开门户[注册表设置页](../esb-toolkit/registry-settings-page.md)。  
  
3.  若要启用自动审批和发布，可在顶部文本框中键入 UDDI 服务器的 URL **UDDI 的详细信息**部分中的页上，并选择**以自动发布**复选框。  
  
4.  若要禁用自动审批和发布，请清除**自动发布**复选框。  
  
### <a name="to-configure-e-mail-and-registry-settings-for-the-uddi-integration-features"></a>若要配置的 UDDI 集成功能的电子邮件和注册表设置  
  
1.  请确保您登录到在门户中使用该帐户是 BizTalk Server 管理员帐户组的成员。  
  
2.  指向**管理员**在门户的主菜单上，选项卡，然后单击**注册表设置**以打开门户[注册表设置页](../esb-toolkit/registry-settings-page.md)。  
  
3.  编辑 UDDI 服务器顶部的文本框中的 URL **UDDI 的详细信息**页部分。 默认的 UDDI 服务是本地的 Microsoft UDDI 服务。  
  
4.  选择**Anonymous**复选框，如果希望在门户中访问 UDDI 服务器时使用匿名身份验证。  
  
5.  如果希望在门户中通过电子邮件时 UDDI 发布通知您的请求正在等待批准，请选择**启用通知**中的复选框**电子邮件通知**页部分。 然后输入电子邮件服务器、 发送电子邮件地址、 相应的 '发件人"电子邮件地址、 邮件主题和消息正文的详细信息。  
  
6.  输入管理员联系人姓名和电子邮件地址的 UDDI 回执请求中的电子邮件**默认设置**页部分。  
  
### <a name="to-approve-or-decline-a-registration-request-as-an-administrator"></a>若要批准或拒绝以管理员身份注册请求  
  
1.  请确保登录到在门户中使用该帐户是 BizTalk Server Administrators 组的成员。  
  
2.  指向**注册表**在门户的主菜单上，选项卡，然后单击**管理挂起的请求**以打开门户[管理挂起的请求页](../esb-toolkit/manage-pending-requests-page.md)。  
  
3.  若要批准挂起的请求，请单击**批准**列表中该请求旁边的图标 （复选标记）。  
  
4.  若要拒绝挂起的请求，请单击**拒绝**列表中该请求旁边的图标 （十字标记）。  
  
5.  若要查看挂起的请求的详细信息，请单击**查看详细信息**图标 （放大镜） 以打开[注册表详细信息页](../esb-toolkit/registry-details-page.md)。 您可以发布、 删除或更新此页中的请求。  
  
6.  若要查看请求状态，并查看以前的请求的列表，请单击**查看请求历史记录**链接。