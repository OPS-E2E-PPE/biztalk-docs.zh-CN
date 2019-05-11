---
title: 基本和复杂映射操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da864b48-6255-4847-9a6f-13e489e8658d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3ca1e0819de255e70d4f66064f52cdc70f7189c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529159"
---
# <a name="basic-and-complex-mapping-operations"></a><span data-ttu-id="a70bf-102">基本和复杂映射操作</span><span class="sxs-lookup"><span data-stu-id="a70bf-102">Basic and Complex Mapping Operations</span></span>
<span data-ttu-id="a70bf-103">BizTalk 映射器为各种映射方案范围从简单的父子树类型操作到包含循环记录和层次结构的详细又复杂的操作提供解决方案。</span><span class="sxs-lookup"><span data-stu-id="a70bf-103">BizTalk Mapper provides solutions for a variety of mapping scenarios ranging from simple parent-child tree-type operations to detailed, complex operations involving looping records and hierarchies.</span></span> <span data-ttu-id="a70bf-104">映射方案的复杂性取决于您的首选项和业务需求 — XML 架构定义 (XSD) 语言提供了相当大的灵活性，在定义结构化的格式。</span><span class="sxs-lookup"><span data-stu-id="a70bf-104">The complexity of a mapping scenario depends on your preferences and business needs—XML Schema definition (XSD) language gives you considerable flexibility in defining structured formats.</span></span> <span data-ttu-id="a70bf-105">几乎所有映射方案都分为两个类别之一： 基本映射和复杂映射。</span><span class="sxs-lookup"><span data-stu-id="a70bf-105">Almost all mapping scenarios fall into one of two categories: basic mapping and complex mapping.</span></span>  
  
## <a name="basic-mapping"></a><span data-ttu-id="a70bf-106">基本映射</span><span class="sxs-lookup"><span data-stu-id="a70bf-106">Basic Mapping</span></span>  
 <span data-ttu-id="a70bf-107">基本映射是映射的最常见的可以创建类型。</span><span class="sxs-lookup"><span data-stu-id="a70bf-107">Basic mapping is the most common type of mapping you can create.</span></span> <span data-ttu-id="a70bf-108">在基本映射中，输入和输出项具有一对一的关系。</span><span class="sxs-lookup"><span data-stu-id="a70bf-108">In a basic map, input and output items have a one-to-one relationship.</span></span> <span data-ttu-id="a70bf-109">输入的项映射到一个且只有一个输出项。</span><span class="sxs-lookup"><span data-stu-id="a70bf-109">An input item maps to one and only one output item.</span></span> <span data-ttu-id="a70bf-110">尽管许多类型的转换和转换都使用基本映射，例如，使用多个可能*functoid*和级联 functoid 来处理要复制的值，基础方案仍保持相对简单。</span><span class="sxs-lookup"><span data-stu-id="a70bf-110">Although many types of transformations and translations are possible with basic mapping, such as using multiple *functoids* and cascading functoids to manipulate the value being copied, the underlying scenario remains relatively simple.</span></span> <span data-ttu-id="a70bf-111">基本映射操作还包括来自两个不同父记录 （仅出现一次） 到目标架构中的单个父记录下的字段的字段映射。</span><span class="sxs-lookup"><span data-stu-id="a70bf-111">Basic mapping operations also include mapping fields from two different parent records (occurring only once) to fields under a single parent record in the destination schema.</span></span>  
  
## <a name="complex-mapping"></a><span data-ttu-id="a70bf-112">复杂的映射</span><span class="sxs-lookup"><span data-stu-id="a70bf-112">Complex Mapping</span></span>  
 <span data-ttu-id="a70bf-113">复杂映射涉及记录或字段的单个实例出现多次**记录**或**Field 元素**架构树中的节点。</span><span class="sxs-lookup"><span data-stu-id="a70bf-113">Complex mapping involves records or fields that occur multiple times for a single instance of the **Record** or **Field Element** node in the schema tree.</span></span> <span data-ttu-id="a70bf-114">这些节点将其**Max Occurs**属性设置为一个值大于一 (1)，该值指示实例消息中可能有多个相应元素。</span><span class="sxs-lookup"><span data-stu-id="a70bf-114">Such nodes have their **Max Occurs** property set to a value greater than one (1), indicating there may be more than one corresponding element in an instance message.</span></span> <span data-ttu-id="a70bf-115">当 BizTalk 映射使用此类型的可变计数映射 (也称为*循环*)，可扩展样式表语言 (XSL) 样式表编译器必须能够确定要对其进行循环访问以生成的适当循环路径所需的输出。</span><span class="sxs-lookup"><span data-stu-id="a70bf-115">When a BizTalk map uses this type of variable count mapping (also known as *looping*), the Extensible Stylesheet Language (XSL) style sheet compiler must be able to determine the proper loop path over which to iterate to produce the required output.</span></span>  
  
 <span data-ttu-id="a70bf-116">一般情况下，可以将源架构中的循环记录中的字段链接到目标架构中的循环记录中的字段。</span><span class="sxs-lookup"><span data-stu-id="a70bf-116">In general, you can link a field in a looping record in the source schema to a field in a looping record in the destination schema.</span></span> <span data-ttu-id="a70bf-117">输入的实例消息中的相应元素数决定创建输出实例消息中的元素数。</span><span class="sxs-lookup"><span data-stu-id="a70bf-117">The number of corresponding elements in an input instance message determines the number of elements created in the output instance message.</span></span> <span data-ttu-id="a70bf-118">源和目标架构，请考虑从示例具有以下 XSD 片断。</span><span class="sxs-lookup"><span data-stu-id="a70bf-118">Consider the following XSD fragments from example source and destination schemas.</span></span>  
  
### <a name="source-schema-fragment"></a><span data-ttu-id="a70bf-119">源架构片断</span><span class="sxs-lookup"><span data-stu-id="a70bf-119">Source Schema Fragment</span></span>  
  
```  
<xs:element minOccurs="1" maxOccurs="5"  
            name="SrcLoopingRecord">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="" type="xs:string" />   
      <xs:element name="" type="xs:integer" />   
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
  
```  
  
### <a name="destination-schema-fragment"></a><span data-ttu-id="a70bf-120">目标架构片断</span><span class="sxs-lookup"><span data-stu-id="a70bf-120">Destination Schema Fragment</span></span>  
  
```  
<xs:element minOccurs="0" maxOccurs="unbounded"  
            name="DstLoopingRecord">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="" type="xs:string" />   
      <xs:element name="" type="xs:integer" />   
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
  
```  
  
 <span data-ttu-id="a70bf-121">在这些片断中：</span><span class="sxs-lookup"><span data-stu-id="a70bf-121">In these fragments:</span></span>  
  
- <span data-ttu-id="a70bf-122">**SrcLoopingRecord**、 一个**记录**输入的实例消息中的节点可出现一到五次。</span><span class="sxs-lookup"><span data-stu-id="a70bf-122">**SrcLoopingRecord**, a **Record** node in input instance messages, can occur from one to five times.</span></span> <span data-ttu-id="a70bf-123">它还包含子级**Field 元素**节点**Field1** （字符串） 和**Field2** （整数） 出现一次为其父级的每个实例。</span><span class="sxs-lookup"><span data-stu-id="a70bf-123">It also contains the child **Field Element** nodes **Field1** (a string) and **Field2** (an integer) that occur once for each instance of their parent.</span></span>  
  
- <span data-ttu-id="a70bf-124">**DstLoopingRecord**、 一个**记录**输出实例消息中的节点可以出现零 (0) 或时间，不受限制的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a70bf-124">**DstLoopingRecord**, a **Record** node in output instance messages, can occur zero (0) or more times, unbounded.</span></span> <span data-ttu-id="a70bf-125">它还包含子级**Field 元素**节点**FieldA** （字符串） 和**FieldB** （整数） 出现一次为其父级的每个实例。</span><span class="sxs-lookup"><span data-stu-id="a70bf-125">It also contains the child **Field Element** nodes **FieldA** (a string) and **FieldB** (an integer) that occur once for each instance of their parent.</span></span>  
  
  <span data-ttu-id="a70bf-126">假定 Field1 映射到 FieldA、 将 Field2 映射到 FieldB，并且以下片段中的输入的实例消息已处理相应的映射，将生成的以下片段中的输出实例消息。</span><span class="sxs-lookup"><span data-stu-id="a70bf-126">Assuming that Field1 is mapped to FieldA and Field2 is mapped to FieldB, and that the following fragment from an input instance message has processed those mappings, the following fragment from an output instance message would be produced.</span></span>  
  
### <a name="input-instance-message-fragment"></a><span data-ttu-id="a70bf-127">输入的实例消息片断</span><span class="sxs-lookup"><span data-stu-id="a70bf-127">Input Instance Message Fragment</span></span>  
  
```  
<SrcLoopingRecord>  
    <Field1>A string</Field1>  
    <Field2>10</Field2>  
</SrcLoopingRecord>  
<SrcLoopingRecord>  
    <Field1>Another string</Field1>  
    <Field2>11</Field2>  
</SrcLoopingRecord>  
<SrcLoopingRecord>  
    <Field1>A ball of string</Field1>  
    <Field2>12</Field2>  
</SrcLoopingRecord>  
```  
  
### <a name="output-instance-message-fragment"></a><span data-ttu-id="a70bf-128">输出实例消息片断</span><span class="sxs-lookup"><span data-stu-id="a70bf-128">Output Instance Message Fragment</span></span>  
  
```  
<DstLoopingRecord>  
    <FieldA>A string</FieldA>  
    <FieldB>10</FieldB>  
</DstLoopingRecord>  
<DstLoopingRecord>  
  <FieldA>Another string</FieldA>  
  <FieldB>11</FieldB>  
</DstLoopingRecord>  
<DstLoopingRecord>  
    <FieldA>A ball of string</FieldA>  
    <FieldB>12</FieldB>  
</DstLoopingRecord>  
```  
  
 <span data-ttu-id="a70bf-129">次数**SrcLoopingRecord**输入的实例消息 (3) 中的元素可确定的次数**DstLoopingRecord**输出实例消息中的元素。</span><span class="sxs-lookup"><span data-stu-id="a70bf-129">The number of occurrences of the **SrcLoopingRecord** element in the input instance message (3) determines the number of occurrences of the **DstLoopingRecord** element in the output instance message.</span></span>  
  
 <span data-ttu-id="a70bf-130">映射的 BizTalk 映射器不支持的类型是使用多个循环路径。</span><span class="sxs-lookup"><span data-stu-id="a70bf-130">A type of mapping not supported by BizTalk Mapper is the use of multiple loop paths.</span></span> <span data-ttu-id="a70bf-131">此类型的映射涉及源架构映射到目标架构中的单个循环记录中的字段中的两个或多个循环记录中的字段。</span><span class="sxs-lookup"><span data-stu-id="a70bf-131">This type of mapping involves fields from two or more looping records in the source schema being mapped to fields within a single looping record in the destination schema.</span></span> <span data-ttu-id="a70bf-132">这会带来一个问题 — 没有有效的方法可确定要生成输出实例消息中的元素数。</span><span class="sxs-lookup"><span data-stu-id="a70bf-132">This presents a problem—there is no effective way to determine the number of elements to produce in the output instance message.</span></span> <span data-ttu-id="a70bf-133">多个循环路径会导致映射编译警告，指出目标节点具有多个源循环路径。</span><span class="sxs-lookup"><span data-stu-id="a70bf-133">Multiple loop paths result in a map compilation warning indicating that the destination node has multiple source loop paths.</span></span> <span data-ttu-id="a70bf-134">但是，这只是一个警告，并且第一个源循环路径中的迭代数用于确定生成输出实例消息中的元素数量。</span><span class="sxs-lookup"><span data-stu-id="a70bf-134">However, this is only a warning, and the number of iterations in the first source loop path is used to determine the number of elements produced in the output instance message.</span></span> <span data-ttu-id="a70bf-135">可能需要显式控制循环行为，通过使用**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="a70bf-135">You can take explicit control of looping behavior by using the **Looping** functoid.</span></span>  
  
 <span data-ttu-id="a70bf-136">Microsoft BizTalk Server 引入了一种新的循环调用表驱动循环。</span><span class="sxs-lookup"><span data-stu-id="a70bf-136">Microsoft BizTalk Server introduced a new kind of looping called table-driven looping.</span></span> <span data-ttu-id="a70bf-137">表驱动循环时，输出实例消息需要基于输入的实例消息中的数据，结合一个或多个常数、 来自源架构或 functoid 的链接。</span><span class="sxs-lookup"><span data-stu-id="a70bf-137">Table-driven looping is useful when your output instance message needs to be based on data from the input instance message, combined with one or more constants, links from the source schema, or functoids.</span></span> <span data-ttu-id="a70bf-138">在这种情况下，输出实例消息可以有根据是组合使用不同的常量，或根据从输入的实例消息中的多个记录的数据的输入的实例消息中的单个记录中的数据的多个记录。</span><span class="sxs-lookup"><span data-stu-id="a70bf-138">In such cases, the output instance message can have multiple records based on data from a single record in the input instance message that is combined with different constants, or based on data coming from multiple records in the input instance message.</span></span> <span data-ttu-id="a70bf-139">有关表驱动循环使用**表循环**并**表提取程序**functoid，请参阅[表循环和表提取程序 Functoid](../core/table-looping-and-table-extractor-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="a70bf-139">For more information about table-driven looping using the **Table Looping** and **Table Extractor** functoids, see [Table Looping and Table Extractor Functoids](../core/table-looping-and-table-extractor-functoids.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a70bf-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="a70bf-140">See Also</span></span>  
 <span data-ttu-id="a70bf-141">[映射](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="a70bf-141">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="a70bf-142">使用 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="a70bf-142">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)