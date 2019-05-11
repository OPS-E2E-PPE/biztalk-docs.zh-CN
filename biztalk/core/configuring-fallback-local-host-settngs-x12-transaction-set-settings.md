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
ms.openlocfilehash: f3eb3ed007a30e2d65c4d65aebe98ebabf2f93c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391213"
---
# <a name="configuring-fallback-local-host-settngs-x12-transaction-set-settings"></a>配置回退本地主机设置（X12-事务集设置）
若要处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须确定它需要使用在处理和验证交换的架构。 这包括确定与架构相关联的目标命名空间并确定要使用的架构。 在备用协议的此页上，指定备用目标命名空间。 如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]确定架构中，请参阅[协议解析、 架构发现和收到的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。  
  
> [!NOTE]
>  本主题还适用于与 HIPAA 相关的设置。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>若要配置本地主机设置为事务集  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。  
  
2. 在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**事务集设置**部分中，单击**本地主机设置**.  
  
3. 选择**将隐式小数格式 Nn 十进制数值**若要使用的中间 XML 中 BizTalk Server 的十进制数字值格式 Nn 指定的 EDI 数值转换。  
  
   > [!NOTE]
   >  在此转换后的中间 XML 可能无法通过长度验证。 这是因为采用以 10 为基数的数字格式的数字包含小数点，使其长度超过一个以 Nn 格式。 可以通过添加的值来解决此问题**1**为最小/最大长度值。  
  
4. 选择**创建为尾部分隔符的空 XML 标记**以使交换发送方包含为尾部分隔符的空 XML 标记。  
  
5. 有关**目标 Namespace**，输入 （或从下拉列表中选择） 的目标命名空间的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用来确定处理接收的消息的架构。  
  
6. 单击**Apply**以接受更改，或单击**确定**以输入和验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为事务集设置配置 X12 后备协议属性](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)