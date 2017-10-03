---
title: "贸易合作伙伴协议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- trading partners, agreements
- agreements, trading partners
ms.assetid: 846466d2-db39-42ba-8be1-ecca83a55a02
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26c8ac38e9b3dd0c32b496f3f7750fa0dcd982a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="trading-partner-agreements"></a>贸易合作伙伴协议
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]通过贸易合作伙伴协议 (TPA) 来处理与合作伙伴的消息交换。 TPA 定义消息处理和验证两个合作伙伴之间的特性。 它定义了这些合作伙伴如何实现相关的合作伙伴接口过程 (PIP)，它指定某个特定消息类型的所有实现的消息内容。 TPA 还定义合作伙伴如何通过 Internet 交换消息的详细的信息。  
  
## <a name="trading-partner-agreement-contents"></a>贸易合作伙伴协议内容  
 每个贸易合作伙伴协议包括以下信息：  
  
-   贸易合作伙伴的标识  
  
-   公共，按照定义，处理 RosettaNet 实现框架 (RNIF) 版本 — 每个 TPA 引用单个公共进程用于启动或响应 PIP 操作  
  
-   过程配置的配置文件， [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] PIP 的实现  
  
-   ASPX 设置，包括操作、 信号和同步 Url  
  
-   用于编码和加密协议  
  
-   自定义属性  
  
 要创建贸易合作伙伴协议，必须使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台创建流程配置。 你通常基础上 RosettaNet PIP，此配置，但可以还使它基于自定义的架构。 你必须使用控制台来创建本组织和合作伙伴。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不支持未知的参与方之间的消息交换。 创建的配置和组织后，可以使用管理控制台来创建合作伙伴协议。  
  
### <a name="process-configuration"></a>流程配置  
 这些设置决定了 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 如何处理消息内容； 指定了 RosettaNet PIP，并指示 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将如何实现 PIP。 若要执行此操作，它们提供特定值的行为的设置，PIP 指定，例如，超时和重试值。 因此，两组不同的伙伴或一组相同的合作伙伴，还可以用两种不同方式实现相同的 PIP。  
  
 这些设置也指定的标准 （RosettaNet 或 CIDX） 和家庭的组织与伙伴角色的常规方面。 你还可以创建非 RosettaNet 内容的过程配置。 若要执行此操作，必须为该内容创建架构，然后创建基于该架构的配置。 有关非 RosettaNet 内容，你必须输入值为消息标准、 标准版中和负载绑定 ID 设置**常规**选项卡中**过程配置设置**对话框。 仅可以通过使用 RNIF 2.0 传输非 RosettaNet 内容。  
  
 有关设置这些属性的详细信息，请参阅[如何创建或编辑过程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。  
  
### <a name="home-organization"></a>本组织  
 这些设置用于定义本组织将启动消息。 这些设置包括全局业务标识符 (GBI)，即是业务的唯一标识符的 DUNS 编号，并且联系某些事务中所需的信息。 有关设置这些属性的详细信息，请参阅[创建或编辑了主页的组织](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)。  
  
### <a name="partner-organization"></a>伙伴组织  
 这些设置用于定义将接收和响应消息的合作伙伴。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]验证每个传入 RNIF 消息来自有效的当事方，具有与主组织协议。 如果不是，则 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 验证失败，不处理该消息。 有关设置这些属性的详细信息，请参阅[创建或编辑合作伙伴](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)。  
  
### <a name="agreements-trading-partner-agreement-variables"></a>协议 （贸易合作伙伴协议变量）  
 协议指定贸易合作伙伴关系的所有方面。 正如在 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台中定义的那样，协议指定了流程配置设置的显示代码； 它还指定 RNIF 版本、 端口 Url、 协议设置 （编码和加密） 和其他变量。 有关设置这些属性的详细信息，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。  
  
 有关管理控制台的详细信息，请参阅[管理配置、 证书、 数据库和安全](manage-configuration-certificates-databases-security.md)。 此外可以获取类和接口的开发人员参考 Microsoft.Solutions.BTARN.ConfigurationManager Namespace 通过这些设置的只读的编程访问。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Accelerator for RosettaNet 将添加到 BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [RNIF 管道](../../adapters-and-accelerators/accelerator-rosettanet/rnif-pipelines.md)   
 [如何创建或编辑过程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)   
 [创建或编辑主组织](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)   
 [创建或编辑合作伙伴](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)   
 [创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)