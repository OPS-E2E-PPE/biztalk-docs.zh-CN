---
title: 配置回退本地主机设置 （EDIFACT-交换设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eecf5abb-9c12-44b0-bc58-94cb138515c3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a503a54e712026295c5df295e7ed6d8e2408a9a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001838"
---
# <a name="configuring-fallback-local-host-settings-edifact-interchange-settings"></a>配置回退本地主机设置（EDIFACT-交换设置）
本地主机设置控制如何处理 EDI 交换。 此页上的设置可以分为两个类别：接收方设置（用于传入交换）和发送方设置（用于传出交换）。 作为接收方设置的一部分，您可以指定将要生成确认控制编号的方式。 作为发送方设置的一部分，可以指定为传出消息生成控制编号的方式。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-local-host--receivers-settings"></a>配置本地主机 – 接收方设置  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 后备设置**。  
  
2. 在中**EDIFACT 后备设置**对话框中**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**本地主机设置**。  
  
3. 在中**EDIFACT 确认**部分，若要指定要在确认中使用的事务集参考编号的前缀、 参考编号和后缀的范围输入一个值。  
  
    单击**重置**重置当前事务集参考编号为下限。 选择**重置为下限值超出界限时**具有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将的参考编号重置为较低范围值限制，如果超出最大限制。  
  
### <a name="to-configure-local-host--senders-settings"></a>配置本地主机 – 发送方设置  
  
1.  有关**交换控制编号 (UNB5)**，输入要由 BizTalk Server 生成传出交换的交换控制编号的值的范围。 输入一个最小为 1、最大为 999999999 的数值。 此字段是必需字段。  
  
    > [!NOTE]
    >  第一个字段 (**UNB5.1**) 是前缀; 第二个和第三字段 (**UNB5.2**) 包含要用作交换控制编号; 和第四个字段的编号范围 (**UNB5.3**)是的后缀。 前缀和后缀是可选的；控制编号是必需的。 每条新消息的控制编号是递增的；前缀和后缀保持不变。 控制编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。  
    >   
    >  若要将控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限值超出界限时**以自动重置为最小值超过了最大值。  
  
2.  有关**组控制编号 (UNG5)**、 输入前缀、 参考编号范围和 BizTalk Server 应为它发送的第一个交换的组控制编号使用的后缀。  
  
    > [!NOTE]
    >  第一个字段 (**UNG5.1**) 是前缀; 第二个和第三字段 (**UNG5.2**) 包含要用于组控制编号; 和第四个字段的编号范围 (**UNG5.3**) 是后缀。 前缀和后缀是可选的；控制编号是必需的。 每条新消息的控制编号是递增的直到达到最大值；前缀和后缀保持不变。 只允许使用数字中**UNG5.2**。 控制编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。  
    >   
    >  若要将组控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限值超出界限时**以自动重置为最小值超过了最大值。  
  
3.  有关**消息标头 (UNH)**，单击**应用新 ID**、 输入前缀、 参考编号范围，输入和输入 BizTalk Server 应为事务集参考编号使用的后缀。  
  
    > [!NOTE]
    >  第一个字段 (**UNH1.1**) 是前缀; 第二个和第三字段 (**UNH1.2**) 是参考编号范围; 和第四个字段 (**UNH1.3**) 是后缀。 前缀和后缀是可选的；参考编号是必需的。 每条新消息的参考编号是递增的；前缀和后缀保持不变。 参考编号的默认值范围是 1 到 99999999999999。 只允许使用数字中**UNH1.2**。 控制编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。  
    >   
    >  若要重置当前事务集控制编号的最小值，请单击**重置**。 选择**重置为下限值超出界限时**重置控制编号的最小值，如果超过了最大值。  
  
4.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为交换处理配置 EDIFACT 后备协议属性](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)