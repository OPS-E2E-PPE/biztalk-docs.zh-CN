---
title: 架构示例 |Microsoft Docs
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
ms.openlocfilehash: 344780047c9072dab00bb4b04ffe33f783e4d9fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281930"
---
# <a name="schema-samples"></a>架构示例
The Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 包括一系列用于 RNIF 和合作伙伴接口流程 (PIP) 处理的 XSD 架构。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用这些架构来处理消息。 可以修改这些架构以根据自己的目的，或使用这些来排除故障。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 提供三组架构。 这些架构包括与 RosettaNet Pip 相关联的 XSD 架构、 RosettaNet 下一代架构和 RNIF 架构。  
  
## <a name="xsd-schemas-associated-with-rosettanet-pips"></a>与 RosettaNet Pip 相关联的 XSD 架构  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用这些架构来验证消息实例的服务内容。 您可以修改这些架构来改变消息处理。 此外可以使用架构来验证消息实例中处理服务内容的错误进行故障排除时。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 已编译到 Rnpip 程序集的两个架构。 通过取消部署 Rnpip 程序集、 更改架构，以及然后重新部署 Rnpip，可以修改这些架构中的任何一个。 您必须小心不要更改架构。 如果您更改架构，所做的更改可能不符合相应的 RosettaNet PIP。 您还可以向 Rnpip 中添加架构。 有关详细信息，请参阅[修改 Rnpip 中的现有 PIP](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将这些架构安装\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Schemas。  
  
## <a name="rnif-schemas"></a>RNIF 架构  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用这些架构来验证 RNIF 消息部分，如前导头、 服务头和传递头。 这些内容还包括适用于确认和异常的架构。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将这些架构安装\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\RNIFSchemas。  
  
## <a name="rosettanet-next-generation-schemas"></a>RosettaNet 下一代架构  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用这些架构来验证符合 RosettaNet 的下一代架构的消息。 这些架构本身，而不是 Dtd 支持 XSD。 若要使用这些架构，将其添加到 Rnpip 程序集中所述[修改 Rnpip 中的现有 PIP](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将这些架构安装\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator forRosettaNet\SDK\Schemas\Domain、 \Interchange 和 \Universal 文件夹。  
  
## <a name="see-also"></a>请参阅  
 [PIP 实现](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md)   
 [使用 Pip](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)   
 [示例](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)