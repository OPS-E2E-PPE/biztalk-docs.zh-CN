---
title: 保留批的交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 907e07f3-1f3e-485e-a82d-b28eb7658e0a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4360e4e042ee7302935d20029be2880aee9f4be2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271160"
---
# <a name="preserving-a-batched-interchange"></a>保留批的交换
本主题介绍如何配置批处理的 EDI 交换作为单个文档处理而不拆分事务集从交换的协议。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-the-receiving-and-sending-of-a-preserved-batch"></a>若要配置接收和发送保留批  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点。 在中**参与方和业务配置文件**页上，单击具有将解析为传入批处理交换的协议的参与方。 在中**协议**部分中的页上，右键单击该协议，然后单击**属性**。 在中**协议属性**对话框单向协议选项卡 （向其解析将入站批处理的交换） 中，执行以下操作：  
  
   1.  在中**标识符**页上，输入为 ISA5、 ISA6、 ISA7 和 ISA8 的值输入值。 请确保输入正确的值，使传入批处理的交换解析为该协议。  
  
   2.  在中**本地主机设置**页 (下**交换设置**)，在**接收方设置**部分中，为**入站批处理选项**，选择以下选项：  
  
       -   **保留交换-出错时挂起交换**– 选择此选项可指定 BizTalk Server 应原样保留交换不变，同时创建一个 XML 文档为整个批处理交换。 使用此选项时，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。  
  
       -   **保留交换-出错时挂起事务集**– 选择此选项可指定 BizTalk Server 应原样保留交换不变，同时创建一个 XML 文档为整个批处理交换。 使用此选项，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起的事务集，同时继续处理所有其他事务集。  
  
       > [!NOTE]
       >  如果选择上面提到的两个选项之一，则交换、 组和事务集段属性 （确定 BizTalk Server 将如何创建传出交换的 ISA、 GS 和 ST 标头） 不适。 当发送管道对其进行处理用于发送保留交换、 组和要保留的交换中存在的事务集标头。 但是，如果你确实想要使用的交换协议中指定的值，设置`EDI.PopulateInterchangeValues`上下文属性设为 true。  
  
2. 创建保留的批处理的 Visual Studio 项目，如下所示：  
  
   1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、 创建 BizTalk 项目并添加批中的所有消息的架构。  
  
   2. 生成和部署项目。  
  
3. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建发送端口以发送保留的批，如下所示：  
  
   1.  发送管道设置为**EdiSend**或**AS2EdiSend**。  
  
   2.  将发送端口的筛选器设置为上下文属性`EDI.ReuseEnvelope == True`。  
  
       > [!NOTE]
       >  设置此筛选器，可确保发送端口将订阅保留的所有批处理交换。 EdiReceive 接收管道会升级上下文属性`EDI.ReuseEnvelope`以将交换标识为保留。  
  
## <a name="see-also"></a>请参阅  
 [配置 EDI 批](../core/configuring-edi-batches.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)