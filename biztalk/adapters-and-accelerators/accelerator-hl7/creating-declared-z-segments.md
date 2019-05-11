---
title: 创建声明的 Z 段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Z objects, creating segments
- segments, creating Z segments [Z objects]
- Z segments, creating
- creating, Z segments [Z objects]
ms.assetid: afd1b7b7-089e-4c6a-a063-e708431bb888
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67b6469130173dbdc60d223f4f5c4f268699ce3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255636"
---
# <a name="creating-declared-z-segments"></a><span data-ttu-id="e521b-102">创建声明的 Z 段</span><span class="sxs-lookup"><span data-stu-id="e521b-102">Creating Declared Z Segments</span></span>
<span data-ttu-id="e521b-103">可以在任何级别 （不同于未声明的 Z 段，它必须是以下正文部分的多方消息的最后一部分） 的架构创建声明的 Z 段。</span><span class="sxs-lookup"><span data-stu-id="e521b-103">You can create declared Z segments at any level of a schema (unlike undeclared Z segments, which must be the last part of a multi-party message, following the body part).</span></span>  
  
### <a name="to-create-a-z-segment-in-biztalk-editor"></a><span data-ttu-id="e521b-104">若要创建在 BizTalk 编辑器中的 Z 段</span><span class="sxs-lookup"><span data-stu-id="e521b-104">To create a Z segment in BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="e521b-105">在解决方案资源管理器的 Visual Studio 中，右键单击你想要添加的 Z 段，并单击的架构**打开**。</span><span class="sxs-lookup"><span data-stu-id="e521b-105">In Solution Explorer of Visual Studio, right-click the schema to which you want to add a Z segment, and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="e521b-106">在 BizTalk 编辑器中，右键单击具有架构的名称的节点，指向**插入 Schema 节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="e521b-106">In BizTalk Editor, right-click the node with the name of the schema, point to **Insert Schema Node**, and then click **Child Record**.</span></span>  
  
3.  <span data-ttu-id="e521b-107">名称的名称以三个字母数字，字母都大写，与第一个数字被"Z"开头的记录。</span><span class="sxs-lookup"><span data-stu-id="e521b-107">Name the record starting the name with three alphanumeric digits, in capitals, with the first digit being "Z".</span></span> <span data-ttu-id="e521b-108">（Z 段标记必须包含三个字符）。插入下划线 (_)，然后添加段的简短说明。</span><span class="sxs-lookup"><span data-stu-id="e521b-108">(The Z segment tag must include three characters.) Insert an underscore (_), and then add a short description of the segment.</span></span> <span data-ttu-id="e521b-109">说明应为一个或一系列文字，不含空格，使用首字母大写每个单词的第一个字母。</span><span class="sxs-lookup"><span data-stu-id="e521b-109">The description should be one or a series of words, without spaces, with the first letter of each word capitalized.</span></span> <span data-ttu-id="e521b-110">最后一个单词应为"段"。</span><span class="sxs-lookup"><span data-stu-id="e521b-110">The last word should be "Segment".</span></span> <span data-ttu-id="e521b-111">（例如，"ZPP_PatientPreferencesSegment。）按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="e521b-111">(An example is "ZPP_PatientPreferencesSegment.) Press **Enter**.</span></span>  
  
4.  <span data-ttu-id="e521b-112">在属性窗格中，键入想要的 Z 段的属性包括**Data Structure Type** （架构名称或格式 xsd: anytype） **Max Occurs**，并**Min Occurs**。</span><span class="sxs-lookup"><span data-stu-id="e521b-112">In the Properties pane, type the properties you want for the Z segment, including **Data Structure Type** (schema name or xsd:anyType), **Max Occurs**, and **Min Occurs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e521b-113">如果输入数据结构类型的记录，你将不能添加子字段元素。</span><span class="sxs-lookup"><span data-stu-id="e521b-113">If you enter a data structure type for the record, you will not be able to add a child field element.</span></span>  
  
5.  <span data-ttu-id="e521b-114">在 BizTalk 编辑器中，右键单击的 Z 段的名称，指向**插入 Schema 节点**，然后单击**子字段元素**。</span><span class="sxs-lookup"><span data-stu-id="e521b-114">In BizTalk Editor, right-click the name of the Z segment, point to **Insert Schema Node**, then click **Child Field Element**.</span></span>  
  
6.  <span data-ttu-id="e521b-115">键入名称开头的段名称后, 跟一个句点和跟下划线，然后在字段的简短说明的字段数的前三个数字字段的名称。</span><span class="sxs-lookup"><span data-stu-id="e521b-115">Type the name of the field, starting the name with the first three digits of the segment name, followed by a period and the number of the field, followed by an underscore and then a short description of the field.</span></span> <span data-ttu-id="e521b-116">说明应为一个或一系列文字，不含空格，使用首字母大写每个单词的第一个字母。</span><span class="sxs-lookup"><span data-stu-id="e521b-116">The description should be one or a series of words, without spaces, with the first letter of each word capitalized.</span></span> <span data-ttu-id="e521b-117">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="e521b-117">Press **Enter**.</span></span>  
  
7.  <span data-ttu-id="e521b-118">在属性窗格中，键入想要的 Z 段的属性包括**数据类型**， **Nillable**，**固定**，**最大出现次数**，并**最小出现次数**。</span><span class="sxs-lookup"><span data-stu-id="e521b-118">In the Properties pane, type the properties you want for the Z segment, including **Data Type**, **Nillable**, **Fixed**, **Max Occurs**, and **Min Occurs**.</span></span>  
  
8.  <span data-ttu-id="e521b-119">若要创建组件字段，将创建为一个记录，然后再创建该记录为每个组件的子元素。</span><span class="sxs-lookup"><span data-stu-id="e521b-119">To create a field with components, create the field as a record, and then create a child element of that record for each component.</span></span> <span data-ttu-id="e521b-120">若要使用子组件创建一个字段，创建字段和组件作为记录，并且子组件为作为子元素。</span><span class="sxs-lookup"><span data-stu-id="e521b-120">To create a field with subcomponents, create the field and components as records, and the subcomponents as child elements.</span></span> <span data-ttu-id="e521b-121">请注意，子组件不能为复合数据类型。</span><span class="sxs-lookup"><span data-stu-id="e521b-121">Note that subcomponents cannot be composite data types.</span></span> <span data-ttu-id="e521b-122">例如，对于名为 ZPP_PatientPreferencesSegment 的段，你可能创建 ZPP.1_Dietary 字段和 PD.1 过敏组件与 PD.1.1_FoodGroupAllergy 子组件。</span><span class="sxs-lookup"><span data-stu-id="e521b-122">For example, for the segment named ZPP_PatientPreferencesSegment, you might create a ZPP.1_Dietary field and a PD.1 Allergies component with a PD.1.1_FoodGroupAllergy subcomponent.</span></span> <span data-ttu-id="e521b-123">PD.1.1_FoodGroupAllergy 子组件必须是简单的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e521b-123">The PD.1.1_FoodGroupAllergy subcomponent would have to be a simple data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e521b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="e521b-124">See Also</span></span>  
 <span data-ttu-id="e521b-125">[使用 Z 对象扩展 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="e521b-125">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="e521b-126">[在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="e521b-126">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 <span data-ttu-id="e521b-127">[在架构中创建自定义表](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="e521b-127">[Creating Custom Tables in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span></span>  
 <span data-ttu-id="e521b-128">[扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="e521b-128">[Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span></span>  
 [<span data-ttu-id="e521b-129">处理未声明的 Z 段</span><span class="sxs-lookup"><span data-stu-id="e521b-129">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)