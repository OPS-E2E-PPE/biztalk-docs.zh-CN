---
title: 管理默认映射器行为使用&lt;mapsource&gt; |Microsoft 文档
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
ms.openlocfilehash: 44e2e66350709c6b857d875ec3979fe3f7059648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263373"
---
# <a name="managing-default-mapper-behavior-using-ltmapsourcegt"></a>管理默认映射器行为使用&lt;mapsource&gt;
你可以通过修改的属性来修改 BizTalk 映射程序的某些默认行为**mapsource**直接映射 (.btm) 源文件中的元素。  
  
## <a name="optimizing-value-mapping-functoid-code-generation"></a>优化“值映射”Functoid 代码生成  
 当映射器会生成 XSLT 代码来调用**值映射**functoid，变量用来存储结果。 你可以使用**OptimizeValueMapping**标志来优化**值映射**functoid，以便生成一个变量时，才`if`语句的计算结果为`True`。 例如，对于**OptimizeValueMapping**设置为**否**:  
  
```  
<xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 无法通过移动优化此代码**值映射**主体 functoid 调用`if`语句中，确保调用发生它时才需要。 设置**OptimizeValueMapping**到**是**生成的以下代码：  
  
```  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 映射器会此优化自动如果你设置**OptimizeValueMapping**属性**mapsource**源文件中的元素映射 (.btm) 到**是**作为所示：  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="Yes" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
## <a name="accommodating-schemas-with-large-footprints"></a>适应占用较大空间的架构  
 如果映射器使用的架构具有较大的实例占用空间、较深且复杂的结构和/或递归节点，则对映射进行测试、验证和编译需要较长的时间，甚至有可能导致“内存不足”错误的出现。 较小但是复杂的架构以及较大的架构都可能发生这种情况。  
  
 复杂架构的问题是因为，映射器具有到以递归方式加载整个架构树，以查找的节点，或者具有连接至它们的链接，或者具有**值**在其上设置的属性。 您可以通过设置来缓解此问题**GenerateDefaultFixedNodes**标志的**mapsource** .btm 文件中的元素**否**如所示：  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="No" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 通过此设置，映射器不再需要创建与目标架构的每一架构节点相关联的内部编译器节点。 编译器仅会考虑链接节点。 这样可使执行“测试映射”或“验证映射”操作、编辑映射或保存映射时的内存占用量大大减少，并显著提高处理速度。  
  
 但是，当**GenerateDefaultFixedNodes**标志设置为**否**，目标架构中设置的默认字段值不会保留在实例中生成的映射。 如果这些值必须保留在目标实例内，这样处理将引发问题。 要避免此问题，必须在映射中重新显式设置所需的值。 你可以设置**GenerateDefaultFixedNodes**标志切换为**RequiredDefaults**，这意味着所有必需的节点被予以考虑。 这包含链接的节点，节点具有默认值，使用节点**MinOccurs**属性设置为大于或等于 1，且其父项所需的节点。  
  
> [!NOTE]
>  设置之后**GenerateDefaultFixedNodes**到**否**或**RequiredDefaults**，应测试映射，并验证输出是否与时相同**GenerateDefaultFixedNodes**设置它的默认值为**是**中的所有节点已都考虑到编译器。  
  
## <a name="managing-for-each-usage-with-looping-conditional-and-value-mapping-functoids"></a>管理“循环”、“条件”和“值映射”Functoid 的 For-each 用法  
 当你使用**循环**functoid，**条件**functoid，或**值映射**functoid，`xsl:for-each`编译映射中生成语句。 如果目标架构的子字段具有不受限制的最大匹配数，`xsl:for-each`语句放在子字段。 如果子字段不具有不受限制的最大匹配数，`xsl:for-each`语句放在子字段的父字段。  
  
 但是，因为的位置`xsl:for-each`语句都会影响映射结果中，你可能想`xsl:for-each`语句放在目标架构，而不考虑子字段的最大匹配项是否设置为的子字段**1**。  
  
 你可以控制的放置位置`xsl:for-each`通过修改的值的语句**TreatElementsAsRecords**属性映射 (.btm) 文件中所示：  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 当此属性设置为**是**、`xsl:for-each`语句放在目标架构，而不考虑子字段的最大匹配项是否设置为的子字段**1**。  
  
## <a name="preserving-the-order-when-mapping-a-repeating-sequence-group"></a>在映射重复顺序组时保持顺序  
 XSD 架构中的顺序组不提供循环上下文，因为它们未以消息实例表示。 由于顺序组不存在循环可能性，映射器的编译器不会生成适当的 XSLT 来保持段的顺序。 因此，输入实例中的相关上下文会丢失，从而导致输出实例无法用于依赖于相关上下文的进一步处理。  
  
 你可以使用**PreserveSequenceOrder**标志来维护记录的顺序映射重复时序列化到另一个重复的序列。 默认情况下，标志的值设置为**否**以保留的更早版本中创建的现有映射功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]版本标志不存在。 在新创建的映射，该标志将会显示其值设置为**否**。 若要维护段顺序，你必须显式将值设置为**是**中.btm 文件所示：  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" PreserveSequenceOrder="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 以下为一个输入实例示例：  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
 与**PreserveSequenceOrder**标志设置为**否**，输出实例将如下所示：  
  
```  
<Name>Person1</Name>  
<Name>Person2</Name>  
<Gender>Male</Gender>  
<Gender>Female</Gender>  
<Address>Bellevue</Address>  
<Address>Redmond</Address>  
```  
  
 与**PreserveSequenceOrder**标志设置为**是**，输出实例将如下所示：  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
## <a name="see-also"></a>另请参阅  
 [创建使用 BizTalk 映射程序图](../core/creating-maps-using-biztalk-mapper.md)