---
title: "创建声明的 Z 段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Z objects, creating segments
- segments, creating Z segments [Z objects]
- Z segments, creating
- creating, Z segments [Z objects]
ms.assetid: afd1b7b7-089e-4c6a-a063-e708431bb888
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dae9148547f527d29238b6080cd499be8da7b7e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-declared-z-segments"></a><span data-ttu-id="fa564-102">创建声明的 Z 段</span><span class="sxs-lookup"><span data-stu-id="fa564-102">Creating Declared Z Segments</span></span>
<span data-ttu-id="fa564-103">你可以在任何级别 （而不像未声明 Z 段，必须多方的消息，后面的正文部分的最后一部分） 架构创建声明的 Z 段。</span><span class="sxs-lookup"><span data-stu-id="fa564-103">You can create declared Z segments at any level of a schema (unlike undeclared Z segments, which must be the last part of a multi-party message, following the body part).</span></span>  
  
### <a name="to-create-a-z-segment-in-biztalk-editor"></a><span data-ttu-id="fa564-104">创建 BizTalk 编辑器中的 Z 段</span><span class="sxs-lookup"><span data-stu-id="fa564-104">To create a Z segment in BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="fa564-105">在解决方案资源管理器的 Visual Studio 中，右键单击你想要添加一个 Z 段中，，然后单击的架构**打开**。</span><span class="sxs-lookup"><span data-stu-id="fa564-105">In Solution Explorer of Visual Studio, right-click the schema to which you want to add a Z segment, and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="fa564-106">在 BizTalk 编辑器中，右键单击包含架构的名称的节点，指向**插入架构节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="fa564-106">In BizTalk Editor, right-click the node with the name of the schema, point to **Insert Schema Node**, and then click **Child Record**.</span></span>  
  
3.  <span data-ttu-id="fa564-107">名称名称开头三个字母数字数字，字母都大写，其中在"Z"的第一个数字的记录。</span><span class="sxs-lookup"><span data-stu-id="fa564-107">Name the record starting the name with three alphanumeric digits, in capitals, with the first digit being "Z".</span></span> <span data-ttu-id="fa564-108">（Z 段标记必须包括三个字符。）插入下划线 (_)，然后再添加段的简短说明。</span><span class="sxs-lookup"><span data-stu-id="fa564-108">(The Z segment tag must include three characters.) Insert an underscore (_), and then add a short description of the segment.</span></span> <span data-ttu-id="fa564-109">说明应为一个或一系列文字，不含空格，首字母大写的每个单词的首字母。</span><span class="sxs-lookup"><span data-stu-id="fa564-109">The description should be one or a series of words, without spaces, with the first letter of each word capitalized.</span></span> <span data-ttu-id="fa564-110">最后一个单词应为"段"。</span><span class="sxs-lookup"><span data-stu-id="fa564-110">The last word should be "Segment".</span></span> <span data-ttu-id="fa564-111">（一个示例是"ZPP_PatientPreferencesSegment。）按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="fa564-111">(An example is "ZPP_PatientPreferencesSegment.) Press **Enter**.</span></span>  
  
4.  <span data-ttu-id="fa564-112">在属性窗格中，键入的 Z 段中，所需的属性包括**数据结构类型**（架构名称或 xsd:anyType） **Max Occurs**，和**最小出现次数**。</span><span class="sxs-lookup"><span data-stu-id="fa564-112">In the Properties pane, type the properties you want for the Z segment, including **Data Structure Type** (schema name or xsd:anyType), **Max Occurs**, and **Min Occurs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fa564-113">如果为记录输入数据结构类型，你将无法将子字段元素添加。</span><span class="sxs-lookup"><span data-stu-id="fa564-113">If you enter a data structure type for the record, you will not be able to add a child field element.</span></span>  
  
5.  <span data-ttu-id="fa564-114">在 BizTalk 编辑器中，右键单击 Z 段的名称，指向**插入架构节点**，然后单击**子字段元素**。</span><span class="sxs-lookup"><span data-stu-id="fa564-114">In BizTalk Editor, right-click the name of the Z segment, point to **Insert Schema Node**, then click **Child Field Element**.</span></span>  
  
6.  <span data-ttu-id="fa564-115">键入字段的名称，名称开头段名称后, 跟一个句点和跟下划线，然后选择字段的简短说明的字段数的前三个数字。</span><span class="sxs-lookup"><span data-stu-id="fa564-115">Type the name of the field, starting the name with the first three digits of the segment name, followed by a period and the number of the field, followed by an underscore and then a short description of the field.</span></span> <span data-ttu-id="fa564-116">说明应为一个或一系列文字，不含空格，首字母大写的每个单词的首字母。</span><span class="sxs-lookup"><span data-stu-id="fa564-116">The description should be one or a series of words, without spaces, with the first letter of each word capitalized.</span></span> <span data-ttu-id="fa564-117">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="fa564-117">Press **Enter**.</span></span>  
  
7.  <span data-ttu-id="fa564-118">在属性窗格中，键入的 Z 段中，所需的属性包括**数据类型**， **Nillable**，**固定**， **Max Occurs**，和**最小出现次数**。</span><span class="sxs-lookup"><span data-stu-id="fa564-118">In the Properties pane, type the properties you want for the Z segment, including **Data Type**, **Nillable**, **Fixed**, **Max Occurs**, and **Min Occurs**.</span></span>  
  
8.  <span data-ttu-id="fa564-119">若要创建具有组件的字段，请创建为一个记录，该字段，然后创建该记录每个组件的子元素。</span><span class="sxs-lookup"><span data-stu-id="fa564-119">To create a field with components, create the field as a record, and then create a child element of that record for each component.</span></span> <span data-ttu-id="fa564-120">若要创建子组件的字段，创建字段和组件作为记录，并且这些子组件作为子元素。</span><span class="sxs-lookup"><span data-stu-id="fa564-120">To create a field with subcomponents, create the field and components as records, and the subcomponents as child elements.</span></span> <span data-ttu-id="fa564-121">请注意，子组件不能为复合数据类型。</span><span class="sxs-lookup"><span data-stu-id="fa564-121">Note that subcomponents cannot be composite data types.</span></span> <span data-ttu-id="fa564-122">例如，对于名为 ZPP_PatientPreferencesSegment 段，你可能需要创建 ZPP.1_Dietary 字段和 PD.1 过敏组件与 PD.1.1_FoodGroupAllergy 子组件。</span><span class="sxs-lookup"><span data-stu-id="fa564-122">For example, for the segment named ZPP_PatientPreferencesSegment, you might create a ZPP.1_Dietary field and a PD.1 Allergies component with a PD.1.1_FoodGroupAllergy subcomponent.</span></span> <span data-ttu-id="fa564-123">PD.1.1_FoodGroupAllergy 子组件都是一个简单的数据类型。</span><span class="sxs-lookup"><span data-stu-id="fa564-123">The PD.1.1_FoodGroupAllergy subcomponent would have to be a simple data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa564-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa564-124">See Also</span></span>  
 <span data-ttu-id="fa564-125">[扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="fa564-125">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="fa564-126">[在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="fa564-126">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 <span data-ttu-id="fa564-127">[在架构中创建自定义的表](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="fa564-127">[Creating Custom Tables in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span></span>  
 <span data-ttu-id="fa564-128">[扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="fa564-128">[Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span></span>  
 [<span data-ttu-id="fa564-129">处理未声明的 Z 段</span><span class="sxs-lookup"><span data-stu-id="fa564-129">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)