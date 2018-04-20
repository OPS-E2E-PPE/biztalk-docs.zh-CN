---
title: 配置回退信封属性 (EDIFACT 交换 Settngs) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8826041e-02fa-4086-a774-d44a388f42b1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6a141b852f85947165d3d3d4d638cf1cb10ccb0
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="configuring-fallback-envelope-properties-edifact-interchange-settngs"></a>配置回退信封属性（EDIFACT-交换设置）
本节提供有关如何配置 EDIFACT 待发邮件的信封的说明。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-the-interchange-envelope"></a>配置交换信封  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 回退设置**。  
  
2.  在 **EDIFACT 回退设置** 对话框中，在 **EDIFACT 协议页** 选项卡上，在 **交换设置** 部分中，单击 **包络线**。  
  
3.  有关 **处理优先级代码 (UNB8)**, ，输入最少包含一个字符，最多一个字符的字母值。 此字段为可选字段。  
  
4.  有关 **通信协议 (UNB10)**, ，输入一个字母数字值，该值最少包含一个字符，最多 35 个字符。 此字段为可选字段  
  
5.  选择**测试指示器 (UNB11)**以指示该交换生成的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是测试数据。  
  
6.  选择 **应用 UNA 段 （字符串服务建议）** 生成 UNA 段为要发送的交换。 如果选中此选项，然后 **UNA6** 不能为空和 **UNA 6 后缀** 不能为 **无**。  
  
    > [!NOTE]
    >  你指定**UNA6**和**UNA6 后缀**中**字符集和分隔符**页中所述[配置回退字符集和分隔符属性 (EDIFACT)](../core/configuring-fallback-charset-and-separator-properties-edifact.md)。  
  
7.  选择 **应用 UNG 段 （功能组标头）** 创建分组段的功能组标头中传出消息。  
  
8.  单击 **应用** 接受所做的更改，然后才能继续进行配置，或单击 **确定** 验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [为交换处理配置 EDIFACT 后备协议属性](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)