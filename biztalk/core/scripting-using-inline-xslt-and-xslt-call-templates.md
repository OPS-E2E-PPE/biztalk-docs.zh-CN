---
title: "脚本使用内联 XSLT 和 XSLT 调用模板 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3168417-3653-4c9e-a09c-184ffdc0ccb2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7c4c1d8eff582d15f9ce022053b80f2dea2f856
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scripting-using-inline-xslt-and-xslt-call-templates"></a><span data-ttu-id="39578-102">脚本使用内联 XSLT 和 XSLT 调用模板</span><span class="sxs-lookup"><span data-stu-id="39578-102">Scripting Using Inline XSLT and XSLT Call Templates</span></span>
<span data-ttu-id="39578-103">你可以直接编写用于可扩展样式表语言转换 (XSLT) 样式表**脚本**functoid。</span><span class="sxs-lookup"><span data-stu-id="39578-103">You can directly write Extensible Stylesheet Language Transformations (XSLT) stylesheets for use in the **Scripting** functoid.</span></span> <span data-ttu-id="39578-104">这样，您就可以执行链接和内置 functoid 可能无法表示的转换。</span><span class="sxs-lookup"><span data-stu-id="39578-104">This enables you to perform transformations, that links and built-in functoids may not be able to represent.</span></span> <span data-ttu-id="39578-105">XSLT 脚本有两种类型：内联 XSLT 和 XSLT 调用模板。</span><span class="sxs-lookup"><span data-stu-id="39578-105">There are two kinds of XSLT scripts: inline XSLT and XSLT call templates.</span></span> <span data-ttu-id="39578-106">当你选择在**选择脚本类型**中的下拉列表**配置脚本 Functoid**对话框中，示例代码将显示您可以使用。</span><span class="sxs-lookup"><span data-stu-id="39578-106">When you select either in the **Select script type** dropdown in the **Configure Scripting Functoid** dialog box, sample code appears that you may use.</span></span>  
  
 <span data-ttu-id="39578-107">内联 XSLT 脚本和内联 XSLT 调用模板可以调用外部程序集中的函数。</span><span class="sxs-lookup"><span data-stu-id="39578-107">Inline XSLT scripts and inline XSLT call templates may call functions in external assemblies.</span></span> <span data-ttu-id="39578-108">进行此类调用需要设置**自定义扩展 XML**网格的属性。</span><span class="sxs-lookup"><span data-stu-id="39578-108">Making such calls requires setting the **Custom Extension XML** property of the grid.</span></span> <span data-ttu-id="39578-109">有关详细信息，请参阅**自定义扩展 XML （网格属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="39578-109">For more information, see **Custom Extension XML (Grid Property)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="inline-xslt"></a><span data-ttu-id="39578-110">内联 XSLT</span><span class="sxs-lookup"><span data-stu-id="39578-110">Inline XSLT</span></span>  
 <span data-ttu-id="39578-111">内联 XSLT 脚本只能生成输出。</span><span class="sxs-lookup"><span data-stu-id="39578-111">An inline XSLT script may only produce output.</span></span> <span data-ttu-id="39578-112">**脚本**functoid 可能没有任何输入的链接。</span><span class="sxs-lookup"><span data-stu-id="39578-112">The **Scripting** functoid may not have any input links.</span></span> <span data-ttu-id="39578-113">该 functoid 还必须直接链接到目标架构中的记录或字段。</span><span class="sxs-lookup"><span data-stu-id="39578-113">The functoid must also directly link to a record or field in the destination schema.</span></span>  
  
 <span data-ttu-id="39578-114">此外，该脚本还用于创建目标节点及其任何下级结构。</span><span class="sxs-lookup"><span data-stu-id="39578-114">In addition, the script is responsible for creating the target node and any structures underneath it.</span></span>  
  
 <span data-ttu-id="39578-115">以下输入实例消息包含表示联系人信息的两个元素：</span><span class="sxs-lookup"><span data-stu-id="39578-115">The following input instance message contains two elements representing contact information.</span></span>  
  
```  
<ns0:SourceInstance xmlns:ns0="http://SourceInstanceNamespace">  
    <Address>  
        <Contact>Karin Zimprich</Contact>  
        <ContactType>Referral</ContactType>  
    </Address>  
</ns0:SourceInstance>  
```  
  
 <span data-ttu-id="39578-116">以下的内联 XSLT 脚本，在脚本缓冲区中，输入将转换**联系人**和**ContactType**字段添加到属性。</span><span class="sxs-lookup"><span data-stu-id="39578-116">The following inline XSLT script, entered in the script buffer, converts the **Contact** and **ContactType** fields to attributes.</span></span>  
  
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
  
 <span data-ttu-id="39578-117">如果具有适当的输出架构，那么，在针对前面的输入实例消息运行时，该脚本将生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="39578-117">The script produces the following output, assuming an appropriate output schema, when run against the preceding input instance message.</span></span>  
  
```  
<ns0:OutInstance xmlns:ns0="http://More_XSLT.Out">  
    <ContactInfo ContactType="Referral" Contact="Karin Zimprich" xmlns:p="http://SourceInstanceNamespace">  
    </ContactInfo>  
</ns0:OutInstance>  
```  
  
 <span data-ttu-id="39578-118">请注意，指向没有**脚本**functoid 不会阻止 XSLT 脚本从输入的实例消息中获取数据。</span><span class="sxs-lookup"><span data-stu-id="39578-118">Notice that the absence of links to the **Scripting** functoid does not prevent the XSLT script from getting data from the input instance message.</span></span> <span data-ttu-id="39578-119">该脚本指定了输入实例值的路径。</span><span class="sxs-lookup"><span data-stu-id="39578-119">The script specifies paths to the input instance values.</span></span>  
  
 <span data-ttu-id="39578-120">有关内联 XSLT 脚本的另一个示例，请参阅[（BizTalk Server 示例文件夹中） 的 XML 工具](../core/xml-tools-biztalk-server-samples-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="39578-120">For another example of an inline XSLT script, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="inline-xslt-call-templates"></a><span data-ttu-id="39578-121">内联 XSLT 调用模板</span><span class="sxs-lookup"><span data-stu-id="39578-121">Inline XSLT Call Templates</span></span>  
 <span data-ttu-id="39578-122">与内联 XSLT 脚本类似，内联 XSLT 调用模板必须直接连接到目标节点。</span><span class="sxs-lookup"><span data-stu-id="39578-122">Like an inline XSLT script, an inline XSLT call template must connect directly to a destination node.</span></span> <span data-ttu-id="39578-123">不过，内联 XSLT 调用模板可以使用源自源架构和其他 functoid 的链接。</span><span class="sxs-lookup"><span data-stu-id="39578-123">However, an inline XSLT call template may use links from the source schema and from other functoids.</span></span>  
  
 <span data-ttu-id="39578-124">调用模板用于创建目标节点及其任何子结构。</span><span class="sxs-lookup"><span data-stu-id="39578-124">The call template is responsible for creating the destination node and any of its substructures.</span></span>  
  
 <span data-ttu-id="39578-125">连接两个元素的示例 XSLT 调用模板出现在**输入脚本**时你选择缓冲**内联 XSLT 调用模板**中**选择脚本类型**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="39578-125">A sample XSLT call template that concatenates two elements appears in the **Input script** buffer when you select **Inline XSLT Call Template** in the **Select script type** dropdown.</span></span>  
  
 <span data-ttu-id="39578-126">有关内联 XSLT 调用模板的另一个示例，请参阅[（BizTalk Server 示例文件夹中） 的 XML 工具](../core/xml-tools-biztalk-server-samples-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="39578-126">For another example of an inline XSLT call template, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39578-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39578-127">See Also</span></span>  
 <span data-ttu-id="39578-128">[脚本 Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="39578-128">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="39578-129">[脚本使用外部程序集](../core/scripting-using-external-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="39578-129">[Scripting Using External Assemblies](../core/scripting-using-external-assemblies.md) </span></span>  
 <span data-ttu-id="39578-130">[脚本使用内联 C#、 JScript.NET 和 Visual Basic.NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span><span class="sxs-lookup"><span data-stu-id="39578-130">[Scripting Using Inline C#, JScript .NET, and Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span></span>  
 <span data-ttu-id="39578-131">[如何在向地图添加脚本 Functoid](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="39578-131">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="39578-132">如何配置脚本 Functoid</span><span class="sxs-lookup"><span data-stu-id="39578-132">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)