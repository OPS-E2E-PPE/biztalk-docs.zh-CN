---
title: 贸易合作伙伴协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trading partners, agreements
- agreements, trading partners
ms.assetid: 846466d2-db39-42ba-8be1-ecca83a55a02
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc197479f20453225d70d425a0f59290c79e5d84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280481"
---
# <a name="trading-partner-agreements"></a>贸易合作伙伴协议
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]的贸易合作伙伴协议 (TPA) 来处理与合作伙伴交换消息。 TPA 定义消息处理和验证两个合作伙伴之间的细节。 它定义了这些合作伙伴如何实现相关的合作伙伴接口流程 (PIP)，它指定特定的消息类型的所有实现的消息内容。 TPA 还定义合作伙伴通过 Internet 交换消息的方式的详细信息。  
  
## <a name="trading-partner-agreement-contents"></a>贸易合作伙伴协议内容  
 每个贸易合作伙伴协议包括以下信息：  
  
- 贸易合作伙伴的标识  
  
- 公用流程，如 RosettaNet 实现框架 (RNIF) 版本定义的 — 每个 TPA 引用单个公用流程，以便发起或响应 PIP 操作  
  
- 流程配置的配置文件， [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] PIP 的实现  
  
- ASPX 设置，包括操作、 信号和同步 Url  
  
- 用于编码和加密协议  
  
- 自定义属性  
  
  若要创建贸易合作伙伴协议，必须使用[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台创建流程配置。 您通常基于在 RosettaNet PIP，此配置，但也可以基于其自定义架构。 您必须使用控制台创建本组织和合作伙伴。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不支持在未知参与方之间交换消息。 配置和组织创建之后，可以使用管理控制台创建合作伙伴协议。  
  
### <a name="process-configuration"></a>过程配置  
 这些设置确定如何[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]处理消息内容。 它们指定了 RosettaNet PIP，并指示如何[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将实现 PIP。 若要执行此操作，它们提供特定值的行为的设置，PIP 指定，例如，超时和重试值。 因此，两组不同的合作伙伴或一组相同的合作伙伴，还可以用两种不同方式实现同一 PIP。  
  
 这些设置还指定的标准 （RosettaNet 或 CIDX） 和本组织和合作伙伴角色的常规方面。 此外可以创建流程配置对于非 RosettaNet 内容。 若要执行此操作，必须为该内容创建架构，然后创建基于该架构的配置。 对于非 RosettaNet 内容，您必须输入的值的消息标准、 标准版和负载绑定 ID 设置**常规**选项卡**流程配置设置**对话框。 仅可以通过使用 RNIF 2.0 传输非 RosettaNet 内容。  
  
 有关如何设置这些属性的详细信息，请参阅[如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。  
  
### <a name="home-organization"></a>本组织  
 这些设置定义本组织，将启动的消息。 设置包括全局业务标识符 (GBI)，即是业务的唯一标识符的 duns 和联系人中某些交易记录所需的信息。 有关如何设置这些属性的详细信息，请参阅[创建或编辑本组织](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)。  
  
### <a name="partner-organization"></a>合作伙伴组织  
 这些设置用于定义将接收和响应消息的合作伙伴。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 验证每个传入的 RNIF 消息来自有效的当事方拥有与本组织的协议。 如果没有，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将无法进行身份验证并处理该消息。 有关如何设置这些属性的详细信息，请参阅[创建或编辑合作伙伴](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)。  
  
### <a name="agreements-trading-partner-agreement-variables"></a>协议 （贸易合作伙伴协议变量）  
 该协议指定贸易合作伙伴关系的所有方面。 它指定流程配置设置，显示代码中定义[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台。 它还指定 RNIF 版本、 端口 Url、 协议设置 （编码和加密） 和其他变量。 有关如何设置这些属性的详细信息，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。  
  
 有关管理控制台的详细信息，请参阅[管理配置、 证书、 数据库和安全](manage-configuration-certificates-databases-security.md)。 此外可以只读能够以编程方式访问的类和接口的开发人员参考中 Microsoft.Solutions.BTARN.ConfigurationManager Namespace 通过这些设置。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Accelerator for RosettaNet 向 BizTalk Server 的添加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [RNIF 管道](../../adapters-and-accelerators/accelerator-rosettanet/rnif-pipelines.md)   
 [如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)   
 [创建或编辑本组织](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)   
 [创建或编辑合作伙伴](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)   
 [创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)