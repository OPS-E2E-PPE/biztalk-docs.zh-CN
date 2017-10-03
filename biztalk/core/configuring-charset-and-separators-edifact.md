---
title: "配置字符集和分隔符 (EDIFACT) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4764938-0968-4536-9eb6-d600c03a0428
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7089cde27eeb45f41852c00122272f506632e61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-charset-and-separators-edifact"></a>配置字符集和分隔页(EDIFACT)
在合作伙伴协议中，您可以指定在为传出 EDIFACT 消息创建信封时 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用哪个字符集 (UNA) 来验证参与方属性。 你还可以指定哪些分隔符和终止符 (UNB) 用于交换中的段。  
  
 在 UNA 段中，可定义 BizTalk Server 如何生成它将发送到方的 EDIFACT 编码交换 UNA 段。 UNA 段定义将用作 EDIFACT 编码的交换的分隔符和指示器的字符。 仅当该交换包含非标准的分隔符，请使用此段。  
  
 UNB 段中，你可以定义将用于的 EDIFACT 字符集。  
  
> [!IMPORTANT]
>  如果你清除了所有属性会被都禁用此页上**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-the-character-set-and-separators"></a>配置字符集和分隔符  
  
1.  创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**交换设置**部分中，单击**字符集和分隔符**。  
  
3.  在**语法 (UNB1)**部分中，执行以下操作：  
  
    1.  有关**标识符 (UNB1.1)**，输入将应用到传出交换的 EDIFACT 字符集。 这是必填字段。  
  
    2.  有关**版本 (UNB1.2)**，选择一个介于**1**和**4**。 此字段为可选字段。  
  
4.  在**分隔符**部分中，执行以下操作：  
  
    1.  有关**组件数据元素分隔符 (UNA1)**，输入组件数据元素分隔符用于分隔复合数据元素中的简单数据元素的值。 选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。 如果你更改其格式，将自动更改您输入的字符。  
  
    2.  有关**数据元素分隔符 (UNA2)**，输入数据元素分隔符用于分隔复合数据元素组成两个或多个简单数据元素或不是复合的一部分的简单数据元素的值。 选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。 如果你更改其格式，将自动更改您输入的字符。  
  
    3.  有关**十进制表示法 (UNA3)**，选择要在传出交换中使用的十进制表示法。  
  
    4.  有关**转义指示器 (UNA4)**，指示以下字符不是语法分隔符、 终止符或转义符，而是原始数据的一部分转义指示器输入的值。 选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。 如果你更改其格式，将自动更改您输入的字符。  
  
    5.  有关**重复分隔符 (UNA5)**，输入值的重复分隔符用于分隔事务集内的重复的段。 选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。 如果你更改其格式，将自动更改您输入的字符。  
  
    6.  有关**段终止符 (UNA6)**，为用于指示 EDI 段尾的段终止符输入一个值。  
  
    7.  有关**UNA6 后缀**，选择 BizTalk Server 将使用与段标识符，或者字符**无**， **CR** （回车符）， **LF**（换行符），或**CR LF** （回车符/换行符）。 如果指定后缀，则段终止符数据元素可以为空。 如果段终止符留空，则必须指定后缀。 段终止符和后缀的组合可以采用以下任何形式：  
  
        -   段终止符  
  
        -   段终止符 + 回车符  
  
        -   段终止符 + 回车符/换行符  
  
        -   回车符  
  
        -   换行符  
  
        -   回车符/换行符  
  
5.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**若要验证并接受所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)