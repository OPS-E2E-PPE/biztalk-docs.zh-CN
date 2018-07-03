---
title: 启用多个接收交换中的单个消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c98bcd2e-495a-49d8-a471-6e23b1e161f9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77af57fb4a72e2e0c039b512d4e6f30659ccedd5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006846"
---
# <a name="enabling-the-receiving-of-multiple-interchanges-in-a-single-message"></a>启用接收单个消息中的多个交换
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以处理包含多个交换的消息。 对于 X12 消息，此类消息将包括多个 ISA 标头和 IEA 尾部。 对于 EDIFACT 消息，此类消息将包括多个 UNA/UNB 标头和 UNZ 尾部。  
  
 若要启用 EDI 拆装器在 EdiReceive 或 AS2EdiReceive 管道中，以便解析单个消息中的多个交换，必须设置**DetectMID**管道属性设置为**True**。 （MID 表示多个交换拆装。）默认情况下，该属性设置为 True。  
  
 当包括 EDI 拆装器的接收管道收到具有多个交换的消息时，该拆装器将从交换标头至交换尾部解析每个交换。 此处理依据的规则如下：  
  
- 相同消息中的所有交换必须具有相同的编码类型，X12 或 EDIFACT。 如果消息包含的交换具有多个编码类型，EDI 拆装器会将具有相同编码类型的所有交换作为该消息中的第一个交换进行处理。 拆装器将忽略其编码类型不同于第一个交换的所有交换。  
  
- EDI 拆装器将忽略某一交换的交换尾部和下一交换的交换标头之间的任何字符。  
  
- 如果通过选择启用身份验证**身份验证失败时删除消息**或**身份验证失败时保留消息**属性的接收端口，然后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将如果消息中多个交换的任何一个失败，则挂起整个消息。  
  
- 如果启用验证，当同一消息中的任一交换未解析到协议时，将挂起该消息中的所有交换，并且不会返回任何确认，即使对于已解析到协议的交换也是如此。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-enable-the-receiving-of-multiple-interchanges-in-a-message"></a>启用接收一个消息中的多个交换  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**接收位置**节点，右键单击你想要启用以接收多个接收位置交换中一条消息，然后单击**属性**。  
  
2. 单击接收管道（必须是 EdiReceive 或 AS2EdiReceive）旁的省略号。  
  
3. 在中**配置管道**对话框中，将**DetectMID**管道属性设置为**True**。  
  
4. 单击**确定**，然后单击**确定**试。  
  
## <a name="see-also"></a>请参阅  
 [为 EDI 解决方案配置端口](../core/configuring-ports-for-an-edi-solution.md)