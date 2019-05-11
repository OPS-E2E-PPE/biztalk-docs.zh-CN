---
title: 配置回退本地主机设置 （X12-交换设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b552fa2b-1154-491f-9bcf-aaba3b8f343f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d71fae411bf6a2bd016706d540ad53b969f4f2bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355526"
---
# <a name="configuring-fallback-local-host-settings-x12-interchange-settings"></a>配置回退本地主机设置（X12-交换设置）
本地主机设置控制如何处理 EDI 交换。 此页上的设置可划分为两个类别： 接收方设置 （用于传入交换） 和发件人的设置 （适用于传出交换）。 作为接收方设置的一部分，可以指定将生成 ST02 的方式，确认控制编号。 作为发送方设置的一部分，可以指定如何为传出消息生成控制编号。  
  
> [!NOTE]
>  此处所述的设置也适用于 HIPAA 交换。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-local-host--receivers-settings"></a>若要配置本地主机 – 接收方设置  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。  
  
2. 在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**交换设置**部分中，单击**本地主机设置**.  
  
3. 若要指定确认中使用的事务集控制编号范围，请输入中的值**确认控制编号 (ST02)** 字段。 输入用于中间两个字段值的数值和的字母数字值 （如果需要） 的前缀和后缀字段。 中间字段是必需的包含的控制编号; 的最小值和最大值前缀和后缀是可选的。 所有三个字段的最大长度是九个字符。  
  
    若要重置当前事务集控制编号的最小值，请单击**重置**。 检查**重置为下限值超出界限时**重置为下限的控制编号，一旦超出了最大值。  
  
### <a name="to-configure-local-host--senders-settings"></a>若要配置本地主机 – 发送方设置  
  
1.  有关**交换控制编号 (ISA13)**，输入要由 BizTalk Server 生成传出交换的交换控制编号的值的范围。 输入具有最小为 1 和最大为 999999999 的数值。 这是必填字段。  
  
     若要将控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限值超出界限时**以自动重置为最小值超过了最大值。  
  
2.  有关**组控制编号 (GS06)**，输入 BizTalk Server 应为组控制编号使用的数字范围。 输入最少一个字符，最多九个字符的数字值。 这是必填字段。  
  
     若要将组控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限值超出界限时**以自动重置为最小值超过了最大值。  
  
3.  有关**事务集控制编号 (ST02)**，单击**应用新 ID**，然后为可选前缀和后缀输入所需的中间字段的数值和字母数字值的范围。 所有四个字段的最大长度是九个字符。  
  
     若要重置当前事务集控制编号的最小值，请单击**重置**。 选择**重置为下限值超出界限时**重置控制编号的最小值，如果超过了最大值。  
  
4.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为交换处理配置 X12 后备协议属性](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)