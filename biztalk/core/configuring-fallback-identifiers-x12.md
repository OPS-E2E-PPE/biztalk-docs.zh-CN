---
title: 配置回退标识符 (X12) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cb5b32c-96ec-4192-9a10-6668a2cb1195
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cced4cbb22be0f486542f092946462906bd674df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998222"
---
# <a name="configuring-fallback-identifiers-x12"></a>配置回退标识符(X12)
在后备协议中，必须设置 X12 授权和安全属性，以确认交换不会被未经授权的收件人接收。  
  
> [!NOTE]
>  此处所述的交换处理属性也适用于 HIPAA 交换。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-set-sender-receiver-and-security-properties"></a>设置发送方、接收方和安全属性  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。  
  
2. 在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**交换设置**部分中，单击**标识符**.  
  
3. 输入值**ISA1-2 （授权限定符和信息）**。 选择的值**授权限定符 (ISA1)** 从关联的下拉列表。 如果此值不是**00**，对于**值 (ISA2)** 文字框中，输入一个字母数字字符的最小值和最多 10 个。 此字段为可选字段。 如果您确实要指定这些值，请确保它们与接收的交换中的 ISA1 和 ISA2 字段相匹配，否则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将挂起交换。  
  
4. 输入值**ISA3-4 （安全限定符和信息）**。 选择的值**安全限定符 (ISA3)** 从下拉列表。 如果此值不是**00**，对于**值 (ISA4)** 文字框中，输入一个字母数字值的最小值和最多 10 个。 此字段为可选字段。 如果这些值与所接收交换中的 ISA3 和 ISA4 字段不匹配，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将挂起该交换。  
  
   > [!NOTE]
   >  值**03 – 密码 （用于向后兼容性）**，是为了向后兼容包含[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]和将在未来版本中删除。  
  
5. 输入的值**ISA5-6 （发送方限定符和标识符）**。 选择从限定符的值**发件人 Id 限定符 (ISA5)** 下拉列表。 对于标识符，在**值 (ISA6)** 文字框中，输入最少一个字母数字字符、 最多包含 15 个字符。  
  
6. 输入的值**ISA7-8 （接收方限定符和标识符）**。 选择从限定符的值**接收方 Id 限定符 (ISA7)** 下拉列表。 对于标识符，在**值 (ISA8)** 文字框中，输入最少一个字母数字字符、 最多包含 15 个字符。  
  
7. 单击**Apply**以接受更改，或单击**确定**以输入和验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为交换处理配置 X12 后备协议属性](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)