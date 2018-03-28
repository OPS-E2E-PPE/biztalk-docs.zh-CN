---
title: 如何搜索跟踪的服务实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6337df9-8c2e-4d4a-a64b-cc040f83bd91
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08e5a7fa563e175d6a1d784e546bd399e20d3c21
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-search-for-tracked-service-instances"></a>如何搜索跟踪的服务实例
你可以使用**查询**选项卡中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来搜索所有跟踪的服务实例。 若要查找服务实例，您可以搜索程序集的名称和版本、生存期的开始时间和结束时间、服务类的名称或实例 ID、主机名称、错误代码和服务实例的状态。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators 组成员的身份登录。  
  
### <a name="to-search-for-tracked-service-instances"></a>搜索跟踪的服务实例  
  
1.  单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  
  
2.  在控制台树中，展开 **BizTalk Server 管理**, ，然后单击 BizTalk 组。  
  
3.  在详细信息窗格中，单击 **新查询** 选项卡。  
  
4.  在 **查询表达式** 组中，在 **值** 列中，选择 **跟踪服务实例** 从下拉列表框。  
  
5.  在 **字段名称** 旁边星号的空下拉列表框中的列，(**\***)，选择一个或多个以下︰  
  
    |项|Description|  
    |----------|-----------------|  
    |**程序集名称**|服务实例的程序集的名称。|  
    |**程序集版本**|服务实例的版本。|  
    |**结束时间**|服务实例的结束时间。|  
    |**错误代码**|与服务实例相关联的任何错误代码。|  
    |**主机名**|服务实例的主机名称。|  
    |**最大匹配数**|要显示的匹配数。|  
    |**服务类**|服务实例的类别。|  
    |**服务实例 ID**|服务实例 ID。|  
    |**服务名称**|服务实例的名称。|  
    |**开始时间**|服务实例的开始时间。|  
    |**状态**|服务实例的状态。|  
  
6.  完成 **值** 列的适合于所选内容所做中 **字段名称** 列。  
  
7.  继续向根据查询中添加更多的行，通过完成 **字段名称**, ，**运算符**, ，和 **值** columns 和 then click **运行查询**。  
  
## <a name="see-also"></a>另请参阅  
 [使用管理控制台的“查询”选项卡](../core/using-the-administration-console-query-tab.md)