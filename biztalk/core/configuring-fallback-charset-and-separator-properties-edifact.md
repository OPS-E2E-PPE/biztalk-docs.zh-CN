---
title: 配置回退字符集和分隔符属性 (EDIFACT) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9eadc9c1-ebec-42f5-a9ca-06cb28bebcdf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8d36df63d1bcad0ebd39bd828a1a9407e6cc480
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977102"
---
# <a name="configuring-fallback-charset-and-separator-properties-edifact"></a>配置回退字符集和分隔符属性 (EDIFACT)
在回滚协议中，您可以指定在为传出 EDIFACT 消息创建信封时 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用哪个字符集 (UNMA) 来验证参与方属性。 此外可以指定将交换中的分段使用哪些分隔符和终止符 (UNB)。  
  
 在 UNA 段中，可以定义 BizTalk Server 如何生成它发送到参与方的 EDIFACT 编码交换的 UNA 段。 UNA 段定义将用作 EDIFACT 编码的交换的分隔符和指示器的字符。 使用此段，仅当该交换包含非标准分隔符字符。  
  
 在 UNB 段定义将设置为使用的 EDIFACT 字符集。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-the-character-set-and-separators"></a>配置字符集和分隔符  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 后备设置**。  
  
2. 在中**EDIFACT 后备设置**对话框中**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**字符集和分隔符**。  
  
3. 在中**语法 (UNB1)** 部分中，执行以下操作：  
  
   1.  有关**标识符 (UNB1.1)**，为要应用于传出交换的 EDIFACT 字符集输入。 这是必填字段。  
  
   2.  有关**版本 (UNB1.2)**，选择介于**1**并**4**。 此字段为可选字段。  
  
4. 在中**分隔符**部分中，执行以下操作：  
  
   1.  有关**组件数据元素分隔符 (UNA1)**，输入组件数据元素分隔符用于分隔复合数据元素中的简单数据元素的值。 选择**Char**字符数据元素或**Hex**十六进制数据元素。 如果更改其格式，你输入的字符将自动更改。  
  
   2.  有关**数据元素分隔符 (UNA2)**，分隔复合数据元素包含两个或多个简单数据元素或简单数据元素不属于复合数据元素分隔符输入一个值。 选择**Char**字符数据元素或**Hex**十六进制数据元素。 如果更改其格式，你输入的字符将自动更改。  
  
   3.  有关**十进制符号 (UNA3)**，选择要在传出交换中使用的十进制表示法。  
  
   4.  有关**转义指示器 (UNA4)**，输入转义指示器用于指示后面的字符不是语法分隔符、 终止符或转义符，而是原始数据的一部分的值。 选择**Char**字符数据元素或**Hex**十六进制数据元素。 如果更改其格式，你输入的字符将自动更改。  
  
   5.  有关**重复分隔符 (UNA5)**，为此重复分隔符用于分隔事务集内的重复的段输入一个值。 选择**Char**字符数据元素或**Hex**十六进制数据元素。 如果更改其格式，你输入的字符将自动更改。  
  
   6.  有关**段终止符 (UNA6)**，用于指示 EDI 段尾段终止符输入的值。  
  
   7.  有关**UNA6 后缀**，选择 BizTalk Server 将与段标识符，或者使用的字符**None**， **CR** （回车符）、 **LF**（换行符），或**CR LF** （回车符/换行符）。 如果指定后缀，则段终止符数据元素可以为空。 如果段终止符留空，则必须指定后缀。 段终止符和后缀的组合可以采用以下任何形式：  
  
       -   段终止符  
  
       -   段终止符 + 回车符  
  
       -   段终止符 + 回车符/换行符  
  
       -   回车符  
  
       -   换行  
  
       -   回车符/换行符  
  
5. 单击**Apply**接受所做的更改，然后才能继续进行配置，或单击**确定**以验证并接受所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为交换处理配置 EDIFACT 后备协议属性](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)