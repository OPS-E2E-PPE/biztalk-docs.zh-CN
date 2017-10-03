---
title: "配置回退本地主机设置 （EDIFACT 交换设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eecf5abb-9c12-44b0-bc58-94cb138515c3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dc98c62870632501c5b5330ed72ad5aee971fdd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-local-host-settings-edifact-interchange-settings"></a>配置回退本地主机设置（EDIFACT-交换设置）
本地主机设置控制如何处理 EDI 交换。 此页上的设置可以分为两个类别：接收方设置（用于传入交换）和发送方设置（用于传出交换）。 作为接收方设置的一部分，您可以指定将要生成确认控制编号的方式。 作为发送方设置的一部分，可以指定为传出消息生成控制编号的方式。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-local-host--receivers-settings"></a>配置本地主机 – 接收方设置  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 回退设置**。  
  
2.  在**EDIFACT 回退设置**对话框中，在**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**本地主机设置**。  
  
3.  在**EDIFACT ACK**部分中，指定事务集引用编号，以确认中, 使用输入的值的前缀、 引用编号和后缀的范围。  
  
     单击**重置**重置当前事务集引用编号为下限。 选择**重置为下限超出界限时**能够[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将引用编号重置为较低范围值限制，如果超出最大限制。  
  
### <a name="to-configure-local-host--senders-settings"></a>配置本地主机 – 发送方设置  
  
1.  有关**交换控制编号 (UNB5)**，输入的用于 BizTalk Server 中生成传出交换的交换控制编号的值的范围。 输入一个最小为 1、最大为 999999999 的数值。 此字段是必需字段。  
  
    > [!NOTE]
    >  第一个字段 (**UNB5.1**) 是前缀; 第二个和第三个字段 (**UNB5.2**) 包含要用作交换控制编号; 和第四个字段的数字范围 (**UNB5.3**)是的后缀。 前缀和后缀是可选的；控制编号是必需的。 每条新消息的控制编号是递增的；前缀和后缀保持不变。 控制编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。  
    >   
    >  若要将控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限超出界限时**自动重置的最小值如果超出最大值。  
  
2.  有关**组控制编号 (UNG5)**、 输入前缀、 引用编号范围，以及 BizTalk Server 应该用于发送第一个交换组控制编号的后缀。  
  
    > [!NOTE]
    >  第一个字段 (**UNG5.1**) 是前缀; 第二个和第三个字段 (**UNG5.2**) 包含要用于组控制编号; 和第四个字段的数字范围 (**UNG5.3**) 是的后缀。 前缀和后缀是可选的；控制编号是必需的。 每条新消息的控制编号是递增的直到达到最大值；前缀和后缀保持不变。 数字可以用在**UNG5.2**。 控制编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。  
    >   
    >  若要将组控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限超出界限时**自动重置的最小值如果超出最大值。  
  
3.  有关**消息标头 （新罕布什尔大学）**，单击**应用新的 ID**、 输入前缀、 引用编号范围中，输入和输入 BizTalk 服务器应使用为事务集引用编号的后缀。  
  
    > [!NOTE]
    >  第一个字段 (**UNH1.1**) 是前缀; 第二个和第三个字段 (**UNH1.2**) 是引用编号范围; 和第四个字段 (**UNH1.3**) 是的后缀。 前缀和后缀是可选的；参考编号是必需的。 每条新消息的参考编号是递增的；前缀和后缀保持不变。 参考编号的默认值范围是 1 到 99999999999999。 数字可以用在**UNH1.2**。 控制编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。  
    >   
    >  若要重置当前事务集控制编号的最小值，请单击**重置**。 选择**重置为下限超出界限时**来将控制编号重置的最小值为，如果尚未超过最大值。  
  
4.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [为交换处理配置 EDIFACT 回退协议属性](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)