---
title: 配置回退本地主机 Settngs （X12 事务集设置） |Microsoft 文档
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
ms.openlocfilehash: 9fa9e1fcc8bf1764a16142d38058e14878341fdc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233389"
---
# <a name="configuring-fallback-local-host-settngs-x12-transaction-set-settings"></a>配置回退本地主机设置（X12-事务集设置）
为了处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 必须确定在处理和验证交换时需要使用的架构。 这包括确定与架构关联的目标命名空间和确定要使用的架构。 在备用协议的此页，指定备用目标命名空间。 如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]确定架构所述[协议解析、 架构发现和接收 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。  
  
> [!NOTE]
>  本主题还适用于与 HIPAA 相关的设置。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>要配置事务集的本地主机设置，请执行以下操作：  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 回退设置**。  
  
2.  在**X12 回退设置**对话框中，在**X12 协议页**选项卡上，在**事务设置设置**部分中，单击**本地主机设置**.  
  
3.  选择**转换隐式小数格式 Nn 以十进制数值**将使用格式 Nn 转换为 BizTalk Server 中的中间 XML 中的以 10 为基数的数字值指定的 EDI 数字转换。  
  
    > [!NOTE]
    >  在此转换后，中间 XML 可能无法通过长度验证。 这是因为十进制数值格式的数包含小数点，使其比 Nn 格式的数长一位。 你可以通过添加的值来解决此问题**1**到的最小/最大长度值。  
  
4.  选择**创建为尾随分隔符的空 XML 标记**能够包含的尾随分隔符的空 XML 标记交换发件人。  
  
5.  有关**目标 Namespace**、 输入 （或从下拉列表中选择） 的目标命名空间，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用来确定要处理收到的消息的架构。  
  
6.  单击**应用**接受所做的更改，或单击**确定**以输入和验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置 X12 事务的回退协议属性设置](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)