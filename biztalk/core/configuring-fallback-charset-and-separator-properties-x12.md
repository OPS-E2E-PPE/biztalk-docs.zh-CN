---
title: "配置回退字符集和分隔符属性 (X12) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 477f4952-6a4e-4e98-a37f-f6e1fe7db3d3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 633ea22c611eb0fab994fd62250b9cb9ff8a0f2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-charset-and-separator-properties-x12"></a>配置回退字符集和分隔符属性 (X12)
在备用协议中，您可以指定在为传出 X12 消息创建信封时 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用哪个字符集来验证参与方属性。 还可以指定为交换内部的分段使用哪些分隔符和终止符。  
  
> [!NOTE]
>  此处所述的设置同样适用于 HIPAA 交换。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-the-character-set-and-separators"></a>配置字符集和分隔符  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 回退设置**。  
  
2.  在**X12 回退设置**对话框中，在**X12 协议页**选项卡上，在**交换设置**部分中，单击**字符集和分隔符**.  
  
3.  从**字符将设置为使用**下拉列表中，选择 X12 字符集要用于验证你为协议输入的属性。  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 仅使用此设置来验证为相关协议属性输入的值。 在执行运行时处理时，接收管道或发送管道将忽略此字符集属性。  
  
4.  有关**数据元素**，输入单个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔两个或多个简单数据元素和不属于复合元素的简单数据元素组成的复合数据元素。 选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。 在更改中的格式时，您输入的字符将自动更改**Char**到**十六进制**，反之亦然。  
  
5.  有关**组件元素分隔符 (ISA16)**，输入单个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔复合数据元素中的简单数据元素。 选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。 在更改中的格式时，您输入的字符将自动更改**Char**到**十六进制**，反之亦然。  
  
6.  有关**段终止符**，输入单个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要用来指示 EDI 段尾。 选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。 在更改中的格式时，您输入的字符将自动更改**Char**到**十六进制**，反之亦然。  
  
7.  有关**后缀**，选择的字符，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用与段标识符中，这两个**无**， **CR** （回车符）， **LF**（换行符），或**CR LF** （回车符/换行符）。 如果指定后缀，则段终止符数据元素可以为空。 如果段终止符留空，则必须指定后缀。 段终止符和后缀的组合可以采用以下任何形式：  
  
    -   段终止符  
  
    -   段终止符 + 回车符  
  
    -   段终止符 + 回车符/换行符  
  
    -   回车符  
  
    -   换行符  
  
    -   回车符/换行符  
  
8.  如果负载数据中的字符也用作数据、 段或组件分隔符，请检查**替换负载中的分隔符**并指定替换字符。 在生成出站 X12 消息时，负载数据中的分隔符的所有实例都将替换为指定字符。 选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。 在更改中的格式时，您输入的字符将自动更改**Char**到**十六进制**，反之亦然。  
  
9. 单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置 X12 回退协议属性交换处理](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)