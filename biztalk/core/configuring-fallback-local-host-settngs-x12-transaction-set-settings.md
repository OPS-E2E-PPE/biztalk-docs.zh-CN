---
title: 配置回退本地主机设置 （X12-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68511199-a7ed-45b3-807d-70378b2c6ebb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eb13da3e0bc9e0c3ee676a8bf01d484a4201a80
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979022"
---
# <a name="configuring-fallback-local-host-settngs-x12-transaction-set-settings"></a>配置回退本地主机设置（X12-事务集设置）
为了处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 必须确定在处理和验证交换时需要使用的架构。 这包括确定与架构关联的目标命名空间和确定要使用的架构。 在备用协议的此页，指定备用目标命名空间。 如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]确定架构中，请参阅[协议解析、 架构发现和收到的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。  
  
> [!NOTE]
>  本主题还适用于与 HIPAA 相关的设置。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>要配置事务集的本地主机设置，请执行以下操作：  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。  
  
2. 在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**事务集设置**部分中，单击**本地主机设置**.  
  
3. 选择**将隐式小数格式 Nn 十进制数值**若要使用的中间 XML 中 BizTalk Server 的十进制数字值格式 Nn 指定的 EDI 数值转换。  
  
   > [!NOTE]
   >  在此转换后，中间 XML 可能无法通过长度验证。 这是因为十进制数值格式的数包含小数点，使其比 Nn 格式的数长一位。 可以通过添加的值来解决此问题**1**为最小/最大长度值。  
  
4. 选择**创建为尾部分隔符的空 XML 标记**以使交换发送方包含为尾部分隔符的空 XML 标记。  
  
5. 有关**目标 Namespace**，输入 （或从下拉列表中选择） 的目标命名空间的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用来确定处理接收的消息的架构。  
  
6. 单击**Apply**以接受更改，或单击**确定**以输入和验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为事务集设置配置 X12 后备协议属性](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)