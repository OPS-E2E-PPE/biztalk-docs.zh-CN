---
title: 配置信封 （X12 交换设置） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4fade73-14cf-475c-81b5-6102c75db991
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf4f88ee1e5d786367c1a4bc0f5b2404fd5c1a37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233413"
---
# <a name="configuring-envelopes-x12-interchange-settings"></a>配置信封（X 12 交换设置）
X12 交换信封生成设置定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何生成要发送到接收方的 X12 编码交换的信封。 在本部分中，您可以定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何为它发送到参与方的 X12 编码的交换生成 ISA 段。 ISA 段是 X12 编码的交换的交换控制标头。  
  
> [!NOTE]
>  对于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时，字母数字 ISA 字段的长度是固定的。 但是，对于[!INCLUDE[TPM](../includes/tpm-md.md)]用户界面，您可以为字母数字的 ISA 字段输入单个字符。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将填充尾随空格字符，以确保符合标准要求使用这些字段。  
  
> [!NOTE]
>  此处介绍的设置还适用于 HIPAA 交换信封生成。  
  
> [!IMPORTANT]
>  如果你清除了所有属性会被都禁用此页上**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-define-the-envelope"></a>定义信封  
  
1.  创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**交换设置**部分中，单击**包络线**。  
  
3.  下**ISA11 用法**，保留**标准标识符**选择用来指定标准标识符而不是重复分隔符，，然后从下拉列表中选择标准标识符的值。 选择**重复分隔符**若要指定重复分隔符而不是一个标准的标识符，然后的重复分隔符输入单个字符。 用于分隔在事务集内重复的段的重复分隔符仅限于 ASCII 字符集中的值。  
  
4.  有关**控制版本号 (ISA12)**，选择的 x12 标准要使用的版本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于生成传出交换。  
  
5.  有关**用法指示符 (ISA15)**，选择以指示是否由生成将交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是信息、 生产数据还是测试数据。  
  
6.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md)