---
title: 适配器框架配置架构修饰标记 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d5d7f6b-2273-45a6-ba9d-43201760cf22
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdce504133ecb1de4763ce72b314fe39cea8fef3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361483"
---
# <a name="adapter-framework-configuration-schema-decoration-tags"></a><span data-ttu-id="d4f11-102">适配器框架配置架构修饰标记</span><span class="sxs-lookup"><span data-stu-id="d4f11-102">Adapter Framework Configuration Schema Decoration Tags</span></span>
<span data-ttu-id="d4f11-103">可以使用本主题中的配置架构文件中所述的标记来显示和组织适配器属性页上的数据。</span><span class="sxs-lookup"><span data-stu-id="d4f11-103">You can use the tags described in this topic within the configuration schema files to display and organize data on the adapter property pages.</span></span>  
  
 <span data-ttu-id="d4f11-104">下图显示了如何 FTP 接收位置属性页将实施某些这些标记。</span><span class="sxs-lookup"><span data-stu-id="d4f11-104">The following figure shows how the FTP receive location property page implements some of these tags.</span></span>  
  
 <span data-ttu-id="d4f11-105">![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")</span><span class="sxs-lookup"><span data-stu-id="d4f11-105">![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")</span></span>  
<span data-ttu-id="d4f11-106">\<描述\>， \<displayname\>，并\<类别\>FTP 适配器属性页中的标记</span><span class="sxs-lookup"><span data-stu-id="d4f11-106">The \<description\>, \<displayname\>, and \<category\> tags in the FTP adapter property page</span></span>  
  
## <a name="designer"></a><span data-ttu-id="d4f11-107">\<designer\></span><span class="sxs-lookup"><span data-stu-id="d4f11-107">\<designer\></span></span>  
 <span data-ttu-id="d4f11-108">BizTalk 适配器框架修饰出现之间\<baf: designer\>标记和\</baf:designer\>结束标记。</span><span class="sxs-lookup"><span data-stu-id="d4f11-108">The BizTalk Adapter Framework decorations appear between a \<baf:designer\> tag and \</baf:designer\> end tag.</span></span> <span data-ttu-id="d4f11-109">\<Baf: designer\>标记有助于区分适配器框架\<appinfo\>和其他适配器提供\<appinfo\>信息。</span><span class="sxs-lookup"><span data-stu-id="d4f11-109">The \<baf:designer\> tag helps distinguish between Adapter Framework \<appinfo\> and other adapter-supplied \<appinfo\> information.</span></span>  
  
## <a name="category"></a><span data-ttu-id="d4f11-110">\<category\></span><span class="sxs-lookup"><span data-stu-id="d4f11-110">\<category\></span></span>  
 <span data-ttu-id="d4f11-111">\<类别\>修饰包含用于将分组在属性网格中的项的字符串。</span><span class="sxs-lookup"><span data-stu-id="d4f11-111">The \<category\> decoration contains the string used to separate entries in the property grid into groups.</span></span> <span data-ttu-id="d4f11-112">修饰将具有同一类别字符串的所有条目都显示为类别的从属条目。</span><span class="sxs-lookup"><span data-stu-id="d4f11-112">The decoration displays all entries with the same category string as subordinate entries of the category.</span></span>  
  
 <span data-ttu-id="d4f11-113">可以进行本地化\<类别\>条目。</span><span class="sxs-lookup"><span data-stu-id="d4f11-113">You can localize \<category\> entries.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d4f11-114">\<description\></span><span class="sxs-lookup"><span data-stu-id="d4f11-114">\<description\></span></span>  
 <span data-ttu-id="d4f11-115">\<说明\>修饰包含用于为属性网格底部的条目提供说明性文本的字符串。</span><span class="sxs-lookup"><span data-stu-id="d4f11-115">The \<description\> decoration contains the string used to provide descriptive text for entries at the bottom of the property grid.</span></span>  
  
 <span data-ttu-id="d4f11-116">可以进行本地化\<说明\>条目。</span><span class="sxs-lookup"><span data-stu-id="d4f11-116">You can localize \<description\> entries.</span></span>  
  
## <a name="displayname"></a><span data-ttu-id="d4f11-117">\<displayname\></span><span class="sxs-lookup"><span data-stu-id="d4f11-117">\<displayname\></span></span>  
 <span data-ttu-id="d4f11-118">\<Displayname\>修饰包含用于显示项的名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="d4f11-118">The \<displayname\> decoration contains the string used for displaying the name of an entry.</span></span> <span data-ttu-id="d4f11-119">这使您可以使用空格、 短语等，它们将不允许为时\<元素\>或\<属性\>名称。</span><span class="sxs-lookup"><span data-stu-id="d4f11-119">This enables you to use spaces, phrases, and so on, when they would not be allowed for an \<element\> or \<attribute\> name.</span></span>  
  
 <span data-ttu-id="d4f11-120">可以进行本地化\<displayname\>条目。</span><span class="sxs-lookup"><span data-stu-id="d4f11-120">You can localize \<displayname\> entries.</span></span>  
  
## <a name="readonly"></a><span data-ttu-id="d4f11-121">\<readonly\></span><span class="sxs-lookup"><span data-stu-id="d4f11-121">\<readonly\></span></span>  
 <span data-ttu-id="d4f11-122">\<Fixed =""\>修饰控制是否可以编辑字段。</span><span class="sxs-lookup"><span data-stu-id="d4f11-122">The \<readonly fixed=""\> decoration controls whether a field may be edited.</span></span> <span data-ttu-id="d4f11-123">"固定"的属性值`true`（默认值） 会使字段变为只读的。</span><span class="sxs-lookup"><span data-stu-id="d4f11-123">A "fixed" attribute value of `true` (the default) makes a field read-only.</span></span>  
  
 <span data-ttu-id="d4f11-124">在实现外部编辑器时，实现外部**TypeConverter**类并重写**getstandardvaluesexclusive （itypedescriptorcontext)** 方法相反。</span><span class="sxs-lookup"><span data-stu-id="d4f11-124">When implementing an external editor, implement an external **TypeConverter** class and override the **GetStandardValuesExclusive(ITypeDescriptorContext)** method instead.</span></span> <span data-ttu-id="d4f11-125">返回`true`使字段成为只读的但保留权访问自定义编辑器。</span><span class="sxs-lookup"><span data-stu-id="d4f11-125">Returning `true` makes a field read-only but preserves access to the custom editor.</span></span>  
  
## <a name="browsable"></a><span data-ttu-id="d4f11-126">\<browsable\></span><span class="sxs-lookup"><span data-stu-id="d4f11-126">\<browsable\></span></span>  
 <span data-ttu-id="d4f11-127">\<可浏览 show =""\>修饰控制字段是否出现在属性网格中。</span><span class="sxs-lookup"><span data-stu-id="d4f11-127">The \<browsable show=""\> decoration controls whether a field appears in the property grid.</span></span> <span data-ttu-id="d4f11-128">一个"显示"属性值为`True`（默认值），网格中显示的字段。</span><span class="sxs-lookup"><span data-stu-id="d4f11-128">A "show" attribute value of `True` (the default) makes a field appear in the grid.</span></span>  
  
## <a name="converter"></a><span data-ttu-id="d4f11-129">\<converter\></span><span class="sxs-lookup"><span data-stu-id="d4f11-129">\<converter\></span></span>  
 <span data-ttu-id="d4f11-130">\<转换器程序集 =""\>修饰指定所需**TypeConverter**类名\<元素\>或者\<特性\>。</span><span class="sxs-lookup"><span data-stu-id="d4f11-130">The \<converter assembly=""\> decoration specifies the desired **TypeConverter** class name for the \<element\> or \<attribute\>.</span></span> <span data-ttu-id="d4f11-131">可选的"assembly"属性值指定包含所需的程序集的路径**TypeConverter**。</span><span class="sxs-lookup"><span data-stu-id="d4f11-131">The optional "assembly" attribute value specifies the path to the assembly containing the desired **TypeConverter**.</span></span> <span data-ttu-id="d4f11-132">没有指定"assembly"值，类名必须包括全局程序集缓存的程序集名称、 密钥、 区域性和版本值。</span><span class="sxs-lookup"><span data-stu-id="d4f11-132">With no "assembly" value specified, the class name must include the global assembly cache's assembly name, key, culture, and version values.</span></span>  
  
## <a name="editor"></a><span data-ttu-id="d4f11-133">\<editor\></span><span class="sxs-lookup"><span data-stu-id="d4f11-133">\<editor\></span></span>  
 <span data-ttu-id="d4f11-134">\<编辑器程序集 =""\>修饰指定所需**UITypeEditor**类名\<元素\>或者\<特性\>。</span><span class="sxs-lookup"><span data-stu-id="d4f11-134">The \<editor assembly=""\> decoration specifies the desired **UITypeEditor** class name for the \<element\> or \<attribute\>.</span></span> <span data-ttu-id="d4f11-135">可选的"assembly"属性值指定包含所需的程序集的路径**UITypeEditor**。</span><span class="sxs-lookup"><span data-stu-id="d4f11-135">The optional "assembly" attribute value specifies the path to the assembly containing the desired **UITypeEditor**.</span></span> <span data-ttu-id="d4f11-136">没有指定"assembly"值，类名必须包括全局程序集缓存的程序集名称、 密钥、 区域性和版本值。</span><span class="sxs-lookup"><span data-stu-id="d4f11-136">With no "assembly" value specified, the class name must include the global assembly cache's assembly name, key, culture, and version values.</span></span>  
  
## <a name="null-values-for-optional-enumerations"></a><span data-ttu-id="d4f11-137">可选枚举的 null 值</span><span class="sxs-lookup"><span data-stu-id="d4f11-137">Null Values for Optional Enumerations</span></span>  
 <span data-ttu-id="d4f11-138">在使用可选的枚举，其中一个值应为\<none\>来表示 null 值。</span><span class="sxs-lookup"><span data-stu-id="d4f11-138">When using an optional enumeration, one of the values should be \<none\> to denote a null value.</span></span> <span data-ttu-id="d4f11-139">这不是内置标记，但可能会通过提供一个枚举值，如果从 xsd: string 派生枚举作为无处理。</span><span class="sxs-lookup"><span data-stu-id="d4f11-139">This is not a built-in tag, but may be achieved by providing an enumeration value that is treated as none if the enumeration is derived from xsd:string.</span></span> <span data-ttu-id="d4f11-140">这是不可能从 xsd: int，派生的枚举，因为整数必须包含一个值。</span><span class="sxs-lookup"><span data-stu-id="d4f11-140">This is not possible for enumerations derived from xsd:int, because the integer must hold a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f11-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4f11-141">See Also</span></span>  
 [<span data-ttu-id="d4f11-142">适配器框架配置架构扩展</span><span class="sxs-lookup"><span data-stu-id="d4f11-142">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)