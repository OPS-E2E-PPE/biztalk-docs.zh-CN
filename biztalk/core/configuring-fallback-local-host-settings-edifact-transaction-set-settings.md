---
title: 配置回退本地主机设置 （EDIFACT-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0142b3fc-009f-4da5-b34d-dddf4fb96e0f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: caeb6c0f56a051d43596dd541a2172ff7eda2de4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391210"
---
# <a name="configuring-fallback-local-host-settings-edifact-transaction-set-settings"></a>配置回退本地主机设置（EDIFACT-事务集设置）
若要处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须确定它需要使用在处理和验证交换的架构。 这包括确定与架构相关联的目标命名空间并确定要使用的架构。 在后备协议的此页上，输入要在确定目标命名空间时使用的属性。 BizTalk Server 如何确定架构中所述[协议解析、 架构发现和收到的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>若要配置本地主机设置为事务集  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 后备设置**。  
  
2. 在中**EDIFACT 后备设置**对话框中**EDIFACT 协议页**选项卡上，在**事务集设置**部分中，单击**本地主机设置**。  
  
3. 选择**创建为尾部分隔符的空 XML 标记**以使交换发送方包含为尾部分隔符的空 XML 标记。  
  
4. 选择**使用点 （.） 作为小数分隔符**启用 BizTalk Server 中包含点 （.） 包含十进制数的交换外创建的 XML 消息。  
  
5. 有关**目标 Namespace**，输入 （或从下拉列表中选择） 的目标命名空间的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于确定处理接收的消息的架构  
  
6. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为事务集设置配置 EDIFACT 后备协议属性](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)