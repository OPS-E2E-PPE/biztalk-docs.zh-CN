---
title: "配置回退本地主机设置 （EDIFACT 事务集设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0142b3fc-009f-4da5-b34d-dddf4fb96e0f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 931db62edda264a6fff0ddb422bd41b243cd29ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-local-host-settings-edifact-transaction-set-settings"></a>配置回退本地主机设置（EDIFACT-事务集设置）
为了处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 必须确定在处理和验证交换时需要使用的架构。 这包括确定与架构关联的目标命名空间和确定要使用的架构。 在后备协议的此页中，可输入要在确定目标命名空间时使用的属性。 中所述 BizTalk Server 如何确定架构[协议解析、 架构发现和接收 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>要配置事务集的本地主机设置，请执行以下操作：  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 回退设置**。  
  
2.  在**EDIFACT 回退设置**对话框中，在**EDIFACT 协议页**选项卡上，在**事务设置设置**部分中，单击**本地主机设置**。  
  
3.  选择**创建为尾随分隔符的空 XML 标记**能够包含的尾随分隔符的空 XML 标记交换发件人。  
  
4.  选择**使用点 （.） 作为小数分隔符**若要启用 BizTalk Server 包括句点 （.） 中包含的小数的交换创建的 XML 消息。  
  
5.  有关**目标 Namespace**、 输入 （或从下拉列表中选择） 的目标命名空间，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用来确定要处理收到的消息的架构  
  
6.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [为事务配置 EDIFACT 回退协议属性设置](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)