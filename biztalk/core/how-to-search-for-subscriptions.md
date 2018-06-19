---
title: 如何搜索订阅 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Query tab [Administration Console], subscriptions
- Query tab [Administration Console], searching
- subscriptions, viewing
- subscriptions, searching
ms.assetid: 95f8fd20-2750-412b-a67b-18976e7706e2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1830a4c1dddfa3dcfc2a1177b69410dd8ee0ac
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22255517"
---
# <a name="how-to-search-for-subscriptions"></a>如何搜索订阅
你可以使用 **查询** 在 BizTalk Server 管理控制台中以搜索订阅的选项卡。 当希望查看系统中定义的所有订阅时，这就非常有用。 在排除路由故障时，您可以查看是不是由于某些订阅未正确设置而导致了路由故障。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，则必须以 BizTalk Server Operators 组成员的身份登录。  
  
### <a name="to-search-for-subscriptions"></a>搜索订阅  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  
  
2.  在控制台树中，展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”，然后单击“BizTalk 组”。  
  
3.  在详细信息窗格中，单击 **新查询** 选项卡。  
  
4.  在 **查询表达式** 组中，在 **值** 列中，选择 **订阅** 从下拉列表框。  
  
5.  在 **字段名称** 旁边星号的空下拉列表框中的列，(**\***)，选择一个或多个以下︰  
  
    |项|Description|  
    |----------|-----------------|  
    |**最大匹配数**|要显示的匹配数。|  
    |**服务实例 ID**|您可以按服务实例 ID 对订阅进行筛选。|  
    |**服务名称**|您可以按服务名对订阅进行筛选。|  
    |**订阅类型**|您可以按“激活订阅”或“实例订阅”对订阅进行筛选。|  
  
6.  完成 **值** 列的适合于所选内容所做中 **字段名称** 列。  
  
7.  继续向视情况而定查询添加更多的行，通过完成 **字段名称**, ，**运算符**, ，和 **值** columns 和 then click **运行查询**。  
  
## <a name="see-also"></a>另请参阅  
 [使用管理控制台的“查询”选项卡](../core/using-the-administration-console-query-tab.md)