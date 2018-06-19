---
title: 配置常见回退属性的 X12 和 EDIFACT 编码消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7393d6ac-b901-43ef-a8d6-c5b0b3033257
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b99d6e60a2a5955a9f0873156dbc5f822b3d519
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006030"
---
# <a name="configuring-common-fallback-properties-for-x12-and-edifact-encoded-messages"></a>为 X12 和 EDIFACT 编码的消息配置通用后备属性
后备属性同时适用于 X12（包括 HIPAA）和 EDIFACT 编码的交换。 和所有后备协议属性一样，仅当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 尚未确定解析传入或传出消息所用的协议时，这些属性才适用。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-set-common-global-properties"></a>设置公用全局属性  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 回退设置**或**EDIFACT 回退设置**。  
  
2.  在**回退设置常规页**选项卡上，在**常规**页上，执行以下操作：  
  
    1.  单击**启用回退设置**启用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用回退协议设置，如果没有协议已解决的传入或传出消息。  
  
        > [!IMPORTANT]
        >  如果未选中该选项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将不使用后备协议中的属性集。  
  
    2.  单击**激活 EDI 报告**激活报告的所有 EDI 消息。 这可确保消息均显示在状态报告功能，通过单击底部的链接可显示的屏幕**组中心数据库**BizTalk Server 管理控制台窗格。  
  
    3.  如果你单击**激活 EDI 报告**，单击**存储事务的一组负载，可用于报告**存储事务设置中的跟踪 (BizTalkDTADb) 数据库的 EDI 表。  
  
    4.  单击**日志 EDI 错误和警告由 EDI 引擎到 Windows 事件日志生成**记录错误/警告消息由 EDI 引擎 （EDI 管道，批处理业务流程，路由业务流程，等等），生成的上下文向 Windows 事件查看器的信息。 如果清除此项，则这些错误/警告消息将不会记录到事件查看器中。  
  
        > [!NOTE]
        >  无论是否选中此复选框，系统/处理错误都会记录到事件查看器中。  
  
3.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**若要验证并接受所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置全局或后备协议属性](../core/configuring-global-or-fallback-agreement-properties.md)