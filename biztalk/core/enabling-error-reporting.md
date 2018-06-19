---
title: 启用错误报告 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1131bbd5-7ab3-4422-b6df-747c722f0b2c
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca862a57bfd2389f3be2b7ff6932ed356232abc8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241245"
---
# <a name="enabling-error-reporting"></a>启用错误报告
使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，您可选择是否要在 Windows 事件查看器中显示增强的错误和警告。  
  
 使用以下过程，可启用或禁用报告由 EDI 报告机制或 EDI 引擎生成的错误或警告。 您可以作为协议的一部分或作为备用协议的一部分来启用报告此类错误或警告。 作为协议的一部分，默认情况下此报告处于启用状态。 作为备用协议的一部分，默认情况下此报告处于禁用状态。 但是，通过生成系统/处理错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]始终记录在事件查看器 (显示通过输入`eventvwr`中**运行**对话框中)、 是否或不启用 EDI 错误或警告。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-enable-error-reporting-for-an-agreement"></a>启用协议错误报告  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]和**BizTalk 组**节点，单击**方**节点。  
  
2.  在**方和业务配置文件**窗格中，单击具有你想要启用日志记录错误和警告记录到事件日志 X12 或 EDIFACT 协议的当事方。  
  
    > [!NOTE]
    >  您无法将 AS2 协议的错误和警告记录到事件查看器。  
  
3.  在**协议**部分中，右键单击你想要启用日志记录错误和警告，，然后单击 X12 或 EDIFACT 协议**属性**。  
  
4.  在**常见主机设置**部分中，单击**记录到事件日志错误**或**警告记录到事件日志**。  
  
5.  单击**确定**或单击**应用**。  
  
### <a name="to-enable-error-reporting-as-part-of-a-fallback-agreement"></a>若要启用错误报告作为回退协议的一部分  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点下的**BizTalk 组**节点，，然后单击**X12 回退设置**或**EDIFACT 回退设置**。  
  
2.  在**回退设置常规页**选项卡上，若要启用的日志记录的 EDI 错误或警告由 BizTalk EDI 引擎，生成单击**日志 EDI 错误和警告由 EDI 引擎到 Windows 事件日志生成**. 错误日志将包括错误数据和上下文信息。  
  
    > [!NOTE]
    >  无论是否选中此复选框，系统/处理错误都会记录到事件查看器中。  
  
    > [!NOTE]
    >  无需选择**激活 EDI 报告**属性，以便选择**日志 EDI 错误和警告由 EDI 引擎到 Windows 事件日志生成**属性。  
  
## <a name="see-also"></a>另请参阅  
 [监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md)   
 [EDI 确认错误代码](../core/edi-acknowledgment-error-codes.md)   
 [AS2 事件](../core/as2-events.md)