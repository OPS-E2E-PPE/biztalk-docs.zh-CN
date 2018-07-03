---
title: 设置 CIDX 解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, process configuration
- creating, CIDX solutions
- CIDX, connecting to Elemica network
- agreements, CIDX
- process configuration, CIDX
- CIDX, agreements
- PIPs, importing for CIDX
- CIDX, PIPs
- CIDX, creating solutions
- CIDX, importing PIPs
- PIPs, CIDX
ms.assetid: 7f1f159f-3b09-4efd-907b-9a75f7f3ecd1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 770691b2862aba307e6f1cc444c8d38adce4aeb4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984286"
---
# <a name="setting-up-a-cidx-solution"></a>设置 CIDX 解决方案
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 提供对 CIDX（化工行业数据交换）XML 消息交换（CIDX Chem eStandards 2.0 版和 3.0 版）的支持。 本主题讲述如何设置 CIDX 解决方案，步骤如下：  
  
-   设置流程配置  
  
-   设置协议  
  
-   应用 PIP  
  
-   导入基于 XSD 的 PIP  
  
-   连接到 Elemica 网络  
  
## <a name="setting-up-a-cidx-process-configuration"></a>设置 CIDX 流程配置  
 若要设置 CIDX eStandards 消息交换，需要创建具有以下属性的流程配置：  
  
- **标准**属性设置为流程配置设置中的**CIDX**  
  
- **是否为单一操作**属性设置为流程配置设置中的 **，则返回 True**  
  
- **0A1 协议**属性设置为贸易合作伙伴协议中的**非 0A1**  
  
  有关详细信息，请参阅[设置 CIDX eStandards 消息交换](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)。  
  
## <a name="creating-a-cidx-agreement"></a>创建 CIDX 协议  
 若要设置 CIDX eStandards 消息交换，需要创建具有以下属性的协议：  
  
- **RNIF 版本**属性设置为协议设置中的**V01.10.00**  
  
- **0A1 协议**属性设置为协议设置中的**非 0A1**  
  
  有关详细信息，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。  
  
## <a name="applying-a-pip-for-cidx"></a>为 CIDX 应用 PIP  
 若要将 PIP 应用于 CIDX 实现中，设置**标准**到过程配置文件中的属性**CIDX**。 完成后，你将能够输入的值**消息标准**，**标准版本**，并**负载绑定 ID**。 您可以在 CIDX Chem eStandards 规范中找到这些值。  
  
## <a name="importing-an-xsd-based-pip-for-cidx"></a>为 CIDX 导入基于 XSD 的 PIP  
 若要为 CIDX 导入基于 XSD 的 PIP，需要在 cidx.org 下载 PIP 的 ZIP 文件[ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=62361)。 请按照导入过程中所述[导入基于 XSD 的 PIP](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)。  
  
## <a name="connecting-to-the-elemica-network"></a>连接到 Elemica 网络  
 可以使用 Elemica Connectivity Pack（Elemica 连接包）中的项目文件来自定义 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]，使其连接到 Elemica。 您可以下载连接包从[ http://go.microsoft.com/fwlink/?LinkId=46195 ](http://go.microsoft.com/fwlink/?LinkId=46195)。 有关详细信息，请在 MSDN 上参阅"连接到 Elemica 网络使用 BizTalk Accelerator for RosettaNet 3.0"白皮书[ http://go.microsoft.com/fwlink/?linkid=46539 ](http://go.microsoft.com/fwlink/?linkid=46539)。  
  
> [!NOTE]
>  “Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0”（使用 BizTalk Accelerator for RosettaNet 3.3 连接到 Elemica 网络）白皮书中的信息对 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 有效。  
  
## <a name="see-also"></a>请参阅  
 [CIDX 支持](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)   
 [CIDX 消息传送标准](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)   
 [设置 CIDX eStandards 消息交换](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)   
 [创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)   
 [导入基于 XSD 的 PIP](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)