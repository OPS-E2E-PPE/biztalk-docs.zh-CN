---
title: "配置回退信封属性 （EDIFACT 事务集设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b56a5a93-35ac-4293-b00e-28dcd89dfa2a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c93f9aae6d67e5dc56d383626e36d1db412be9d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-envelope-properties-edifact-transaction-set-settings"></a>配置回退信封属性（EDIFACT-事务集设置）
在**包络线**页**事务设置设置**部分中，你定义 BizTalk Server 如何生成它将发送到方的 EDIFACT 编码交换 UNG 段。  
  
 UNG 段是用来标识和指定 EDIFACT 编码交换的功能组的标头。 它包含有关准备功能组的日期和时间以及功能组中文档的类型和版本的信息。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-define-the-ung-segments"></a>定义 UNG 段  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 回退设置**。  
  
2.  在**EDIFACT 回退设置**对话框中，在**EDIFACT 协议页**选项卡上，在**事务设置设置**部分中，单击**包络线**.  
  
3.  有关**功能组 ID (UNG1)**，输入一个字母数字值，该值最少包含一个字符，最多六个字符。 这是必填字段。  
  
4.  输入值以标识**应用程序发件人 (UNG2)**。  
  
    -   有关**标识 (UNG2.1)**，输入一个字母数字值，该值最少包含一个字符，最多 35 个字符。 这是必填字段。  
  
    -   有关**代码限定符 (UNG2.2)**，输入一个字母数字值，该值最少包含一个字符，最多四个字符。 此字段为可选字段。  
  
5.  输入值以标识**应用程序接收方 (UNG3)**。  
  
    -   有关**标识 (UNG3.1)**，输入一个字母数字值，该值最少包含一个字符，最多 35 个字符。 这是必填字段。  
  
    -   有关**代码限定符 (UNG3.2)**，输入一个字母数字值，该值最少包含一个字符，最多四个字符。 此字段为可选字段。  
  
6.  有关**控制代理 (UNG6)**，输入最少包含一个字符，最多两个字符的一个字母数字值。 这是必填字段。  
  
7.  输入值以标识**消息版本 (UNG7)**。  
  
    -   有关**版本 (UNG7.1)**，输入一个字母数字值，该值最少包含一个字符，最多三个字符。 这是必填字段。  
  
    -   有关**发行版 (UNG7.2)**，输入一个字母数字值，该值最少包含一个字符，最多三个字符。 这是必填字段。  
  
    -   有关**关联分配的代码 (UNG7.3)**，输入一个字母数字值，该值最少包含 1 个字符，最多 6 个字符。 此字段为可选字段。  
  
8.  有关**应用程序密码 (UNG8)**，输入一个字母数字值，该值最少包含一个字符，最多包含 14 个字符。 这是必填字段。  
  
9. 单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [为事务配置 EDIFACT 回退协议属性设置](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)