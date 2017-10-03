---
title: "表值通用架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, common schemas
- 2.X schemas, table values
- common schemas
ms.assetid: 2421e150-1bae-43bd-aba3-6322c679b22b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b93434c57988b8ef0cdb068ffb960e6fb342edc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="table-values-common-schemas"></a>表值通用架构
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 生成 **tablevalues_*\<版本 >*.xsd * * 文件，以每个 HL7 版本，然后查找根目录下的 HL7 文件特定于版本的文件夹。 数据类型的公共架构文件引用的表值常见架构文件。  
  
 这些表中的值为枚举形式。 每个枚举定义的消息架构的一个或多个字段中可接受的值。 你可以看到哪些表适用于的消息架构节点打开架构 BizTalk 编辑器中，单击某个节点，然后查看**基数据类型**在属性窗格中的属性。  
  
 你将无法查看此节点可接受的值是什么，但是，通过在消息架构节点的属性窗格中查看的枚举。 这是因为表值常见架构文件定义枚举。 若要查看的枚举，请单击 **tablevalues_*\<版本 >*.xsd * * 在架构中树在 BizTalk 编辑器中，，然后单击省略号 (**...**) 在属性窗格中的枚举行上的按钮。  
  
## <a name="see-also"></a>另请参阅  
 [HL7 2.X 公共架构文件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)   
 [数据类型的通用架构](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md)   
 [段通用架构](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)