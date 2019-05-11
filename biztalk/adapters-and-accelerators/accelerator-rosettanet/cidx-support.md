---
title: CIDX 支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, procedures
- CIDX, about CIDX
- CIDX, Elemica Exchange Server Provider (ESP)
- CIDX, PIPs
- CIDX
- Elemica Exchange Server Provider (ESP)
- procedures [CIDX]
- PIPs, CIDX
ms.assetid: 58b75ad3-f6b9-47c0-8dbf-506a3eaf010b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7051de5958560163991b7627881dc0efc1643d9a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284876"
---
# <a name="cidx-support"></a>CIDX 支持
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]提供对 CIDX （化工行业数据交换） XML 消息交换的支持。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 支持 CIDX Chem eStandards 2.0 和 3.0，两者都使用 RosettaNet 实现框架 (RNIF) 1.1 版。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]异步简单公用流程 （支持单操作和双操作消息） 使用并路由 CIDX 服务内容。  
  
 对于基于 CIDX PIP 的协议[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将验证消息中的以下：  
  
- 仅 RNIF 1.1 版本  
  
- 非 0A1  
  
- 仅单操作  
  
  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不会阻止您设置`Standard`流程配置为"CIDX"，在设置后的属性`0A1 agreement`使用该配置文件为"0A1"（这不支持为 CIDX） 为协议的属性。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不执行会防止发生这跨字段验证。  
  
## <a name="applying-a-pip-to-a-cidx-implementation"></a>将 PIP 应用于 CIDX 实现  
 若要将 PIP 应用于 CIDX 实现中，设置`Standard`到过程配置文件中的属性**CIDX**。 完成后，你将能够为消息标准、 标准版本和负载绑定 id。 输入值 您可以在 CIDX Chem eStandards 规范中找到这些值。  
  
## <a name="connecting-to-the-elemica-network"></a>连接到 Elemica 网络  
 可以使安装的 Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]若要连接到 Elemica[!INCLUDE[btsExchangeSvrNoVersion](../../includes/btsexchangesvrnoversion-md.md)]提供商 (ESP)。 有关化工行业购买、 销售和供应链管理使用 CIDX 消息交换，可以使用 Elemica 网络。  
  
 你自定义[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]以连接到 Elemica 使用 Elemica 连接包中的项目文件。 您可以下载连接包从[ http://go.microsoft.com/fwlink/?LinkId=46195 ](http://go.microsoft.com/fwlink/?LinkId=46195)。 有关详细信息，请在 MSDN 上参阅"连接到 Elemica 网络使用 BizTalk Accelerator for RosettaNet 3.0"白皮书[ http://go.microsoft.com/fwlink/?linkid=46539 ](http://go.microsoft.com/fwlink/?linkid=46539)。  
  
> [!NOTE]
>  在"连接到 Elemica 网络使用 BizTalk Accelerator for RosettaNet 3.0"白皮书中的信息是对有效[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]。  
  
## <a name="cidx-procedures"></a>CIDX 过程  
 以下各节介绍了如何设置 CIDX 消息交换：  
  
-   [设置 CIDX eStandards 消息交换](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)  
  
-   [创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)  
  
-   [导入基于 XSD 的 PIP](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Accelerator for RosettaNet 向 BizTalk Server 的添加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [CIDX 消息传送标准](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)