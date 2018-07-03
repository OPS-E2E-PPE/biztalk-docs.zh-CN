---
title: 表值通用架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, common schemas
- 2.X schemas, table values
- common schemas
ms.assetid: 2421e150-1bae-43bd-aba3-6322c679b22b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90c66ee201e5a73d8f632a8002a9a3627d1885f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968062"
---
# <a name="table-values-common-schemas"></a>表值通用架构
Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 生成**tablevalues_*\<版本\>*.xsd**文件为每个 HL7 版本，并查找的根目录处的文件HL7 版本特定的文件夹。 数据类型通用架构文件引用的表值通用架构文件。  
  
 在这些表中的值为枚举形式。 每个枚举定义中的消息架构的一个或多个字段可接受的值。 您可以看到哪些表适用于消息架构的节点在 BizTalk 编辑器中打开该架构中，单击某个节点，并查看**Base Data Type**属性窗格中的属性。  
  
 你将无法再查看此节点可接受的值是什么，但是，通过查看消息架构节点的属性窗格中的枚举。 这是因为表值通用架构文件定义枚举。 若要查看枚举，请单击**tablevalues_*\<版本\>*.xsd**在架构树在 BizTalk 编辑器中，然后单击省略号 (**...**) 在属性窗格中的枚举行上的按钮。  
  
## <a name="see-also"></a>请参阅  
 [HL7 2.X 通用架构文件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)   
 [数据类型通用架构](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md)   
 [段通用架构](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)