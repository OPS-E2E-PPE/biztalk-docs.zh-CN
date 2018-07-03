---
title: 配置信封 （EDIFACT-交换设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501ccc5f-e21c-4c36-9509-217d5b3ba21f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80957d82a70b0fca8a11ace428f87496b45dcb31
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993590"
---
# <a name="configuring-envelopes-edifact-interchange-settings"></a>配置信封（EDIFACT-交换设置）
本节提供有关如何配置 EDIFACT 待发邮件的信封的说明。  
  
> [!IMPORTANT]
>  如果你清除了所有属性会都禁用此页上**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-the-interchange-envelope"></a>配置交换信封  
  
1. 创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2. 在单向协议选项卡下**交换设置**部分中，单击**信封**。  
  
3. 有关**处理优先级代码 (UNB8)**，输入最少一个字符，最多为 1 个字符的字母数字值。 此字段为可选字段。  
  
4. 有关**通信协议 (UNB10)**，输入包含最少一个字符，最多为 35 个字符的字母数字值。 此字段为可选字段  
  
5. 选择**测试指示器 (UNB11)** 以指示由生成的交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是测试数据。  
  
6. 选择**应用 UNA 段 （字符串服务建议）** 生成要发送交换的 UNA 段。 如果选中此选项，然后**UNA6**不能为空并**UNA 6 后缀**不能为**None**。  
  
   > [!NOTE]
   >  您指定**UNA6**并**UNA6 后缀**中**字符集和分隔符**页中所述[配置字符集和分隔符 (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).  
  
7. 选择**应用 UNG 段 （功能组标头）** 在传出消息的功能组标头中创建分组段。  
  
8. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)