---
title: "在架构中创建自定义数据类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, creating Z data types [Z objects]
- data types, creating [Z objects]
- Z objects, creating Z data types
ms.assetid: e545c849-d414-4d5d-bb56-d3f9d5238c70
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09b07843a6e010021b00a1ffa7c3010977d1d3c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-custom-data-types-in-schemas"></a><span data-ttu-id="f6bfd-102">在架构中创建自定义数据类型</span><span class="sxs-lookup"><span data-stu-id="f6bfd-102">Creating Custom Data Types in Schemas</span></span>
<span data-ttu-id="f6bfd-103">你可以在 datatypes_ 中创建自定义数据类型\<*版本*>.xsd 公用架构。</span><span class="sxs-lookup"><span data-stu-id="f6bfd-103">You can create a custom data type in the datatypes_\<*version*>.xsd common schema.</span></span> <span data-ttu-id="f6bfd-104">你可以基于自定义数据类型，现有的数据类型，一个基本数据类型，或基于表中定义的枚举。</span><span class="sxs-lookup"><span data-stu-id="f6bfd-104">You can base a custom data type on an existing data type, a base data type, or on an enumeration defined in a table.</span></span>  
  
### <a name="to-create-a-z-data-type"></a><span data-ttu-id="f6bfd-105">若要创建 Z 数据类型</span><span class="sxs-lookup"><span data-stu-id="f6bfd-105">To create a Z data type</span></span>  
  
1.  <span data-ttu-id="f6bfd-106">在解决方案资源管理器的 Visual Studio 中，打开通用的数据类型架构文件 (**datatypes_\<*版本*>.xsd * *)，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="f6bfd-106">In Solution Explorer of Visual Studio, open the common data-type schema file (**datatypes_\<*version*>.xsd**), and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="f6bfd-107">在 BizTalk 编辑器中，右键单击**HL7DefinedDataTypes**，指向**插入架构节点**，然后单击**子记录**创建组件数据类型，或单击**子元素**创建简单的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f6bfd-107">In BizTalk Editor, right-click **HL7DefinedDataTypes**, point to **Insert Schema Node**, and then click **Child Record** to create a component data type, or click **Child Element** to create a simple data type.</span></span>  
  
3.  <span data-ttu-id="f6bfd-108">具有"Z"开头的三个字符标记名称的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f6bfd-108">Name the data type with a three-character tag starting with "Z".</span></span>  
  
4.  <span data-ttu-id="f6bfd-109">在属性窗格中，键入所需的值**基数据类型**，**数据类型**，和其他属性，根据需要。</span><span class="sxs-lookup"><span data-stu-id="f6bfd-109">In the Properties pane, type the values you want for **Base Data Type**, **Data Type**, and other properties, as needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6bfd-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6bfd-110">See Also</span></span>  
 <span data-ttu-id="f6bfd-111">[扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="f6bfd-111">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="f6bfd-112">[创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="f6bfd-112">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="f6bfd-113">[在架构中创建自定义的表](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="f6bfd-113">[Creating Custom Tables in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span></span>  
 <span data-ttu-id="f6bfd-114">[扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="f6bfd-114">[Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span></span>  
 [<span data-ttu-id="f6bfd-115">处理未声明的 Z 段</span><span class="sxs-lookup"><span data-stu-id="f6bfd-115">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)