---
title: 管理默认映射器行为使用&lt;mapsource&gt; |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deea839c-e52e-44c6-ac0d-4396dc5b10d8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7b4173d514fcc7c671cfd367f64dfc2726bba72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329502"
---
# <a name="managing-default-mapper-behavior-using-ltmapsourcegt"></a><span data-ttu-id="a1c59-102">管理默认映射器行为使用&lt;mapsource&gt;</span><span class="sxs-lookup"><span data-stu-id="a1c59-102">Managing Default Mapper Behavior Using &lt;mapsource&gt;</span></span>
<span data-ttu-id="a1c59-103">可以通过修改的属性来修改 BizTalk 映射器的某些默认行为**mapsource**直接在映射源 (.btm) 文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="a1c59-103">You can modify certain default behaviors of BizTalk Mapper by modifying attributes of the **mapsource** element directly in a map source (.btm) file.</span></span>  
  
## <a name="optimizing-value-mapping-functoid-code-generation"></a><span data-ttu-id="a1c59-104">优化值映射 Functoid 代码生成</span><span class="sxs-lookup"><span data-stu-id="a1c59-104">Optimizing Value Mapping Functoid Code Generation</span></span>  
 <span data-ttu-id="a1c59-105">当映射器生成 XSLT 代码以调用**值映射**functoid，变量用于存储结果。</span><span class="sxs-lookup"><span data-stu-id="a1c59-105">When the Mapper generates XSLT code to call the **Value Mapping** functoid, a variable is used to store the result.</span></span> <span data-ttu-id="a1c59-106">可以使用**OptimizeValueMapping**标志来优化**值映射**functoid，以便生成一个变量时，才`if`语句的计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="a1c59-106">You can use the **OptimizeValueMapping** flag to optimize the **Value Mapping** functoid so that a variable is generated only when the `if` statement evaluates to `True`.</span></span> <span data-ttu-id="a1c59-107">例如，对于**OptimizeValueMapping**设置为**否**:</span><span class="sxs-lookup"><span data-stu-id="a1c59-107">For example, with **OptimizeValueMapping** set to **No**:</span></span>  
  
```  
<xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 <span data-ttu-id="a1c59-108">此代码可以通过将移动优化**值映射**functoid 调用到的正文`if`语句，确保会发生该调用它时才需要。</span><span class="sxs-lookup"><span data-stu-id="a1c59-108">This code could be optimized by moving the **Value Mapping** functoid invocation into the body of the `if` statement, ensuring that invocation occurs only when it is required.</span></span> <span data-ttu-id="a1c59-109">设置**OptimizeValueMapping**到**是**会产生以下代码：</span><span class="sxs-lookup"><span data-stu-id="a1c59-109">Setting **OptimizeValueMapping** to **Yes** yields the following code:</span></span>  
  
```  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 <span data-ttu-id="a1c59-110">映射器这种优化会自动执行如果您设置**OptimizeValueMapping**的属性**mapsource**到映射源 (.btm) 文件中的元素**是**作为所示：</span><span class="sxs-lookup"><span data-stu-id="a1c59-110">The Mapper does this optimization automatically if you set the **OptimizeValueMapping** attribute of the **mapsource** element in the map source (.btm) file to **Yes** as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="Yes" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
## <a name="accommodating-schemas-with-large-footprints"></a><span data-ttu-id="a1c59-111">适应大型操作痕迹包含以下架构：</span><span class="sxs-lookup"><span data-stu-id="a1c59-111">Accommodating Schemas with Large Footprints</span></span>  
 <span data-ttu-id="a1c59-112">当映射器使用的架构，具有较大的实例的占用空间深且复杂的结构和/或递归节点，测试映射，验证映射，或编译映射可能耗时较长的时间或在最坏的情况，导致"内存不足"错误。</span><span class="sxs-lookup"><span data-stu-id="a1c59-112">When the Mapper is using a schema that has a very large instance footprint with deep complex structures and/or recursive nodes, testing the map, validating the map, or compiling the map could take a long time or, in the worse case, result in an "out of memory" error.</span></span> <span data-ttu-id="a1c59-113">与小型、 复杂的架构以及大型架构，则可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="a1c59-113">This could happen with small, complex schemas as well as with large schemas.</span></span>  
  
 <span data-ttu-id="a1c59-114">复杂的架构的问题是因为，映射器具有到以递归方式加载整个架构树，以查找的节点，具有连接到它们的链接，或者具有**值**设置它们的属性。</span><span class="sxs-lookup"><span data-stu-id="a1c59-114">The problem with complex schemas is due to the fact that the Mapper has to recursively load the entire schema tree looking for nodes that either have links connected to them or have the **Value** property set on them.</span></span> <span data-ttu-id="a1c59-115">您可以通过设置来缓解此问题**GenerateDefaultFixedNodes**标记**mapsource** .btm 文件中的元素**否**所示：</span><span class="sxs-lookup"><span data-stu-id="a1c59-115">You can alleviate this problem by setting the **GenerateDefaultFixedNodes** flag of the **mapsource** element in the .btm files to **No** as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="No" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="a1c59-116">使用此设置，不需要创建与目标架构的每个架构节点相关联的内部编译器节点映射器。</span><span class="sxs-lookup"><span data-stu-id="a1c59-116">With this setting, the Mapper does not need to create internal compiler nodes associated with each schema node of a target schema.</span></span> <span data-ttu-id="a1c59-117">仅链接的节点会考虑由编译器使用。</span><span class="sxs-lookup"><span data-stu-id="a1c59-117">Only linked nodes are taken into account by the compiler.</span></span> <span data-ttu-id="a1c59-118">这大大减少内存消耗，并执行"测试映射"验证映射"操作，编译该映射，或保存映射时提高处理速度。</span><span class="sxs-lookup"><span data-stu-id="a1c59-118">This significantly reduces the memory consumption and speeds up the process when doing a "test map" or "validate map" operation, compiling the map, or saving the map.</span></span>  
  
 <span data-ttu-id="a1c59-119">但是，当**GenerateDefaultFixedNodes**标志设置为**否**，目标架构中设置的默认字段值不会保留在映射生成的实例。</span><span class="sxs-lookup"><span data-stu-id="a1c59-119">However, when the **GenerateDefaultFixedNodes** flag is set to **No**, the default field values set in the target schema are not preserved in the instance produced by the map.</span></span> <span data-ttu-id="a1c59-120">这些值需要在目标实例中时，这是一个问题。</span><span class="sxs-lookup"><span data-stu-id="a1c59-120">This is a problem when these values are required in the target instance.</span></span> <span data-ttu-id="a1c59-121">若要避免此问题，所需的值必须再次设置显式映射中。</span><span class="sxs-lookup"><span data-stu-id="a1c59-121">To circumvent this, the required values have to be set again explicitly in the map.</span></span> <span data-ttu-id="a1c59-122">可以设置**GenerateDefaultFixedNodes**标记，用于**RequiredDefaults**，这意味着所有必需的节点都被考虑在内。</span><span class="sxs-lookup"><span data-stu-id="a1c59-122">You can set the **GenerateDefaultFixedNodes** flag to **RequiredDefaults**, which means that all required nodes are taken into account.</span></span> <span data-ttu-id="a1c59-123">这包括链接的节点、 节点具有默认值，与节点**MinOccurs**属性设置为大于或等于一，且需要其父级的节点。</span><span class="sxs-lookup"><span data-stu-id="a1c59-123">This covers linked nodes, nodes that have default values, nodes with the **MinOccurs** property set to greater than or equal to one, and nodes whose parents are required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1c59-124">在设置后**GenerateDefaultFixedNodes**到**否**或**RequiredDefaults**，你应测试映射，并验证输出是否相同时**GenerateDefaultFixedNodes**设置为其默认值**是**中的所有节点会都考虑由编译器。</span><span class="sxs-lookup"><span data-stu-id="a1c59-124">After you set **GenerateDefaultFixedNodes** to **No** or **RequiredDefaults**, you should test the map and verify that the output is the same as when **GenerateDefaultFixedNodes** is set to its default value of **Yes**, in which all nodes are taken into account by the compiler.</span></span>  
  
## <a name="managing-for-each-usage-with-looping-conditional-and-value-mapping-functoids"></a><span data-ttu-id="a1c59-125">管理的 for-each 用法与循环、 条件、 和值映射 Functoid</span><span class="sxs-lookup"><span data-stu-id="a1c59-125">Managing for-each Usage with Looping, Conditional, and Value Mapping Functoids</span></span>  
 <span data-ttu-id="a1c59-126">当你使用**循环**functoid**条件**functoid，或**值映射**functoid，`xsl:for-each`语句生成在编译的映射。</span><span class="sxs-lookup"><span data-stu-id="a1c59-126">When you use a **Looping** functoid, a **Conditional** functoid, or a **Value Mapping** functoid, an `xsl:for-each` statement is generated in the compiled map.</span></span> <span data-ttu-id="a1c59-127">如果目标架构的子字段不受限制的最大出现次数，`xsl:for-each`语句会放在子字段。</span><span class="sxs-lookup"><span data-stu-id="a1c59-127">If the child field of the destination schema has unbounded maximum occurrences, the `xsl:for-each` statement is put at the child field.</span></span> <span data-ttu-id="a1c59-128">如果子字段不具有不受限制的最大出现次数，`xsl:for-each`语句会放在子字段的父字段。</span><span class="sxs-lookup"><span data-stu-id="a1c59-128">If the child field does not have unbounded maximum occurrences, the `xsl:for-each` statement is put at the parent field of the child field.</span></span>  
  
 <span data-ttu-id="a1c59-129">但是，因为的位置`xsl:for-each`语句会影响映射结果，你可能想`xsl:for-each`语句放在子字段的目标架构，而不考虑是否最大出现次数的子字段设置为**1**。</span><span class="sxs-lookup"><span data-stu-id="a1c59-129">However, because the location of the `xsl:for-each` statement affects the map result, you may want the `xsl:for-each` statement to be put at the child field of the destination schema, regardless of whether the maximum occurrence of the child field is set to **1**.</span></span>  
  
 <span data-ttu-id="a1c59-130">您可以控制的放置`xsl:for-each`通过修改的值的语句**TreatElementsAsRecords**属性映射 (.btm) 文件中所示：</span><span class="sxs-lookup"><span data-stu-id="a1c59-130">You can control the placement of the `xsl:for-each` statement by modifying the value of the **TreatElementsAsRecords** attribute in the map (.btm) file as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="a1c59-131">如果此属性设置为**是**，则`xsl:for-each`语句会放在目标架构，而不考虑是否最大出现次数的子字段设置为的子字段**1**。</span><span class="sxs-lookup"><span data-stu-id="a1c59-131">When this attribute is set to **Yes**, the `xsl:for-each` statement is put at the child field of the destination schema, regardless of whether the maximum occurrence of the child field is set to **1**.</span></span>  
  
## <a name="preserving-the-order-when-mapping-a-repeating-sequence-group"></a><span data-ttu-id="a1c59-132">映射重复顺序组时保持顺序</span><span class="sxs-lookup"><span data-stu-id="a1c59-132">Preserving the Order When Mapping a Repeating Sequence Group</span></span>  
 <span data-ttu-id="a1c59-133">XSD 架构中的顺序组不提供循环上下文，因为它们不会出现在消息实例。</span><span class="sxs-lookup"><span data-stu-id="a1c59-133">Sequence groups in XSD schemas do not provide a looping context because they are not represented in the message instance.</span></span> <span data-ttu-id="a1c59-134">不存在循环可能性序列组，映射器编译器不会生成适当的 XSLT 来保持段顺序。</span><span class="sxs-lookup"><span data-stu-id="a1c59-134">Without looping possibilities on the sequence group, the Mapper compiler does not generate the appropriate XSLT to maintain the segment order.</span></span> <span data-ttu-id="a1c59-135">因此，在输入实例中存在的相关上下文是丢失，从而导致输出实例无法用于进一步处理取决于相关上下文。</span><span class="sxs-lookup"><span data-stu-id="a1c59-135">As a result, relative context that is present in the input instance is lost, which makes the output instances useless for further processing that depends on the relative context.</span></span>  
  
 <span data-ttu-id="a1c59-136">可以使用**如 PreserveSequenceOrder**标志来保持纪录顺序映射重复时序列化到另一重复顺序。</span><span class="sxs-lookup"><span data-stu-id="a1c59-136">You can use the **PreserveSequenceOrder** flag to maintain record order when mapping a repeating sequence to another repeating sequence.</span></span> <span data-ttu-id="a1c59-137">默认情况下，标志的值设置为**否**若要保留的前面部分中创建的现有映射的功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]标志不存在的版本。</span><span class="sxs-lookup"><span data-stu-id="a1c59-137">By default, the value of the flag is set to **No** to preserve the functionality of existing maps created in earlier [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versions where the flag is not present.</span></span> <span data-ttu-id="a1c59-138">在新创建的映射，该标志将会显示其值设置为**否**。</span><span class="sxs-lookup"><span data-stu-id="a1c59-138">In the newly created maps, the flag will be present with its value set to **No**.</span></span> <span data-ttu-id="a1c59-139">若要保持段顺序，您必须显式将值设置为**是**在.btm 文件所示：</span><span class="sxs-lookup"><span data-stu-id="a1c59-139">To maintain segment order, you must explicitly set the value to **Yes** in the .btm files as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" PreserveSequenceOrder="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="a1c59-140">下面是一个输入的实例示例：</span><span class="sxs-lookup"><span data-stu-id="a1c59-140">The following is a sample input instance:</span></span>  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
 <span data-ttu-id="a1c59-141">与**如 PreserveSequenceOrder**标志设置为**否**，输出实例将如下所示：</span><span class="sxs-lookup"><span data-stu-id="a1c59-141">With the **PreserveSequenceOrder** flag set to **No**, the output instance will look like the following:</span></span>  
  
```  
<Name>Person1</Name>  
<Name>Person2</Name>  
<Gender>Male</Gender>  
<Gender>Female</Gender>  
<Address>Bellevue</Address>  
<Address>Redmond</Address>  
```  
  
 <span data-ttu-id="a1c59-142">与**如 PreserveSequenceOrder**标志设置为**是**，输出实例将如下所示：</span><span class="sxs-lookup"><span data-stu-id="a1c59-142">With the **PreserveSequenceOrder** flag set to **Yes**, the output instance will look like the following:</span></span>  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1c59-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1c59-143">See Also</span></span>  
 [<span data-ttu-id="a1c59-144">使用 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="a1c59-144">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)