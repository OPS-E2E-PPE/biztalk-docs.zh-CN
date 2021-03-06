---
title: 配置字符集和分隔符 (X12) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6249f2e1-70b0-4960-bbc4-0c3fefd26faa
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 108c539ec93d997410062dcaf4737cb4f213f911
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356145"
---
# <a name="configuring-charset-and-separators-x12"></a>配置字符集和分隔页(X12)
在合作伙伴协议中，您可以指定的字符集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于验证参与方属性创建为传出 x12 信封时消息。 此外可以指定将交换中的分段使用哪些分隔符和终止符。  
  
> [!NOTE]
>  此处所述的设置也适用于 HIPAA 交换。  
> 
> [!IMPORTANT]
>  以下属性禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
> 
> - **数据元素**  
>   -   **组件元素分隔符 (ISA16)**  
>   -   **段终止符**  
>   -   **Suffix**  
>   -   **替换负载中的分隔符**  
> 
>   仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-the-character-set-and-separators"></a>若要配置字符集和分隔符  
  
1. 创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2. 在单向协议选项卡下**交换设置**部分中，单击**字符集和分隔符**。  
  
3. 从**要使用的字符集**下拉列表中，选择 X12 字符集以用于验证为协议输入的属性。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 仅使用此设置验证为相关的协议属性输入的值。 执行运行时处理时，接收管道或发送管道将忽略此字符集属性。  
  
4. 有关**数据元素**，输入一个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔复合数据元素包含两个或多个简单数据元素和不属于复合元素的简单数据元素。 选择**Char**字符数据元素或**Hex**十六进制数据元素。 当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。  
  
5. 有关**组件元素分隔符 (ISA16)** ，输入一个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔复合数据元素中的简单数据元素。 选择**Char**字符数据元素或**Hex**十六进制数据元素。 当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。  
  
6. 有关**段终止符**，输入单个字符，用于指示 EDI 段尾。 选择**Char**字符数据元素或**Hex**十六进制数据元素。  
  
    如果类型为**Char**，默认值是 **~** 。  
  
    如果类型为**十六进制**，默认值是**7E**。  
  
    此数据元素是必需的。  
  
    此元素仅限于 ASCII 字符集中的值。 根据 X12 不验证此属性在常规页中定义的字符集。  
  
    当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。  
  
7. 有关**后缀**，选择要使用的字符**与**段终止符值。 选项包括：  
  
   - **无**：默认  
  
   - **CR**:回车  
  
   - **LF**:换行  
  
   - **CR LF**:回车符/换行符源  
  
     段终止符和后缀组合包括：  
  
   - **任何**段终止符 + **None**后缀  
  
   - **任何**段终止符 + **CR**后缀  
  
   - **任何**段终止符 + **CR LF**后缀  
  
   - **D （十六进制）** 段终止符 + **None**后缀：此组合行为就像段终止符为空且后缀设置为 CR。  
  
   - （十六进制） 段终止符 + **None**后缀：此组合行为就像段终止符为空且后缀设置为 LF。  
  
   - **D （十六进制）** 段终止符 + **LF**后缀：此组合行为就像段终止符为 CR 且后缀设置为 LF。  
  
8. 如果负载数据包含还用作数据、 段或组件分隔符的字符，请检查**替换为在通过有效负载中的分隔符**并指定替换字符。 生成出站 X12 消息时，数据将替换为指定的字符的有效负载中分隔符的所有实例。 选择**Char**字符数据元素或**Hex**十六进制数据元素。 当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。  
  
9. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md)