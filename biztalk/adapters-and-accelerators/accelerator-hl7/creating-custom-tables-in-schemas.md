---
title: "在架构中创建自定义表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, Z tables [Z objects]
- Z objects, creating Z tables
- 2.X schemas, creating Z tables
ms.assetid: d6ab8ac9-a835-4ec0-9ddd-76ff267a3cbd
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7c3ce69e60517f90af4031bf76691a551afcbe2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-custom-tables-in-schemas"></a><span data-ttu-id="33eb8-102">在架构中创建自定义的表</span><span class="sxs-lookup"><span data-stu-id="33eb8-102">Creating Custom Tables in Schemas</span></span>
<span data-ttu-id="33eb8-103">你可以在 tablevalues_ 中创建自定义表格\<*版本*>.xsd 公用架构。</span><span class="sxs-lookup"><span data-stu-id="33eb8-103">You can create a custom table in the tablevalues_\<*version*>.xsd common schema.</span></span> <span data-ttu-id="33eb8-104">你可以基于自定义的表，现有的数据类型，一个基本数据类型，或基于表中定义的枚举。</span><span class="sxs-lookup"><span data-stu-id="33eb8-104">You can base a custom table on an existing data type, a base data type, or on an enumeration defined in a table.</span></span>  
  
### <a name="to-create-a-z-table"></a><span data-ttu-id="33eb8-105">若要创建 Z 表</span><span class="sxs-lookup"><span data-stu-id="33eb8-105">To create a Z table</span></span>  
  
1.  <span data-ttu-id="33eb8-106">在解决方案资源管理器，打开通用的数据类型架构文件 **tablevalues_\<*版本*>.xsd * *，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="33eb8-106">In Solution Explorer, open the common data-type schema file **tablevalues_\<*version*>.xsd**, and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="33eb8-107">在 BizTalk 编辑器中，右键单击**HL7DefinedTables**，指向**插入架构节点**，然后单击**子字段元素**。</span><span class="sxs-lookup"><span data-stu-id="33eb8-107">In BizTalk Editor, right-click **HL7DefinedTables**, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span>  
  
3.  <span data-ttu-id="33eb8-108">命名此表与字母"Z"开头的标记。</span><span class="sxs-lookup"><span data-stu-id="33eb8-108">Name the table with a tag starting with the letter "Z".</span></span>  
  
4.  <span data-ttu-id="33eb8-109">根据需要请在属性窗格中，键入所需的特定属性的值。</span><span class="sxs-lookup"><span data-stu-id="33eb8-109">In the Properties pane, type the values you want for specific properties, as needed.</span></span>  
  
5.  <span data-ttu-id="33eb8-110">若要将枚举与表中，在属性窗格中，关联设置**派生源**到**限制**，单击**枚举**，单击的省略号（…）按钮**枚举**，然后键入想要包含在枚举编辑器中的枚举的值。</span><span class="sxs-lookup"><span data-stu-id="33eb8-110">To associate an enumeration with the table, in the Properties pane, set **Derived By** to **Restriction**, click **Enumeration**, click the ellipsis (…) button for **Enumeration**, and then type the values that you want the enumeration to contain in the Enumeration Editor.</span></span> <span data-ttu-id="33eb8-111">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="33eb8-111">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33eb8-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33eb8-112">See Also</span></span>  
 <span data-ttu-id="33eb8-113">[扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="33eb8-113">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="33eb8-114">[创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="33eb8-114">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="33eb8-115">[在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="33eb8-115">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 <span data-ttu-id="33eb8-116">[扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="33eb8-116">[Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span></span>  
 [<span data-ttu-id="33eb8-117">处理未声明的 Z 段</span><span class="sxs-lookup"><span data-stu-id="33eb8-117">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)