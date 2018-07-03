---
title: 配置回退字符集和分隔符属性 (X12) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 477f4952-6a4e-4e98-a37f-f6e1fe7db3d3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 019fdb4262d778ec8f6605b8f3daef1df7881232
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994534"
---
# <a name="configuring-fallback-charset-and-separator-properties-x12"></a>配置回退字符集和分隔符属性 (X12)
在备用协议中，您可以指定在为传出 X12 消息创建信封时 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用哪个字符集来验证参与方属性。 还可以指定为交换内部的分段使用哪些分隔符和终止符。  
  
> [!NOTE]
>  此处所述的设置同样适用于 HIPAA 交换。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-the-character-set-and-separators"></a>配置字符集和分隔符  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。  
  
2. 在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**交换设置**部分中，单击**字符集和分隔符**.  
  
3. 从**要使用的字符集**下拉列表中，选择 X12 字符集以用于验证为协议输入的属性。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 仅使用此设置来验证为相关协议属性输入的值。 在执行运行时处理时，接收管道或发送管道将忽略此字符集属性。  
  
4. 有关**数据元素**，输入一个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔复合数据元素包含两个或多个简单数据元素和不属于复合元素的简单数据元素。 选择**Char**字符数据元素或**Hex**十六进制数据元素。 当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。  
  
5. 有关**组件元素分隔符 (ISA16)**，输入一个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔复合数据元素中的简单数据元素。 选择**Char**字符数据元素或**Hex**十六进制数据元素。 当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。  
  
6. 有关**段终止符**，输入一个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于指示 EDI 段尾。 选择**Char**字符数据元素或**Hex**十六进制数据元素。 当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。  
  
7. 有关**后缀**，选择的字符的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用段标识符，这两个**None**， **CR** （回车符）、 **LF**（换行符），或**CR LF** （回车符/换行符）。 如果指定后缀，则段终止符数据元素可以为空。 如果段终止符留空，则必须指定后缀。 段终止符和后缀的组合可以采用以下任何形式：  
  
   -   段终止符  
  
   -   段终止符 + 回车符  
  
   -   段终止符 + 回车符/换行符  
  
   -   回车符  
  
   -   换行  
  
   -   回车符/换行符  
  
8. 如果负载数据包含还用作数据、 段或组件分隔符的字符，请检查**替换为在通过有效负载中的分隔符**并指定替换字符。 在生成出站 X12 消息时，负载数据中的分隔符的所有实例都将替换为指定字符。 选择**Char**字符数据元素或**Hex**十六进制数据元素。 当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。  
  
9. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为交换处理配置 X12 后备协议属性](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)