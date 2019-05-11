---
title: 编码的消息配置通用后备属性适用于 X12 和 EDIFACT |Microsoft Docs
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
ms.openlocfilehash: a6f15f3ae839be446cfb10581a3514cc9093d641
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356132"
---
# <a name="configuring-common-fallback-properties-for-x12-and-edifact-encoded-messages"></a>为 X12 和 EDIFACT 编码的消息配置通用后备属性
后备属性同时适用于 X12 （包括 HIPAA） 和 EDIFACT 编码的交换。 与所有后备协议属性，这些属性应用时，才[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]尚未确定所用的协议解析为的传入或传出消息。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-set-common-global-properties"></a>若要设置公用全局属性  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**或**EDIFACT 后备设置**。  
  
2. 在中**回退设置常规页**选项卡中，**常规**页上，执行以下操作：  
  
   1. 单击**启用回退设置**若要启用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用后备协议设置，如果没有协议可解析为传入或传出消息。  
  
      > [!IMPORTANT]
      >  如果未选中此选项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不会使用后备协议中设置的属性。  
  
   2. 单击**激活 EDI 报告**以激活报告所有 EDI 消息。 这可确保消息显示在状态报告功能，通过单击底部的链接显示的屏幕**组中心**窗格中的 BizTalk Server 管理控制台。  
  
   3. 如果单击了**激活 EDI 报告**，单击**存储事务集/负载以用于报告**来存储事务集跟踪 (BizTalkDTADb) 数据库的 EDI 表中。  
  
   4. 单击**EDI 错误和警告记录到 Windows 事件日志的 EDI 引擎生成的**记录由 EDI 引擎 （EDI 管道、 批处理业务流程、 路由业务流程等），生成具有上下文的错误/警告消息Windows 事件查看器的信息。 如果未选中状态，这些错误/警告消息将不会记录到事件查看器。  
  
      > [!NOTE]
      >  系统/处理错误记录在事件查看器中，无论选中此复选框。  
  
3. 单击**Apply**接受所做的更改，然后才能继续进行配置，或单击**确定**以验证并接受所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置全局或后备协议属性](../core/configuring-global-or-fallback-agreement-properties.md)