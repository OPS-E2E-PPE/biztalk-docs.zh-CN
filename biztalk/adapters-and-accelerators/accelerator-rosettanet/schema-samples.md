---
title: 架构示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SDK samples, schemas
- examples, schemas
- schemas, examples
ms.assetid: 7d7e696d-935f-4582-b873-c5637673b651
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4f8070c260c3972b2e8eef58af538932f1c5bf6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966147"
---
# <a name="schema-samples"></a>架构示例
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 包含一系列的 RNIF 和合作伙伴接口过程 (PIP) 处理的 XSD 架构。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]使用这些架构来处理消息。 你可以根据需要修改这些架构，或使用这些架构来排除故障。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 提供三组架构。 它们是与 RosettaNet PIP 相关联的 XSD 架构、RosettaNet 下一代架构和 RNIF 架构。  
  
## <a name="xsd-schemas-associated-with-rosettanet-pips"></a>与 RosettaNet PIP 关联的 XSD 架构  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用这些架构来验证消息实例的服务内容。 你可以修改这些架构来改变消息处理的流程。 在排除服务内容处理过程中的错误时，可以使用这些架构来验证消息实例。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 已将这些架构编译到 RNPIP 程序集中。 通过取消部署 RNPIP 程序集，更改架构，然后重新部署 RNPIP，可以修改这些架构中的任何一个。 但你必须小心谨慎，确保不要对架构进行大幅度更改。 如果你大幅度更改架构，你所做的更改可能会与相应的 RosettaNet PIP 不符。 你还可以向 RNPIP 中添加架构。 有关详细信息，请参阅[修改现有 PIP 在 RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装在这些架构\<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>快捷键RosettaNet\SDK\Schemas。  
  
## <a name="rnif-schemas"></a>RNIF 架构  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用这些架构来验证 RNIF 消息的各部分，如前导头、服务头和传递头。 这些架构还包括适用于确认和异常的架构。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装在这些架构\<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>快捷键RosettaNet\SDK\RNIFSchemas。  
  
## <a name="rosettanet-next-generation-schemas"></a>RosettaNet 下一代架构  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用这些架构来验证消息是否符合 RosettaNet 的下一代架构要求。 这些架构是为支持 XSD（而非 DTD）而设计的。 若要使用这些架构，将它们添加到 RNPIPs 程序集中所述[修改现有 PIP 在 RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装在这些架构\<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>快捷键RosettaNet\SDK\Schemas\Domain、 \Interchange 和 \Universal 文件夹。  
  
## <a name="see-also"></a>另请参阅  
 [PIP 实现](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md)   
 [使用 Pip](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)   
 [示例](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)