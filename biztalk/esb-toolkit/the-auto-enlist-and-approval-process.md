---
title: 自动登记和审批过程 |Microsoft 文档
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
ms.openlocfilehash: 333e1403ffd45f80a98d3eb17f5d3aa2b63c7798
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295621"
---
# <a name="the-auto-enlist-and-approval-process"></a>自动登记和审批过程
你可以配置 ESB 管理门户以两种方式发布 Microsoft BizTalk Server 终结点：  
  
-   它可以通过审批过程，其中管理员必须确认和审批注册请求配置。  
  
-   这可以通过使用配置自动发布，其中门户仪表板请求到通用、 描述、 发现和集成 (UDDI) 注册表而无需管理员干预。  
  
 以下两个过程中所述，还可以指定多个门户中，UDDI 集成功能的其他设置。  
  
### <a name="to-configure-auto-approval-and-publishing-in-the-esb-management-portal"></a>若要在 ESB 管理门户中配置自动批准和发布  
  
1.  请确保您登录到使用 BizTalk Server Administrators 组的成员的帐户门户。  
  
2.  指向**管理员**在门户的主菜单上，选项卡，然后单击**注册表设置**以打开门户[注册表设置页](../esb-toolkit/registry-settings-page.md)。  
  
3.  若要启用自动批准和发布，在顶部的文本框中键入 UDDI 服务器的 URL **UDDI 详细信息**部分页上，，然后选择**自动发布**复选框。  
  
4.  若要禁用自动批准和发布，清除**自动发布**复选框。  
  
### <a name="to-configure-e-mail-and-registry-settings-for-the-uddi-integration-features"></a>若要配置的 UDDI 集成功能的电子邮件和注册表设置  
  
1.  请确保您登录到使用 BizTalk Server Administrators 帐户组的成员的帐户门户。  
  
2.  指向**管理员**在门户的主菜单上，选项卡，然后单击**注册表设置**以打开门户[注册表设置页](../esb-toolkit/registry-settings-page.md)。  
  
3.  编辑 UDDI 服务器在顶部的文本框中的 URL **UDDI 详细信息**页的部分。 默认 UDDI 服务是本地的 Microsoft UDDI 服务。  
  
4.  选择**匿名**复选框，如果你希望在门户中访问 UDDI 服务器时使用匿名身份验证。  
  
5.  如果你希望在门户以通过电子邮件时 UDDI 发布通知你的请求正在等待批准，请选择**启用通知**中的复选框**电子邮件通知**页的部分。 然后输入电子邮件服务器、 电子邮件的传递地址、 适当 '发件人"电子邮件地址、 邮件主题和消息正文的详细信息。  
  
6.  输入管理员联系人姓名和电子邮件地址为 UDDI 接收请求中的电子邮件**默认设置**页的部分。  
  
### <a name="to-approve-or-decline-a-registration-request-as-an-administrator"></a>若要批准或拒绝以管理员身份注册请求  
  
1.  请确保你登录到使用 BizTalk Server Administrators 组的成员的帐户门户。  
  
2.  指向**注册表**在门户的主菜单上，选项卡，然后单击**管理挂起的请求**以打开门户[管理挂起的请求页](../esb-toolkit/manage-pending-requests-page.md)。  
  
3.  若要批准挂起的请求，请单击**批准**列表中该请求旁边的图标 （复选标记）。  
  
4.  若要拒绝挂起的请求，请单击**拒绝**列表中该请求旁边的图标 （交叉标记）。  
  
5.  若要查看的挂起请求的详细信息，请单击**查看详细信息**图标 （放大镜） 以打开[注册表的详细信息页](../esb-toolkit/registry-details-page.md)。 你可以发布、 删除或更新此页中的请求。  
  
6.  若要查看请求状态，并查看以前的请求的列表，请单击**查看请求历史记录**链接。