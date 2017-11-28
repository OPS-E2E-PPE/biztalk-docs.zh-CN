---
title: "管理默认映射器行为使用&lt;mapsource&gt; |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: deea839c-e52e-44c6-ac0d-4396dc5b10d8
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44e2e66350709c6b857d875ec3979fe3f7059648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-default-mapper-behavior-using-ltmapsourcegt"></a><span data-ttu-id="5f368-102">管理默认映射器行为使用&lt;mapsource&gt;</span><span class="sxs-lookup"><span data-stu-id="5f368-102">Managing Default Mapper Behavior Using &lt;mapsource&gt;</span></span>
<span data-ttu-id="5f368-103">你可以通过修改的属性来修改 BizTalk 映射程序的某些默认行为**mapsource**直接映射 (.btm) 源文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="5f368-103">You can modify certain default behaviors of BizTalk Mapper by modifying attributes of the **mapsource** element directly in a map source (.btm) file.</span></span>  
  
## <a name="optimizing-value-mapping-functoid-code-generation"></a><span data-ttu-id="5f368-104">优化“值映射”Functoid 代码生成</span><span class="sxs-lookup"><span data-stu-id="5f368-104">Optimizing Value Mapping Functoid Code Generation</span></span>  
 <span data-ttu-id="5f368-105">当映射器会生成 XSLT 代码来调用**值映射**functoid，变量用来存储结果。</span><span class="sxs-lookup"><span data-stu-id="5f368-105">When the Mapper generates XSLT code to call the **Value Mapping** functoid, a variable is used to store the result.</span></span> <span data-ttu-id="5f368-106">你可以使用**OptimizeValueMapping**标志来优化**值映射**functoid，以便生成一个变量时，才`if`语句的计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="5f368-106">You can use the **OptimizeValueMapping** flag to optimize the **Value Mapping** functoid so that a variable is generated only when the `if` statement evaluates to `True`.</span></span> <span data-ttu-id="5f368-107">例如，对于**OptimizeValueMapping**设置为**否**:</span><span class="sxs-lookup"><span data-stu-id="5f368-107">For example, with **OptimizeValueMapping** set to **No**:</span></span>  
  
```  
<xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 <span data-ttu-id="5f368-108">无法通过移动优化此代码**值映射**主体 functoid 调用`if`语句中，确保调用发生它时才需要。</span><span class="sxs-lookup"><span data-stu-id="5f368-108">This code could be optimized by moving the **Value Mapping** functoid invocation into the body of the `if` statement, ensuring that invocation occurs only when it is required.</span></span> <span data-ttu-id="5f368-109">设置**OptimizeValueMapping**到**是**生成的以下代码：</span><span class="sxs-lookup"><span data-stu-id="5f368-109">Setting **OptimizeValueMapping** to **Yes** yields the following code:</span></span>  
  
```  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 <span data-ttu-id="5f368-110">映射器会此优化自动如果你设置**OptimizeValueMapping**属性**mapsource**源文件中的元素映射 (.btm) 到**是**作为所示：</span><span class="sxs-lookup"><span data-stu-id="5f368-110">The Mapper does this optimization automatically if you set the **OptimizeValueMapping** attribute of the **mapsource** element in the map source (.btm) file to **Yes** as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="Yes" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
## <a name="accommodating-schemas-with-large-footprints"></a><span data-ttu-id="5f368-111">适应占用较大空间的架构</span><span class="sxs-lookup"><span data-stu-id="5f368-111">Accommodating Schemas with Large Footprints</span></span>  
 <span data-ttu-id="5f368-112">如果映射器使用的架构具有较大的实例占用空间、较深且复杂的结构和/或递归节点，则对映射进行测试、验证和编译需要较长的时间，甚至有可能导致“内存不足”错误的出现。</span><span class="sxs-lookup"><span data-stu-id="5f368-112">When the Mapper is using a schema that has a very large instance footprint with deep complex structures and/or recursive nodes, testing the map, validating the map, or compiling the map could take a long time or, in the worse case, result in an "out of memory" error.</span></span> <span data-ttu-id="5f368-113">较小但是复杂的架构以及较大的架构都可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="5f368-113">This could happen with small, complex schemas as well as with large schemas.</span></span>  
  
 <span data-ttu-id="5f368-114">复杂架构的问题是因为，映射器具有到以递归方式加载整个架构树，以查找的节点，或者具有连接至它们的链接，或者具有**值**在其上设置的属性。</span><span class="sxs-lookup"><span data-stu-id="5f368-114">The problem with complex schemas is due to the fact that the Mapper has to recursively load the entire schema tree looking for nodes that either have links connected to them or have the **Value** property set on them.</span></span> <span data-ttu-id="5f368-115">您可以通过设置来缓解此问题**GenerateDefaultFixedNodes**标志的**mapsource** .btm 文件中的元素**否**如所示：</span><span class="sxs-lookup"><span data-stu-id="5f368-115">You can alleviate this problem by setting the **GenerateDefaultFixedNodes** flag of the **mapsource** element in the .btm files to **No** as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="No" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="5f368-116">通过此设置，映射器不再需要创建与目标架构的每一架构节点相关联的内部编译器节点。</span><span class="sxs-lookup"><span data-stu-id="5f368-116">With this setting, the Mapper does not need to create internal compiler nodes associated with each schema node of a target schema.</span></span> <span data-ttu-id="5f368-117">编译器仅会考虑链接节点。</span><span class="sxs-lookup"><span data-stu-id="5f368-117">Only linked nodes are taken into account by the compiler.</span></span> <span data-ttu-id="5f368-118">这样可使执行“测试映射”或“验证映射”操作、编辑映射或保存映射时的内存占用量大大减少，并显著提高处理速度。</span><span class="sxs-lookup"><span data-stu-id="5f368-118">This significantly reduces the memory consumption and speeds up the process when doing a "test map" or "validate map" operation, compiling the map, or saving the map.</span></span>  
  
 <span data-ttu-id="5f368-119">但是，当**GenerateDefaultFixedNodes**标志设置为**否**，目标架构中设置的默认字段值不会保留在实例中生成的映射。</span><span class="sxs-lookup"><span data-stu-id="5f368-119">However, when the **GenerateDefaultFixedNodes** flag is set to **No**, the default field values set in the target schema are not preserved in the instance produced by the map.</span></span> <span data-ttu-id="5f368-120">如果这些值必须保留在目标实例内，这样处理将引发问题。</span><span class="sxs-lookup"><span data-stu-id="5f368-120">This is a problem when these values are required in the target instance.</span></span> <span data-ttu-id="5f368-121">要避免此问题，必须在映射中重新显式设置所需的值。</span><span class="sxs-lookup"><span data-stu-id="5f368-121">To circumvent this, the required values have to be set again explicitly in the map.</span></span> <span data-ttu-id="5f368-122">你可以设置**GenerateDefaultFixedNodes**标志切换为**RequiredDefaults**，这意味着所有必需的节点被予以考虑。</span><span class="sxs-lookup"><span data-stu-id="5f368-122">You can set the **GenerateDefaultFixedNodes** flag to **RequiredDefaults**, which means that all required nodes are taken into account.</span></span> <span data-ttu-id="5f368-123">这包含链接的节点，节点具有默认值，使用节点**MinOccurs**属性设置为大于或等于 1，且其父项所需的节点。</span><span class="sxs-lookup"><span data-stu-id="5f368-123">This covers linked nodes, nodes that have default values, nodes with the **MinOccurs** property set to greater than or equal to one, and nodes whose parents are required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f368-124">设置之后**GenerateDefaultFixedNodes**到**否**或**RequiredDefaults**，应测试映射，并验证输出是否与时相同**GenerateDefaultFixedNodes**设置它的默认值为**是**中的所有节点已都考虑到编译器。</span><span class="sxs-lookup"><span data-stu-id="5f368-124">After you set **GenerateDefaultFixedNodes** to **No** or **RequiredDefaults**, you should test the map and verify that the output is the same as when **GenerateDefaultFixedNodes** is set to its default value of **Yes**, in which all nodes are taken into account by the compiler.</span></span>  
  
## <a name="managing-for-each-usage-with-looping-conditional-and-value-mapping-functoids"></a><span data-ttu-id="5f368-125">管理“循环”、“条件”和“值映射”Functoid 的 For-each 用法</span><span class="sxs-lookup"><span data-stu-id="5f368-125">Managing for-each Usage with Looping, Conditional, and Value Mapping Functoids</span></span>  
 <span data-ttu-id="5f368-126">当你使用**循环**functoid，**条件**functoid，或**值映射**functoid，`xsl:for-each`编译映射中生成语句。</span><span class="sxs-lookup"><span data-stu-id="5f368-126">When you use a **Looping** functoid, a **Conditional** functoid, or a **Value Mapping** functoid, an `xsl:for-each` statement is generated in the compiled map.</span></span> <span data-ttu-id="5f368-127">如果目标架构的子字段具有不受限制的最大匹配数，`xsl:for-each`语句放在子字段。</span><span class="sxs-lookup"><span data-stu-id="5f368-127">If the child field of the destination schema has unbounded maximum occurrences, the `xsl:for-each` statement is put at the child field.</span></span> <span data-ttu-id="5f368-128">如果子字段不具有不受限制的最大匹配数，`xsl:for-each`语句放在子字段的父字段。</span><span class="sxs-lookup"><span data-stu-id="5f368-128">If the child field does not have unbounded maximum occurrences, the `xsl:for-each` statement is put at the parent field of the child field.</span></span>  
  
 <span data-ttu-id="5f368-129">但是，因为的位置`xsl:for-each`语句都会影响映射结果中，你可能想`xsl:for-each`语句放在目标架构，而不考虑子字段的最大匹配项是否设置为的子字段**1**。</span><span class="sxs-lookup"><span data-stu-id="5f368-129">However, because the location of the `xsl:for-each` statement affects the map result, you may want the `xsl:for-each` statement to be put at the child field of the destination schema, regardless of whether the maximum occurrence of the child field is set to **1**.</span></span>  
  
 <span data-ttu-id="5f368-130">你可以控制的放置位置`xsl:for-each`通过修改的值的语句**TreatElementsAsRecords**属性映射 (.btm) 文件中所示：</span><span class="sxs-lookup"><span data-stu-id="5f368-130">You can control the placement of the `xsl:for-each` statement by modifying the value of the **TreatElementsAsRecords** attribute in the map (.btm) file as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="5f368-131">当此属性设置为**是**、`xsl:for-each`语句放在目标架构，而不考虑子字段的最大匹配项是否设置为的子字段**1**。</span><span class="sxs-lookup"><span data-stu-id="5f368-131">When this attribute is set to **Yes**, the `xsl:for-each` statement is put at the child field of the destination schema, regardless of whether the maximum occurrence of the child field is set to **1**.</span></span>  
  
## <a name="preserving-the-order-when-mapping-a-repeating-sequence-group"></a><span data-ttu-id="5f368-132">在映射重复顺序组时保持顺序</span><span class="sxs-lookup"><span data-stu-id="5f368-132">Preserving the Order When Mapping a Repeating Sequence Group</span></span>  
 <span data-ttu-id="5f368-133">XSD 架构中的顺序组不提供循环上下文，因为它们未以消息实例表示。</span><span class="sxs-lookup"><span data-stu-id="5f368-133">Sequence groups in XSD schemas do not provide a looping context because they are not represented in the message instance.</span></span> <span data-ttu-id="5f368-134">由于顺序组不存在循环可能性，映射器的编译器不会生成适当的 XSLT 来保持段的顺序。</span><span class="sxs-lookup"><span data-stu-id="5f368-134">Without looping possibilities on the sequence group, the Mapper compiler does not generate the appropriate XSLT to maintain the segment order.</span></span> <span data-ttu-id="5f368-135">因此，输入实例中的相关上下文会丢失，从而导致输出实例无法用于依赖于相关上下文的进一步处理。</span><span class="sxs-lookup"><span data-stu-id="5f368-135">As a result, relative context that is present in the input instance is lost, which makes the output instances useless for further processing that depends on the relative context.</span></span>  
  
 <span data-ttu-id="5f368-136">你可以使用**PreserveSequenceOrder**标志来维护记录的顺序映射重复时序列化到另一个重复的序列。</span><span class="sxs-lookup"><span data-stu-id="5f368-136">You can use the **PreserveSequenceOrder** flag to maintain record order when mapping a repeating sequence to another repeating sequence.</span></span> <span data-ttu-id="5f368-137">默认情况下，标志的值设置为**否**以保留的更早版本中创建的现有映射功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]版本标志不存在。</span><span class="sxs-lookup"><span data-stu-id="5f368-137">By default, the value of the flag is set to **No** to preserve the functionality of existing maps created in earlier [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versions where the flag is not present.</span></span> <span data-ttu-id="5f368-138">在新创建的映射，该标志将会显示其值设置为**否**。</span><span class="sxs-lookup"><span data-stu-id="5f368-138">In the newly created maps, the flag will be present with its value set to **No**.</span></span> <span data-ttu-id="5f368-139">若要维护段顺序，你必须显式将值设置为**是**中.btm 文件所示：</span><span class="sxs-lookup"><span data-stu-id="5f368-139">To maintain segment order, you must explicitly set the value to **Yes** in the .btm files as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" PreserveSequenceOrder="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="5f368-140">以下为一个输入实例示例：</span><span class="sxs-lookup"><span data-stu-id="5f368-140">The following is a sample input instance:</span></span>  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
 <span data-ttu-id="5f368-141">与**PreserveSequenceOrder**标志设置为**否**，输出实例将如下所示：</span><span class="sxs-lookup"><span data-stu-id="5f368-141">With the **PreserveSequenceOrder** flag set to **No**, the output instance will look like the following:</span></span>  
  
```  
<Name>Person1</Name>  
<Name>Person2</Name>  
<Gender>Male</Gender>  
<Gender>Female</Gender>  
<Address>Bellevue</Address>  
<Address>Redmond</Address>  
```  
  
 <span data-ttu-id="5f368-142">与**PreserveSequenceOrder**标志设置为**是**，输出实例将如下所示：</span><span class="sxs-lookup"><span data-stu-id="5f368-142">With the **PreserveSequenceOrder** flag set to **Yes**, the output instance will look like the following:</span></span>  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f368-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f368-143">See Also</span></span>  
 [<span data-ttu-id="5f368-144">创建使用 BizTalk 映射程序图</span><span class="sxs-lookup"><span data-stu-id="5f368-144">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)