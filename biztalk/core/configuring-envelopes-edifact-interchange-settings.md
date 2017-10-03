---
title: "配置信封 （EDIFACT 交换设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 501ccc5f-e21c-4c36-9509-217d5b3ba21f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 531b559e690fae5369298a90cd372edcae79db57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-envelopes-edifact-interchange-settings"></a>配置信封（EDIFACT-交换设置）
本节提供有关如何配置 EDIFACT 待发邮件的信封的说明。  
  
> [!IMPORTANT]
>  如果你清除了所有属性会被都禁用此页上**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-the-interchange-envelope"></a>配置交换信封  
  
1.  创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**交换设置**部分中，单击**包络线**。  
  
3.  有关**处理优先级代码 (UNB8)**，输入最少包含一个字符，最多一个字符的字母值。 此字段为可选字段。  
  
4.  有关**通信协议 (UNB10)**，输入一个字母数字值，该值最少包含一个字符，最多 35 个字符。 此字段为可选字段  
  
5.  选择**测试指示器 (UNB11)**以指示该交换生成的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是测试数据。  
  
6.  选择**应用 UNA 段 （字符串服务建议）**生成 UNA 段为要发送的交换。 如果选中此选项，然后**UNA6**不能为空和**UNA 6 后缀**不能为**无**。  
  
    > [!NOTE]
    >  你指定**UNA6**和**UNA6 后缀**中**字符集和分隔符**页中所述[配置字符集和分隔符 (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).  
  
7.  选择**应用 UNG 段 （功能组标头）**创建分组段的功能组标头中传出消息。  
  
8.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)