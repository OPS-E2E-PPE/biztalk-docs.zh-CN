---
title: "配置字符集和分隔符 (X12) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6249f2e1-70b0-4960-bbc4-0c3fefd26faa
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43e32c4d9a240c3302126fc403d64efd787ed54c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-charset-and-separators-x12"></a>配置字符集和分隔页(X12)
在合作伙伴协议中，你可以指定在为传出 X12 消息创建信封时 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用哪个字符集来验证参与方属性。 还可以指定为交换内部的分段使用哪些分隔符和终止符。  
  
> [!NOTE]
>  此处所述的设置同样适用于 HIPAA 交换。  
  
> [!IMPORTANT]
>  以下属性禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  -   **数据元素**  
> -   **组件元素分隔符 (ISA16)**  
> -   **段终止符**  
> -   **Suffix**  
> -   **将负载中的分隔符**  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-the-character-set-and-separators"></a>配置字符集和分隔符  
  
1.  创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**交换设置**部分中，单击**字符集和分隔符**。  
  
3.  从**字符将设置为使用**下拉列表中，选择 X12 字符集要用于验证你为协议输入的属性。  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 仅使用此设置来验证为相关协议属性输入的值。 在执行运行时处理时，接收管道或发送管道将忽略此字符集属性。  
  
4.  有关**数据元素**，输入单个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔两个或多个简单数据元素和不属于复合元素的简单数据元素组成的复合数据元素。 选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。 在更改中的格式时，您输入的字符将自动更改**Char**到**十六进制**，反之亦然。  
  
5.  有关**组件元素分隔符 (ISA16)**，输入单个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔复合数据元素中的简单数据元素。 选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。 在更改中的格式时，您输入的字符将自动更改**Char**到**十六进制**，反之亦然。  
  
6.  有关**段终止符**，输入单个字符，用于指示 EDI 段尾。 选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。  
  
     如果类型为**Char**，默认值是 **~** 。  
  
     如果类型为**十六进制**，默认值是**7E**。  
  
     此数据元素是必需的。  
  
     此元素仅限于 ASCII 字符集中的值。 不会根据“常规”页中定义的 X12 字符集对此属性进行验证。  
  
     在更改中的格式时，您输入的字符将自动更改**Char**到**十六进制**，反之亦然。  
  
7.  有关**后缀**，选择要使用的字符**与**段终止符值。 选项包括：  
  
    -   **无**： 默认  
  
    -   **CR**： 回车符  
  
    -   **LF**： 换行符  
  
    -   **CR LF**： 回车符/换行符源  
  
     “段终止符”和“后缀”组合包括：  
  
    -   **任何**段终止符 +**无**后缀  
  
    -   **任何**段终止符 + **CR**后缀  
  
    -   **任何**段终止符 + **CR LF**后缀  
  
    -   **D （十六进制）**段终止符 +**无**后缀： 这种组合的行为方式好像段终止符为空白，并设置为 CR 的后缀。  
  
    -   （十六进制） 段终止符 +**无**后缀： 这种组合的行为方式好像段终止符保留为空并且后缀设置为 LF。  
  
    -   **D （十六进制）**段终止符 + **LF**后缀： 这种组合的行为方式好像段终止符是 CR，后缀设置为 LF。  
  
8.  如果负载数据中的字符也用作数据、 段或组件分隔符，请检查**替换负载中的分隔符**并指定替换字符。 在生成出站 X12 消息时，负载数据中的分隔符的所有实例都将替换为指定字符。 选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。 在更改中的格式时，您输入的字符将自动更改**Char**到**十六进制**，反之亦然。  
  
9. 单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md)