---
title: 配置回退字符集和分隔符属性 (EDIFACT) |Microsoft 文档
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
ms.openlocfilehash: 0b517a98130f2d245d68083dc16c65865950800c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233893"
---
# <a name="configuring-fallback-charset-and-separator-properties-edifact"></a>配置回退字符集和分隔符属性 (EDIFACT)
在回滚协议中，您可以指定在为传出 EDIFACT 消息创建信封时 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用哪个字符集 (UNMA) 来验证参与方属性。 你还可以指定哪些分隔符和终止符 (UNB) 用于交换中的段。  
  
 在 UNA 段中，可定义 BizTalk Server 如何生成它将发送到方的 EDIFACT 编码交换 UNA 段。 UNA 段定义将用作 EDIFACT 编码的交换的分隔符和指示器的字符。 仅当该交换包含非标准的分隔符，请使用此段。  
  
 UNB 段中，你可以定义将用于的 EDIFACT 字符集。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-the-character-set-and-separators"></a>配置字符集和分隔符  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 回退设置**。  
  
2.  在**EDIFACT 回退设置**对话框中，在**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**Charset 和分隔符**。  
  
3.  在**语法 (UNB1)** 部分中，执行以下操作：  
  
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
 [为交换处理配置 EDIFACT 回退协议属性](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)