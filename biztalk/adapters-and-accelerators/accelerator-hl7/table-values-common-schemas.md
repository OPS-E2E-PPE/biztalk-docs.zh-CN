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
ms.openlocfilehash: 4f577b96f07daa6367a6e68550df441b9d355c5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286561"
---
# <a name="table-values-common-schemas"></a><span data-ttu-id="e6f69-102">表值通用架构</span><span class="sxs-lookup"><span data-stu-id="e6f69-102">Table Values Common Schemas</span></span>
<span data-ttu-id="e6f69-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 生成**tablevalues_*\<版本\>*.xsd**文件为每个 HL7 版本，并查找的根目录处的文件HL7 版本特定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e6f69-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) generates the **tablevalues_*\<version\>*.xsd** file for each HL7 version, and locates the file at the root of the HL7 version-specific folder.</span></span> <span data-ttu-id="e6f69-104">数据类型通用架构文件引用的表值通用架构文件。</span><span class="sxs-lookup"><span data-stu-id="e6f69-104">The data type common schema file references the table values common schema file.</span></span>  
  
 <span data-ttu-id="e6f69-105">在这些表中的值为枚举形式。</span><span class="sxs-lookup"><span data-stu-id="e6f69-105">Values in these tables are in the form of enumerations.</span></span> <span data-ttu-id="e6f69-106">每个枚举定义中的消息架构的一个或多个字段可接受的值。</span><span class="sxs-lookup"><span data-stu-id="e6f69-106">Each enumeration defines the values that are acceptable within one or more fields of the message schemas.</span></span> <span data-ttu-id="e6f69-107">您可以看到哪些表适用于消息架构的节点在 BizTalk 编辑器中打开该架构中，单击某个节点，并查看**Base Data Type**属性窗格中的属性。</span><span class="sxs-lookup"><span data-stu-id="e6f69-107">You can see which table applies to a node of a message schema by opening the schema in BizTalk Editor, clicking a node, and looking at the **Base Data Type** property in the Properties pane.</span></span>  
  
 <span data-ttu-id="e6f69-108">你将无法再查看此节点可接受的值是什么，但是，通过查看消息架构节点的属性窗格中的枚举。</span><span class="sxs-lookup"><span data-stu-id="e6f69-108">You will not be able to see what the acceptable values for this node are, however, by viewing the enumeration in the Properties pane for the message-schema node.</span></span> <span data-ttu-id="e6f69-109">这是因为表值通用架构文件定义枚举。</span><span class="sxs-lookup"><span data-stu-id="e6f69-109">This is because the table values common schema file defines the enumeration.</span></span> <span data-ttu-id="e6f69-110">若要查看枚举，请单击**tablevalues_*\<版本\>*.xsd**在架构树在 BizTalk 编辑器中，然后单击省略号 (**...**) 在属性窗格中的枚举行上的按钮。</span><span class="sxs-lookup"><span data-stu-id="e6f69-110">To view the enumerations, click **tablevalues_*\<version\>*.xsd** in the Schema tree in BizTalk Editor, and then click the ellipsis (**...**) button on the Enumeration row in the Properties pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f69-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6f69-111">See Also</span></span>  
 <span data-ttu-id="e6f69-112">[HL7 2.X 通用架构文件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="e6f69-112">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="e6f69-113">[数据类型通用架构](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="e6f69-113">[Data Types Common Schemas](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span></span>  
 [<span data-ttu-id="e6f69-114">段通用架构</span><span class="sxs-lookup"><span data-stu-id="e6f69-114">Segments Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)