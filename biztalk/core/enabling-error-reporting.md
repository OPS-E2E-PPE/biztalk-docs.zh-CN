---
title: 启用错误报告 |Microsoft Docs
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
ms.openlocfilehash: 0040e467bf77de9b55333862dadd87ff940bbeba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389314"
---
# <a name="enabling-error-reporting"></a>启用错误报告
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以选择是否想要在 Windows 事件查看器中显示错误和警告。  
  
 下面的过程启用或禁用报告由 EDI 报告机制或 EDI 引擎生成的错误或警告。 你可以启用报告此类错误或警告作为协议的一部分或作为备用协议的一部分。 作为协议的一部分，默认情况下启用此报告。 作为备用协议的一部分，默认情况下禁用此报告。 但是，通过生成系统/处理错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]始终记录在事件查看器 (显示通过输入`eventvwr`中**运行**对话框)，无论是否启用 EDI 错误或警告。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-enable-error-reporting-for-an-agreement"></a>若要为协议启用错误报告  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]并**BizTalk 组**节点，单击**参与方**节点。  
  
2. 在中**参与方和业务配置文件**窗格中，单击包含您要为其启用日志记录错误和警告记录到事件日志的 X12 或 EDIFACT 协议的参与方。  
  
   > [!NOTE]
   >  不能错误和警告记录到事件查看器用于 AS2 协议。  
  
3. 在中**协议**部分中，右键单击你想要启用日志记录错误和警告，然后单击的 X12 或 EDIFACT 协议**属性**。  
  
4. 在中**公用主机设置**部分中，单击**记录到事件日志错误**或**警告记录到事件日志**。  
  
5. 单击**确定**或单击**应用**。  
  
### <a name="to-enable-error-reporting-as-part-of-a-fallback-agreement"></a>若要启用错误报告作为备用协议的一部分  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点下的**BizTalk 组**节点，，然后单击**X12 后备设置**或**EDIFACT 后备设置**。  
  
2. 在中**回退设置常规页**选项卡上，若要启用的日志记录的 EDI 错误或警告 BizTalk EDI 引擎生成的单击**EDI 错误和警告记录到 Windows 事件日志EDI引擎生成的**. 错误日志将包含错误数据和上下文信息。  
  
   > [!NOTE]
   >  系统/处理错误记录在事件查看器中，无论选中此复选框。  
  
   > [!NOTE]
   >  无需选择**激活 EDI 报告**属性，即可选择**EDI 错误和警告记录到 Windows 事件日志的 EDI 引擎生成的**属性。  
  
## <a name="see-also"></a>请参阅  
 [监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md)   
 [EDI 确认错误代码](../core/edi-acknowledgment-error-codes.md)   
 [AS2 事件](../core/as2-events.md)