---
title: CIDX 支持 |Microsoft 文档
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
ms.openlocfilehash: 224d2b50d132efa67e1cfc24dda2df77fa7d29e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210693"
---
# <a name="cidx-support"></a>CIDX 支持
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] CIDX （筛选行业数据交换） XML 消息交换提供支持。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]支持 CIDX Chem eStandards 版本 2.0 和 3.0，这两种使用 RosettaNet 实现框架 (RNIF) 1.1。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 异步简单公用流程（支持单操作和双操作消息）使用并路由 CIDX 服务内容。  
  
 对于基于 CIDX PIP 的协议，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 在消息中验证以下内容：  
  
-   仅 RNIF 1.1 版本  
  
-   非 0A1  
  
-   仅单操作  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不会阻止你设置`Standard`"CIDX"，在设置后到过程配置的属性`0A1 agreement`使用该配置文件"0A1"（这不支持为 CIDX） 到了协议的属性。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不执行跨域验证，这会阻止。  
  
## <a name="applying-a-pip-to-a-cidx-implementation"></a>将 PIP 应用于 CIDX 实现  
 若要应用到 CIDX 实现 PIP，设置`Standard`到过程配置配置文件中的属性**CIDX**。 完成后，你将能够为消息标准、 标准版中和负载绑定 id。 输入值 您可以在 CIDX Chem eStandards 规范中找到这些值。  
  
## <a name="connecting-to-the-elemica-network"></a>连接到 Elemica 网络  
 你可以启用的安装[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]连接到 Elemica[!INCLUDE[btsExchangeSvrNoVersion](../../includes/btsexchangesvrnoversion-md.md)]提供程序 (ESP)。 您可以通过 Elemica 网络使用 CIDX 消息交换进行化工行业中的购买、销售和供应链管理。  
  
 你自定义[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]连接到 Elemica 使用 Elemica 连接包中的项目文件。 你可以下载从连接包[http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195)。 有关详细信息，请在 MSDN 上参阅"连接到具有 BizTalk Accelerator for RosettaNet 3.0 的 Elemica 网络"白皮书[http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539)。  
  
> [!NOTE]
>  “Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0”（使用 BizTalk Accelerator for RosettaNet 3.3 连接到 Elemica 网络）白皮书中的信息对 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 有效。  
  
## <a name="cidx-procedures"></a>CIDX 过程  
 以下部分讲述如何设置 CIDX 消息交换：  
  
-   [设置向上 CIDX eStandards 消息交换](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)  
  
-   [创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)  
  
-   [导入基于 XSD 的 PIP](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Accelerator for RosettaNet 将添加到 BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [CIDX 消息传送标准](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)