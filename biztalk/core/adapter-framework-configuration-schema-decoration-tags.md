---
title: "适配器 Framework 配置架构修饰标记 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d5d7f6b-2273-45a6-ba9d-43201760cf22
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b834482b70e75d12bb6786dac2a5d9eb6f9fef40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-framework-configuration-schema-decoration-tags"></a><span data-ttu-id="078f9-102">适配器 Framework 配置架构修饰标记</span><span class="sxs-lookup"><span data-stu-id="078f9-102">Adapter Framework Configuration Schema Decoration Tags</span></span>
<span data-ttu-id="078f9-103">您可以在配置架构文件中使用本主题所述的标记来显示和组织适配器属性页上的数据。</span><span class="sxs-lookup"><span data-stu-id="078f9-103">You can use the tags described in this topic within the configuration schema files to display and organize data on the adapter property pages.</span></span>  
  
 <span data-ttu-id="078f9-104">下图显示了 FTP 接收位置属性页如何实现其中的一些标记。</span><span class="sxs-lookup"><span data-stu-id="078f9-104">The following figure shows how the FTP receive location property page implements some of these tags.</span></span>  
  
 ![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")  
<span data-ttu-id="078f9-105">\<说明 >， \<displayname >，和\<类别 > FTP 适配器属性页中的标记</span><span class="sxs-lookup"><span data-stu-id="078f9-105">The \<description>, \<displayname>, and \<category> tags in the FTP adapter property page</span></span>  
  
## <a name="designer"></a><span data-ttu-id="078f9-106">\<设计器 ></span><span class="sxs-lookup"><span data-stu-id="078f9-106">\<designer></span></span>  
 <span data-ttu-id="078f9-107">BizTalk 适配器 Framework 修饰之间出现\<baf:designer > 标记和\</baf:designer > 结束标记。</span><span class="sxs-lookup"><span data-stu-id="078f9-107">The BizTalk Adapter Framework decorations appear between a \<baf:designer> tag and \</baf:designer> end tag.</span></span> <span data-ttu-id="078f9-108">\<Baf:designer > 标记可帮助区分适配器 Framework \<appinfo > 和其他适配器提供\<appinfo > 信息。</span><span class="sxs-lookup"><span data-stu-id="078f9-108">The \<baf:designer> tag helps distinguish between Adapter Framework \<appinfo> and other adapter-supplied \<appinfo> information.</span></span>  
  
## <a name="category"></a><span data-ttu-id="078f9-109">\<类别 ></span><span class="sxs-lookup"><span data-stu-id="078f9-109">\<category></span></span>  
 <span data-ttu-id="078f9-110">\<类别 > 修饰包含用来分隔为组在属性网格中的项的字符串。</span><span class="sxs-lookup"><span data-stu-id="078f9-110">The \<category> decoration contains the string used to separate entries in the property grid into groups.</span></span> <span data-ttu-id="078f9-111">该修饰将具有同一类别字符串的所有条目显示为该类别的从属条目。</span><span class="sxs-lookup"><span data-stu-id="078f9-111">The decoration displays all entries with the same category string as subordinate entries of the category.</span></span>  
  
 <span data-ttu-id="078f9-112">可以本地化\<类别 > 条目。</span><span class="sxs-lookup"><span data-stu-id="078f9-112">You can localize \<category> entries.</span></span>  
  
## <a name="description"></a><span data-ttu-id="078f9-113">\<说明 ></span><span class="sxs-lookup"><span data-stu-id="078f9-113">\<description></span></span>  
 <span data-ttu-id="078f9-114">\<说明 > 修饰包含用于为在属性网格底部的条目中提供说明性文本的字符串。</span><span class="sxs-lookup"><span data-stu-id="078f9-114">The \<description> decoration contains the string used to provide descriptive text for entries at the bottom of the property grid.</span></span>  
  
 <span data-ttu-id="078f9-115">可以本地化\<说明 > 条目。</span><span class="sxs-lookup"><span data-stu-id="078f9-115">You can localize \<description> entries.</span></span>  
  
## <a name="displayname"></a><span data-ttu-id="078f9-116">\<displayname ></span><span class="sxs-lookup"><span data-stu-id="078f9-116">\<displayname></span></span>  
 <span data-ttu-id="078f9-117">\<Displayname > 修饰包含用于显示条目的名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="078f9-117">The \<displayname> decoration contains the string used for displaying the name of an entry.</span></span> <span data-ttu-id="078f9-118">这使你可以使用空格、 短语和等等，当它们将不允许用于\<元素 > 或\<属性 > 名称。</span><span class="sxs-lookup"><span data-stu-id="078f9-118">This enables you to use spaces, phrases, and so on, when they would not be allowed for an \<element> or \<attribute> name.</span></span>  
  
 <span data-ttu-id="078f9-119">可以本地化\<displayname > 条目。</span><span class="sxs-lookup"><span data-stu-id="078f9-119">You can localize \<displayname> entries.</span></span>  
  
## <a name="readonly"></a><span data-ttu-id="078f9-120">\<readonly ></span><span class="sxs-lookup"><span data-stu-id="078f9-120">\<readonly></span></span>  
 <span data-ttu-id="078f9-121">\<Readonly 固定 =""> 修饰控制是否可编辑字段。</span><span class="sxs-lookup"><span data-stu-id="078f9-121">The \<readonly fixed=""> decoration controls whether a field may be edited.</span></span> <span data-ttu-id="078f9-122">如果“fixed”属性值为 `true`（默认值），则字段为只读。</span><span class="sxs-lookup"><span data-stu-id="078f9-122">A "fixed" attribute value of `true` (the default) makes a field read-only.</span></span>  
  
 <span data-ttu-id="078f9-123">当实现外部编辑器，实现外部**TypeConverter**类并重写**GetStandardValuesExclusive(ITypeDescriptorContext)**方法相反。</span><span class="sxs-lookup"><span data-stu-id="078f9-123">When implementing an external editor, implement an external **TypeConverter** class and override the **GetStandardValuesExclusive(ITypeDescriptorContext)** method instead.</span></span> <span data-ttu-id="078f9-124">返回`true`使字段成为只读的但会保留到自定义编辑器的访问。</span><span class="sxs-lookup"><span data-stu-id="078f9-124">Returning `true` makes a field read-only but preserves access to the custom editor.</span></span>  
  
## <a name="browsable"></a><span data-ttu-id="078f9-125">\<可浏览 ></span><span class="sxs-lookup"><span data-stu-id="078f9-125">\<browsable></span></span>  
 <span data-ttu-id="078f9-126">\<可浏览显示 =""> 修饰控制字段是否显示在属性网格。</span><span class="sxs-lookup"><span data-stu-id="078f9-126">The \<browsable show=""> decoration controls whether a field appears in the property grid.</span></span> <span data-ttu-id="078f9-127">如果“show”属性值为 `True`（默认值），则字段将出现在网格中。</span><span class="sxs-lookup"><span data-stu-id="078f9-127">A "show" attribute value of `True` (the default) makes a field appear in the grid.</span></span>  
  
## <a name="converter"></a><span data-ttu-id="078f9-128">\<转换器 ></span><span class="sxs-lookup"><span data-stu-id="078f9-128">\<converter></span></span>  
 <span data-ttu-id="078f9-129">\<转换器程序集 =""> 修饰指定所需**TypeConverter**类名称\<元素 > 或\<属性 >。</span><span class="sxs-lookup"><span data-stu-id="078f9-129">The \<converter assembly=""> decoration specifies the desired **TypeConverter** class name for the \<element> or \<attribute>.</span></span> <span data-ttu-id="078f9-130">可选的"程序集"属性值指定包含所需的程序集的路径**TypeConverter**。</span><span class="sxs-lookup"><span data-stu-id="078f9-130">The optional "assembly" attribute value specifies the path to the assembly containing the desired **TypeConverter**.</span></span> <span data-ttu-id="078f9-131">如果不指定“assembly”值，类名必须包括全局程序集缓存的程序集名称、密钥、区域性和版本值。</span><span class="sxs-lookup"><span data-stu-id="078f9-131">With no "assembly" value specified, the class name must include the global assembly cache's assembly name, key, culture, and version values.</span></span>  
  
## <a name="editor"></a><span data-ttu-id="078f9-132">\<编辑器 ></span><span class="sxs-lookup"><span data-stu-id="078f9-132">\<editor></span></span>  
 <span data-ttu-id="078f9-133">\<编辑器程序集 =""> 修饰指定所需**UITypeEditor**类名称\<元素 > 或\<属性 >。</span><span class="sxs-lookup"><span data-stu-id="078f9-133">The \<editor assembly=""> decoration specifies the desired **UITypeEditor** class name for the \<element> or \<attribute>.</span></span> <span data-ttu-id="078f9-134">可选的"程序集"属性值指定包含所需的程序集的路径**UITypeEditor**。</span><span class="sxs-lookup"><span data-stu-id="078f9-134">The optional "assembly" attribute value specifies the path to the assembly containing the desired **UITypeEditor**.</span></span> <span data-ttu-id="078f9-135">如果不指定“assembly”值，类名必须包括全局程序集缓存的程序集名称、密钥、区域性和版本值。</span><span class="sxs-lookup"><span data-stu-id="078f9-135">With no "assembly" value specified, the class name must include the global assembly cache's assembly name, key, culture, and version values.</span></span>  
  
## <a name="null-values-for-optional-enumerations"></a><span data-ttu-id="078f9-136">可选枚举的空值</span><span class="sxs-lookup"><span data-stu-id="078f9-136">Null Values for Optional Enumerations</span></span>  
 <span data-ttu-id="078f9-137">在使用可选的枚举，其中一个值应为\<无 > 来表示 null 值。</span><span class="sxs-lookup"><span data-stu-id="078f9-137">When using an optional enumeration, one of the values should be \<none> to denote a null value.</span></span> <span data-ttu-id="078f9-138">这不是内置标记，但如果枚举是从 xsd:string 派生的，则可以通过提供视为空值的枚举值来生成此标记。</span><span class="sxs-lookup"><span data-stu-id="078f9-138">This is not a built-in tag, but may be achieved by providing an enumeration value that is treated as none if the enumeration is derived from xsd:string.</span></span> <span data-ttu-id="078f9-139">从 xsd:int 派生的枚举无法生成此标记，因为整数必须包含值。</span><span class="sxs-lookup"><span data-stu-id="078f9-139">This is not possible for enumerations derived from xsd:int, because the integer must hold a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="078f9-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="078f9-140">See Also</span></span>  
 [<span data-ttu-id="078f9-141">适配器 Framework 配置架构扩展</span><span class="sxs-lookup"><span data-stu-id="078f9-141">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)