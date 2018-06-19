---
title: 如何配置并安排接收位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, receive locations
- managing [receive locations], scheduling
- scheduling, receive locations
- managing [receive locations], configuring
ms.assetid: 2653e1c3-ddbd-4d3f-be64-2a5fcd7cf267
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea43814d6b7c23875bc222f6d6bd4aee5468b60f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248701"
---
# <a name="how-to-configure-scheduling-for-a-receive-location"></a>如何为接收位置配置计划
本主题将介绍如何使用 BizTalk Server 管理控制台为接收位置配置计划属性。 您可以指定希望接收位置开始和停止处理消息的日期。 还可以指定希望接收位置在一天中的哪几个时间来处理消息。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-scheduling-for-a-receive-location"></a>为接收位置配置计划  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要为其配置接收位置计划的 BizTalk 组和 BizTalk 应用程序。  
  
3.  单击**接收位置**，右键单击接收位置，然后单击**属性**。  
  
4.  在左窗格中，单击**计划**下, 表中所述配置计划的属性，然后单击**确定**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**开始日期**|选中此复选框，然后从下拉日历中，选择接收位置开始处理消息的日期。 若要更改年份，请单击所显示的年份。|  
    |**停止日期**|选中此复选框，然后从下拉日历中，选择接收位置停止处理消息的日期。 此属性是可选的。 如果没有指定停止日期，则在禁用此接收位置之前此接收位置将一直保持活动状态。|  
    |**启用服务时段**|选中此复选框以配置到接收消息的接收位置，则只有在指定时间的一天，然后指定中的这些时间**开始时间和停止时间**框。 如果清除此复选框，则该接收位置可随时接收消息。 默认值为 False（清除复选框）。|  
    |**开始时间**|指定接收位置应开始接收消息的时间。 此框是时才可用**启用服务窗口**复选框处于选中状态。|  
    |**停止时间**|指定接收位置应停止接收消息的时间。 此框是时才可用**启用服务窗口**复选框处于选中状态。|  
  
## <a name="see-also"></a>另请参阅  
 [管理接收位置](../core/managing-receive-locations.md)