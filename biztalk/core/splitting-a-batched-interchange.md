---
title: 拆分批处理的交换 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e67bef19-77fb-47a9-88f3-ee20043b3691
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 745f94d4ec56222d3c1d3e03c0817933248f4b8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278941"
---
# <a name="splitting-a-batched-interchange"></a>拆分批处理的交换
本主题介绍了如何配置协议以便通过从交换拆分事务集来处理批处理的 EDI 交换。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-receive-a-split-edi-interchange"></a>接收一个拆分 EDI 交换  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点。 在**方和业务配置文件**页上，单击具有协议，将解析为传入批处理的交换的当事方。 在**协议**部分的页上，右键单击该协议，然后单击**属性**。 在**协议属性**对话框中，在 （向其解决将入站批处理的交换） 的单向协议选项卡上，执行以下操作：  
  
    1.  在**标识符**页上，请确保输入正确的值，以便传入批处理的交换解析为此协议。  
  
        -   情况下**X12**： 设置 ISA5、 ISA6、 ISA7 和 ISA8。  
  
        -   情况下**Edifact**： 设置 UNB2.1、 UNB2.2、 UNB3.1 和 UNB3.2。  
  
    2.  在**本地主机设置**页 (下**交换设置**) 下**接收方设置**部分中，为**入站批处理选项**，选择以下选项：  
  
        -   **将交换拆分为事务集-出错时暂停事务集**– 选择此选项以指定 BizTalk Server 应分析每个事务集到单独的 XML 文档将交换中。 然后，BizTalk Server 将相应的信封应用到事务集，并且将事务集文档路由至 MessageBox。 选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将仅挂起这些交换集。  
  
        -   **将交换拆分为事务集-出错时暂停交换**– 选择此选项以指定 BizTalk Server 应分析每个事务集到单独的 XML 文档将交换中。 然后，BizTalk Server 将相应的信封应用到事务集，并且将事务集文档路由至 MessageBox。 选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。  
  
2.  按下列操作为保留批创建 Visual Studio 项目：  
  
    1.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建一个 BizTalk 项目，并为批处理内的所有消息添加架构。  
  
    2.  生成和部署项目。  
  
3.  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，创建发送端口以便发送拆分批处理，如下所示：  
  
    1.  发送管道设置为**EdiSend**或**AS2EdiSend**。  
  
    2.  将发送端口的筛选器设置为所需值以便提取每个事务集，例如，设置为 BTS.MessageType。  
  
## <a name="see-also"></a>另请参阅  
 [配置 EDI 批处理](../core/configuring-edi-batches.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)