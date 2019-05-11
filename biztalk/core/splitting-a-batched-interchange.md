---
title: 拆分批处理的交换 |Microsoft Docs
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
ms.openlocfilehash: 7d7f8da0fafe80b96368388d667a5a0934364c83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243143"
---
# <a name="splitting-a-batched-interchange"></a>拆分批处理的交换
本主题介绍如何配置协议以便通过将拆分该交换的事务集处理批处理的 EDI 交换。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-receive-a-split-edi-interchange"></a>若要接收一个拆分 EDI 交换  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点。 在中**参与方和业务配置文件**页上，单击具有将解析为传入批处理交换的协议的参与方。 在中**协议**部分中的页上，右键单击该协议，然后单击**属性**。 在中**协议属性**对话框单向协议选项卡 （向其解析将入站批处理的交换） 中，执行以下操作：  
  
   1.  在中**标识符**页上，请确保输入正确的值，使传入批处理的交换解析为该协议。  
  
       -   情况下**X12**:设置 ISA5、 ISA6、 ISA7 和 ISA8。  
  
       -   情况下**Edifact**:设置 UNB2.1、 UNB2.2、 UNB3.1 和 unb3.2 一起使用。  
  
   2.  在中**本地主机设置**页 (下**交换设置**)，在**接收方设置**部分中，为**入站批处理选项**，选择以下选项：  
  
       -   **将交换拆分为事务集-出错时挂起事务集**– 选择此选项以指定 BizTalk Server 应解析为单独 XML 文档将交换中设置每个事务。 然后，BizTalk Server 将向事务集应用相应的信封和事务集文档路由到 MessageBox。 使用此选项时，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起的事务集。  
  
       -   **将交换拆分为事务集-出错时挂起交换**– 选择此选项以指定 BizTalk Server 应解析为单独 XML 文档将交换中设置每个事务。 然后，BizTalk Server 将向事务集应用相应的信封和事务集文档路由到 MessageBox。 使用此选项时，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。  
  
2. 创建保留的批处理的 Visual Studio 项目，如下所示：  
  
   1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、 创建 BizTalk 项目并添加批中的所有消息的架构。  
  
   2. 生成和部署项目。  
  
3. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建一个发送端口以便发送拆分批处理，如下所示：  
  
   1.  发送管道设置为**EdiSend**或**AS2EdiSend**。  
  
   2.  设置为所需值以便提取每个事务集，例如，BTS 到发送端口的筛选器。MessageType。  
  
## <a name="see-also"></a>请参阅  
 [配置 EDI 批](../core/configuring-edi-batches.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)