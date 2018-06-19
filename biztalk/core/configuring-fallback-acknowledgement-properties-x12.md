---
title: 配置回退确认属性 (X12) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce33f5dd-fbd5-448c-8ea3-05dd1467131a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 216961dea0bdf4a67c550fba8a599eff2d0c89ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232829"
---
# <a name="configuring-fallback-acknowledgement-properties-x12"></a>配置回退确认属性 (X 12)
在备选协议中，您可以指定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何生成确认，以响应从参与方接收的 X12 编码的交换，以及返回到参与方的确认类型。 本节提供有关如何执行上述操作的说明。  
  
> [!NOTE]
>  此处所述的确认属性同样适用于 HIPAA 确认。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-x12-ack-properties"></a>配置 X12 确认属性  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 回退设置**。  
  
2.  在**X12 回退设置**对话框中，在**X12 协议页**选项卡上，在**交换设置**部分中，单击**确认**.  
  
3.  选择**预期的 TA1**可向交换发件人返回技术 (TA1) 确认。  
  
4.  选择**997 预期**可向交换发件人返回功能 (997) 确认。  
  
5.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置 X12 回退协议属性交换处理](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)