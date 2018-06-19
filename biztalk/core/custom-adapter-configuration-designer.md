---
title: 自定义适配器配置设计器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9b231c3-3948-4db8-b4f0-d9c21c31b168
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cff46f95062eff856653b6114f76f89ac17efd1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970371"
---
# <a name="custom-adapter-configuration-designer"></a><span data-ttu-id="7530e-102">自定义适配器配置设计器</span><span class="sxs-lookup"><span data-stu-id="7530e-102">Custom Adapter Configuration Designer</span></span>
<span data-ttu-id="7530e-103">您需要在 .NET 类库中生成自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="7530e-103">You need to build the custom designers into a .NET class library.</span></span> <span data-ttu-id="7530e-104">您既可将它们合并到适配器的 DLL，也可生成单独的 DLL。</span><span class="sxs-lookup"><span data-stu-id="7530e-104">You may incorporate them into the DLL for the adapter or build a separate DLL.</span></span> <span data-ttu-id="7530e-105">生成设计器程序集后，您必须通过修饰来引用该程序集，如同引用说明或类别一样。</span><span class="sxs-lookup"><span data-stu-id="7530e-105">After you build a designer assembly, you must reference it through decorations, just like a description or a category.</span></span> <span data-ttu-id="7530e-106">该引用包括一个程序集规范和一个要使用的完全限定类名。</span><span class="sxs-lookup"><span data-stu-id="7530e-106">The reference includes a specification of the assembly and a fully qualified class name to use.</span></span>  
  
 <span data-ttu-id="7530e-107">这些修饰支持引用特定的自定义设计器的两种方式： 作为全局程序集缓存中的全局程序集或位于磁盘上的外部程序集。</span><span class="sxs-lookup"><span data-stu-id="7530e-107">These decorations support two ways of referencing the specific custom designer: as a global assembly in the global assembly cache or as an external assembly located on the disk.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7530e-108">有两个可能的设计时程序集路径： 你可以指定类型编辑器和 XSD XSD 本身 （不支持相对路径） 中的配置中使用的转换器的绝对路径，也可以在全局存储类型编辑器和转换器程序集缓存，并且不需要绝对路径。</span><span class="sxs-lookup"><span data-stu-id="7530e-108">There are two possible design-time assembly paths: You can specify the absolute path to the type editors and converters used in the configuration XSD in the XSD itself (relative path is not supported), or you can store the type editors and converters in the global assembly cache and not need an absolute path.</span></span>  
  
## <a name="global-assembly-cache-designer-use"></a><span data-ttu-id="7530e-109">全局程序集缓存设计器的使用</span><span class="sxs-lookup"><span data-stu-id="7530e-109">Global Assembly Cache Designer Use</span></span>  
 <span data-ttu-id="7530e-110">全局程序集缓存按照程序集名称、公钥、版本和区域性来存储程序集。</span><span class="sxs-lookup"><span data-stu-id="7530e-110">The global assembly cache stores assemblies by assembly name, public key, version, and culture.</span></span> <span data-ttu-id="7530e-111">因此，建议您：</span><span class="sxs-lookup"><span data-stu-id="7530e-111">Because of this, it is recommended that you:</span></span>  
  
1.  <span data-ttu-id="7530e-112">生成公钥文件，并将其添加到 AssemblyInfo.cs 文件中。</span><span class="sxs-lookup"><span data-stu-id="7530e-112">Generate a public key file and add this file to the AssemblyInfo.cs file.</span></span>  
  
2.  <span data-ttu-id="7530e-113">在 AssemblyInfo.cs 文件中指定特定版本。</span><span class="sxs-lookup"><span data-stu-id="7530e-113">Specify a specific version in the AssemblyInfo.cs file.</span></span>  
  
 <span data-ttu-id="7530e-114">您既可将该程序集拖入全局程序集缓存，也可使用 GACUTIL 将其添加到全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="7530e-114">You can either drag the assembly into the global assembly cache or use GACUTIL to add it to the global assembly cache.</span></span>  
  
 <span data-ttu-id="7530e-115">若要使用此设计器，请指定完全限定类名、逗号和全局程序集缓存程序集项（程序集名称、版本、区域性和公钥标记）作为修饰的值。</span><span class="sxs-lookup"><span data-stu-id="7530e-115">To use this designer, specify the fully qualified class name, a comma, and the global assembly cache assembly entry (assembly name, version, culture, and public key token) as the value of the decoration.</span></span> <span data-ttu-id="7530e-116">使用\<编辑器\>修饰**UITypeEditor**实现和\<转换器\>修饰**TypeConverter**实现.</span><span class="sxs-lookup"><span data-stu-id="7530e-116">Use \<editor\> decorations for **UITypeEditor** implementations and \<converter\> decorations for **TypeConverter** implementations.</span></span>  
  
 <span data-ttu-id="7530e-117">下面的代码演示如何在 XSD 文件中初始化自定义设计器：</span><span class="sxs-lookup"><span data-stu-id="7530e-117">The following code shows how to initialize the custom designers in an XSD file:</span></span>  
  
```  
<xs:element name="Global" type="xs:string">  
   <xs:annotation>  
      <xs:appinfo>  
         <baf:designer>  
            <baf:category>GAC Designer Component</baf:category>  
            <baf:editor>AdapterManagement.ComponentModel. PasswordUITypeEditor, AdapterManagement, Version=1.0.1.0, Culture=neutral, PublicKeyToken=f0db50abb0615c18</baf:editor>  
         </baf:designer>  
      </xs:appinfo>  
   </xs:annotation>  
</xs:element>  
      </xs:sequence>  
```  
  
## <a name="external-assembly-installation-and-use"></a><span data-ttu-id="7530e-118">外部程序集的安装和使用</span><span class="sxs-lookup"><span data-stu-id="7530e-118">External Assembly Installation and Use</span></span>  
 <span data-ttu-id="7530e-119">对于外部程序集，其修饰包含一个可选的属性程序集，该程序集指定包含目标设计器的程序集的完整路径和名称。</span><span class="sxs-lookup"><span data-stu-id="7530e-119">For external assemblies, the decoration contains an optional attribute assembly that specifies the full path and name of the assembly containing the desired designer.</span></span>  
  
 <span data-ttu-id="7530e-120">下面的代码演示如何初始化包含在外部程序集中的自定义设计器：</span><span class="sxs-lookup"><span data-stu-id="7530e-120">The following code shows how to initialize the custom designers contained in external assemblies:</span></span>  
  
```  
<xs:element name="External" type="xs:string">  
   <xs:annotation>  
      <xs:appinfo>  
         <baf:designer>  
            <baf:category>External Designer Component</baf:category>  
            <baf:converter assembly="C:\source\private\Adapter\Framework\Designer\bin\Debug\Designer.External.dll">Designer.External.DesignerTypeConverter</baf:converter>  
         </baf:designer>  
      </xs:appinfo>  
   </xs:annotation>  
</xs:element>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7530e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7530e-121">See Also</span></span>  
 <span data-ttu-id="7530e-122">[适配器配置的的自定义下拉列表编辑器](../core/custom-drop-down-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="7530e-122">[Custom Drop-Down Editor for Adapter Configuration](../core/custom-drop-down-editor-for-adapter-configuration.md) </span></span>  
 <span data-ttu-id="7530e-123">[适配器配置的的自定义模式对话框编辑器](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="7530e-123">[Custom Modal Dialog Editor for Adapter Configuration](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span></span>  
 <span data-ttu-id="7530e-124">[适配器配置的的自定义类型转换器](../core/custom-type-converter-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="7530e-124">[Custom Type Converter for Adapter Configuration](../core/custom-type-converter-for-adapter-configuration.md) </span></span>  
 [<span data-ttu-id="7530e-125">适配器的高级配置组件</span><span class="sxs-lookup"><span data-stu-id="7530e-125">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)