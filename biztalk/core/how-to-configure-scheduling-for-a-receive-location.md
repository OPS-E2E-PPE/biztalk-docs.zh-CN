---
title: 如何配置计划的接收位置 |Microsoft Docs
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
ms.openlocfilehash: 598d26b47e954cf4299aabc0d0e77ecb4598c984
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386183"
---
# <a name="how-to-configure-scheduling-for-a-receive-location"></a>如何配置计划的接收位置
本主题介绍如何使用 BizTalk Server 管理控制台配置接收位置的计划属性。 可以指定当你想要启动和停止处理消息的接收位置的日期。 此外可以指定要处理的消息的接收位置在一天的特定时间。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-scheduling-for-a-receive-location"></a>若要配置的接收位置计划  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk 组和 BizTalk 应用程序要为其配置为接收位置计划。  
  
3. 单击**接收位置**，右键单击该接收位置，然后单击**属性**。  
  
4. 在左窗格中，单击**计划**，按下表中所述配置计划属性，然后单击**确定**。  
  
   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**开始日期**|选择此复选框，并从下拉日历中，选择接收位置开始处理消息的日期。 若要更改年份，请单击所显示的年份。|  
   |**停止日期**|选择此复选框，并从下拉日历中，选择接收位置停止处理消息的日期。 此属性是可选的。 如果不指定停止日期，则接收位置保持活动状态，直到它处于禁用状态。|  
   |**启用服务时段**|选中此复选框以配置接收消息的接收位置，仅在指定时间的日期，则指定的时间**开始时间和停止时间**框。 如果清除该复选框，则接收位置在任何时间接收消息。 默认值为 false （清除）。|  
   |**开始时间**|指定接收位置应开始接收消息的时间。 此框是时才可用**启用服务时段**复选框处于选中状态。|  
   |**停止时间**|指定接收位置应停止接收消息的时间。 此框是时才可用**启用服务时段**复选框处于选中状态。|  
  
## <a name="see-also"></a>请参阅  
 [管理接收位置](../core/managing-receive-locations.md)