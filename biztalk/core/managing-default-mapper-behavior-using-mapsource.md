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
# <a name="managing-default-mapper-behavior-using-ltmapsourcegt"></a>管理默认映射器行为使用&lt;mapsource&gt;
可以通过修改的属性来修改 BizTalk 映射器的某些默认行为**mapsource**直接在映射源 (.btm) 文件中的元素。  
  
## <a name="optimizing-value-mapping-functoid-code-generation"></a>优化值映射 Functoid 代码生成  
 当映射器生成 XSLT 代码以调用**值映射**functoid，变量用于存储结果。 可以使用**OptimizeValueMapping**标志来优化**值映射**functoid，以便生成一个变量时，才`if`语句的计算结果为`True`。 例如，对于**OptimizeValueMapping**设置为**否**:  
  
```  
<xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 此代码可以通过将移动优化**值映射**functoid 调用到的正文`if`语句，确保会发生该调用它时才需要。 设置**OptimizeValueMapping**到**是**会产生以下代码：  
  
```  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 映射器这种优化会自动执行如果您设置**OptimizeValueMapping**的属性**mapsource**到映射源 (.btm) 文件中的元素**是**作为所示：  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="Yes" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
## <a name="accommodating-schemas-with-large-footprints"></a>适应大型操作痕迹包含以下架构：  
 当映射器使用的架构，具有较大的实例的占用空间深且复杂的结构和/或递归节点，测试映射，验证映射，或编译映射可能耗时较长的时间或在最坏的情况，导致"内存不足"错误。 与小型、 复杂的架构以及大型架构，则可能发生这种情况。  
  
 复杂的架构的问题是因为，映射器具有到以递归方式加载整个架构树，以查找的节点，具有连接到它们的链接，或者具有**值**设置它们的属性。 您可以通过设置来缓解此问题**GenerateDefaultFixedNodes**标记**mapsource** .btm 文件中的元素**否**所示：  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="No" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 使用此设置，不需要创建与目标架构的每个架构节点相关联的内部编译器节点映射器。 仅链接的节点会考虑由编译器使用。 这大大减少内存消耗，并执行"测试映射"验证映射"操作，编译该映射，或保存映射时提高处理速度。  
  
 但是，当**GenerateDefaultFixedNodes**标志设置为**否**，目标架构中设置的默认字段值不会保留在映射生成的实例。 这些值需要在目标实例中时，这是一个问题。 若要避免此问题，所需的值必须再次设置显式映射中。 可以设置**GenerateDefaultFixedNodes**标记，用于**RequiredDefaults**，这意味着所有必需的节点都被考虑在内。 这包括链接的节点、 节点具有默认值，与节点**MinOccurs**属性设置为大于或等于一，且需要其父级的节点。  
  
> [!NOTE]
>  在设置后**GenerateDefaultFixedNodes**到**否**或**RequiredDefaults**，你应测试映射，并验证输出是否相同时**GenerateDefaultFixedNodes**设置为其默认值**是**中的所有节点会都考虑由编译器。  
  
## <a name="managing-for-each-usage-with-looping-conditional-and-value-mapping-functoids"></a>管理的 for-each 用法与循环、 条件、 和值映射 Functoid  
 当你使用**循环**functoid**条件**functoid，或**值映射**functoid，`xsl:for-each`语句生成在编译的映射。 如果目标架构的子字段不受限制的最大出现次数，`xsl:for-each`语句会放在子字段。 如果子字段不具有不受限制的最大出现次数，`xsl:for-each`语句会放在子字段的父字段。  
  
 但是，因为的位置`xsl:for-each`语句会影响映射结果，你可能想`xsl:for-each`语句放在子字段的目标架构，而不考虑是否最大出现次数的子字段设置为**1**。  
  
 您可以控制的放置`xsl:for-each`通过修改的值的语句**TreatElementsAsRecords**属性映射 (.btm) 文件中所示：  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 如果此属性设置为**是**，则`xsl:for-each`语句会放在目标架构，而不考虑是否最大出现次数的子字段设置为的子字段**1**。  
  
## <a name="preserving-the-order-when-mapping-a-repeating-sequence-group"></a>映射重复顺序组时保持顺序  
 XSD 架构中的顺序组不提供循环上下文，因为它们不会出现在消息实例。 不存在循环可能性序列组，映射器编译器不会生成适当的 XSLT 来保持段顺序。 因此，在输入实例中存在的相关上下文是丢失，从而导致输出实例无法用于进一步处理取决于相关上下文。  
  
 可以使用**如 PreserveSequenceOrder**标志来保持纪录顺序映射重复时序列化到另一重复顺序。 默认情况下，标志的值设置为**否**若要保留的前面部分中创建的现有映射的功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]标志不存在的版本。 在新创建的映射，该标志将会显示其值设置为**否**。 若要保持段顺序，您必须显式将值设置为**是**在.btm 文件所示：  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" PreserveSequenceOrder="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 下面是一个输入的实例示例：  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
 与**如 PreserveSequenceOrder**标志设置为**否**，输出实例将如下所示：  
  
```  
<Name>Person1</Name>  
<Name>Person2</Name>  
<Gender>Male</Gender>  
<Gender>Female</Gender>  
<Address>Bellevue</Address>  
<Address>Redmond</Address>  
```  
  
 与**如 PreserveSequenceOrder**标志设置为**是**，输出实例将如下所示：  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md)