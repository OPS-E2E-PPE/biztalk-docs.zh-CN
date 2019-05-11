---
title: 使用内联 XSLT 和 XSLT 调用模板编写脚本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3168417-3653-4c9e-a09c-184ffdc0ccb2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5df34bc134b9cb842d4ebc0db96f00a3716ee5a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251241"
---
# <a name="scripting-using-inline-xslt-and-xslt-call-templates"></a><span data-ttu-id="afe46-102">使用内联 XSLT 和 XSLT 调用模板编写脚本</span><span class="sxs-lookup"><span data-stu-id="afe46-102">Scripting Using Inline XSLT and XSLT Call Templates</span></span>
<span data-ttu-id="afe46-103">您可以直接编写可扩展样式表语言转换 (XSLT) 样式表中使用**脚本**functoid。</span><span class="sxs-lookup"><span data-stu-id="afe46-103">You can directly write Extensible Stylesheet Language Transformations (XSLT) stylesheets for use in the **Scripting** functoid.</span></span> <span data-ttu-id="afe46-104">这使您可以执行转换，链接和内置 functoid 可能无法表示。</span><span class="sxs-lookup"><span data-stu-id="afe46-104">This enables you to perform transformations, that links and built-in functoids may not be able to represent.</span></span> <span data-ttu-id="afe46-105">有两种类型的 XSLT 脚本： 内联 XSLT 和 XSLT 调用模板。</span><span class="sxs-lookup"><span data-stu-id="afe46-105">There are two kinds of XSLT scripts: inline XSLT and XSLT call templates.</span></span> <span data-ttu-id="afe46-106">在选中**选择脚本类型**下拉列表中的**配置脚本 Functoid**对话框中，示例代码将显示您可以使用。</span><span class="sxs-lookup"><span data-stu-id="afe46-106">When you select either in the **Select script type** dropdown in the **Configure Scripting Functoid** dialog box, sample code appears that you may use.</span></span>  
  
 <span data-ttu-id="afe46-107">内联 XSLT 脚本和内联 XSLT 调用模板可以调用外部程序集中的函数。</span><span class="sxs-lookup"><span data-stu-id="afe46-107">Inline XSLT scripts and inline XSLT call templates may call functions in external assemblies.</span></span> <span data-ttu-id="afe46-108">执行此类调用需要设置**自定义扩展 XML**网格的属性。</span><span class="sxs-lookup"><span data-stu-id="afe46-108">Making such calls requires setting the **Custom Extension XML** property of the grid.</span></span> <span data-ttu-id="afe46-109">有关详细信息，请参阅**自定义扩展 XML （网格属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="afe46-109">For more information, see **Custom Extension XML (Grid Property)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="inline-xslt"></a><span data-ttu-id="afe46-110">内联 XSLT</span><span class="sxs-lookup"><span data-stu-id="afe46-110">Inline XSLT</span></span>  
 <span data-ttu-id="afe46-111">内联 XSLT 脚本只能生成输出。</span><span class="sxs-lookup"><span data-stu-id="afe46-111">An inline XSLT script may only produce output.</span></span> <span data-ttu-id="afe46-112">**脚本**functoid 可能没有任何输入的链接。</span><span class="sxs-lookup"><span data-stu-id="afe46-112">The **Scripting** functoid may not have any input links.</span></span> <span data-ttu-id="afe46-113">该 functoid 必须直接链接到的记录或目标架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="afe46-113">The functoid must also directly link to a record or field in the destination schema.</span></span>  
  
 <span data-ttu-id="afe46-114">此外，该脚本负责创建目标节点及其任何下级结构。</span><span class="sxs-lookup"><span data-stu-id="afe46-114">In addition, the script is responsible for creating the target node and any structures underneath it.</span></span>  
  
 <span data-ttu-id="afe46-115">以下输入的实例消息包含两个元素代表的联系信息。</span><span class="sxs-lookup"><span data-stu-id="afe46-115">The following input instance message contains two elements representing contact information.</span></span>  
  
```  
<ns0:SourceInstance xmlns:ns0="http://SourceInstanceNamespace">  
    <Address>  
        <Contact>Karin Zimprich</Contact>  
        <ContactType>Referral</ContactType>  
    </Address>  
</ns0:SourceInstance>  
```  
  
 <span data-ttu-id="afe46-116">以下内联 XSLT 脚本，在脚本缓冲区中，输入将转换**联系人**并**ContactType**属性字段。</span><span class="sxs-lookup"><span data-stu-id="afe46-116">The following inline XSLT script, entered in the script buffer, converts the **Contact** and **ContactType** fields to attributes.</span></span>  
  
```  
<ContactInfo xmlns:p="http://SourceInstanceNamespace">  
     <xsl:variable name="var:var1" select="/p:SourceInstance/Address/ContactType" />  
     <xsl:attribute name="ContactType">  
          <xsl:value-of select="$var:var1" />  
     </xsl:attribute>  
     <xsl:variable name="var:var2" select="/p:SourceInstance/Address/Contact" />  
     <xsl:attribute name="Contact">  
          <xsl:value-of select="$var:var2" />  
     </xsl:attribute>  
</ContactInfo>  
```  
  
 <span data-ttu-id="afe46-117">该脚本生成以下输出，假定针对前面的输入的实例消息运行时的相应的输出架构。</span><span class="sxs-lookup"><span data-stu-id="afe46-117">The script produces the following output, assuming an appropriate output schema, when run against the preceding input instance message.</span></span>  
  
```  
<ns0:OutInstance xmlns:ns0="http://More_XSLT.Out">  
    <ContactInfo ContactType="Referral" Contact="Karin Zimprich" xmlns:p="http://SourceInstanceNamespace">  
    </ContactInfo>  
</ns0:OutInstance>  
```  
  
 <span data-ttu-id="afe46-118">请注意，不存在指向**脚本**functoid 不会妨碍该 XSLT 脚本从输入的实例消息中获取数据。</span><span class="sxs-lookup"><span data-stu-id="afe46-118">Notice that the absence of links to the **Scripting** functoid does not prevent the XSLT script from getting data from the input instance message.</span></span> <span data-ttu-id="afe46-119">该脚本指定的输入的实例值的路径。</span><span class="sxs-lookup"><span data-stu-id="afe46-119">The script specifies paths to the input instance values.</span></span>  
  
 <span data-ttu-id="afe46-120">有关内联 XSLT 脚本的其他示例，请参阅[XML 工具 （BizTalk Server 示例文件夹）](../core/xml-tools-biztalk-server-samples-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="afe46-120">For another example of an inline XSLT script, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="inline-xslt-call-templates"></a><span data-ttu-id="afe46-121">内联 XSLT 调用模板</span><span class="sxs-lookup"><span data-stu-id="afe46-121">Inline XSLT Call Templates</span></span>  
 <span data-ttu-id="afe46-122">内联 XSLT 脚本，如内联 XSLT 调用模板必须直接连接到目标节点。</span><span class="sxs-lookup"><span data-stu-id="afe46-122">Like an inline XSLT script, an inline XSLT call template must connect directly to a destination node.</span></span> <span data-ttu-id="afe46-123">但是，内联 XSLT 调用模板可能会使用来自源架构和来自其他 functoid 的链接。</span><span class="sxs-lookup"><span data-stu-id="afe46-123">However, an inline XSLT call template may use links from the source schema and from other functoids.</span></span>  
  
 <span data-ttu-id="afe46-124">调用模板是用于创建目标节点及其任何子结构。</span><span class="sxs-lookup"><span data-stu-id="afe46-124">The call template is responsible for creating the destination node and any of its substructures.</span></span>  
  
 <span data-ttu-id="afe46-125">串联两个元素的示例 XSLT 调用模板中显示**输入脚本**缓冲选择时**内联 XSLT 调用模板**中**选择脚本类型**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="afe46-125">A sample XSLT call template that concatenates two elements appears in the **Input script** buffer when you select **Inline XSLT Call Template** in the **Select script type** dropdown.</span></span>  
  
 <span data-ttu-id="afe46-126">有关内联 XSLT 调用模板的其他示例，请参阅[XML 工具 （BizTalk Server 示例文件夹）](../core/xml-tools-biztalk-server-samples-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="afe46-126">For another example of an inline XSLT call template, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afe46-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="afe46-127">See Also</span></span>  
 <span data-ttu-id="afe46-128">[脚本 Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="afe46-128">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="afe46-129">[使用外部程序集编写脚本](../core/scripting-using-external-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="afe46-129">[Scripting Using External Assemblies](../core/scripting-using-external-assemblies.md) </span></span>  
 <span data-ttu-id="afe46-130">[使用内联 C#、 JScript.NET 和 Visual Basic.NET 编写脚本](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span><span class="sxs-lookup"><span data-stu-id="afe46-130">[Scripting Using Inline C#, JScript .NET, and Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span></span>  
 <span data-ttu-id="afe46-131">[如何向映射添加脚本 Functoid](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="afe46-131">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="afe46-132">如何配置脚本 Functoid</span><span class="sxs-lookup"><span data-stu-id="afe46-132">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)