---
title: 开发自定义引用 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e26d726-240c-4dfc-baa2-77451b8dc6c5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70f9cfcfaf50d92758f808346380b0a351a2f45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239221"
---
# <a name="developing-a-custom-referenced-functoid"></a><span data-ttu-id="d1629-102">开发自定义引用的 Functoid</span><span class="sxs-lookup"><span data-stu-id="d1629-102">Developing a Custom Referenced Functoid</span></span>
<span data-ttu-id="d1629-103">自定义引用的 Functoid 不会将内联的实现代码复制到映射中。</span><span class="sxs-lookup"><span data-stu-id="d1629-103">Custom referenced functoids do not copy implementation code inline into the map.</span></span> <span data-ttu-id="d1629-104">实际上，它将对程序集、类和方法的引用放置在与生成的样式表相关联的扩展对象文件中，并在运行时对其进行调用。</span><span class="sxs-lookup"><span data-stu-id="d1629-104">Instead, a reference to the assembly, class, and method is placed in the extension object file associated with the generated style sheet and called at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1629-105">示例</span><span class="sxs-lookup"><span data-stu-id="d1629-105">Example</span></span>  
 <span data-ttu-id="d1629-106">以下示例说明了如何创建用于连接两个字符串的自定义引用的 functoid。</span><span class="sxs-lookup"><span data-stu-id="d1629-106">The following example illustrates how to create a custom referenced functoid for concatenating two strings.</span></span> <span data-ttu-id="d1629-107">该 functoid 依赖于一个包含三个字符串资源和一个 16x16 像素位图资源的资源文件。</span><span class="sxs-lookup"><span data-stu-id="d1629-107">It relies on a resource file containing three string resources and a 16x16-pixel bitmap resource.</span></span>  
  
```  
using System;  
using Microsoft.BizTalk.BaseFunctoids;  
using System.Reflection;  
  
namespace Microsoft.Samples.BizTalk.CustomFunctoid  
{  
    /// <summary>  
    /// Performs a string concatenation through assembly referenced function. Assembly must be deployed with the BizTalk solution.  
    /// </summary>  
    public class CustomStringConcatFunctoid : BaseFunctoid  
    {  
        public CustomStringConcatFunctoid()  
            : base()  
        {  
            //ID for this functoid  
            this.ID = 6001;  
  
            // Resource assembly must be ProjectName.ResourceName if building with VS.Net  
            SetupResourceAssembly("Microsoft.Samples.BizTalk.CustomFunctoid.CustomFunctoidResources", Assembly.GetExecutingAssembly());  
  
            // Pass the resource ID names for functoid name, tooltip  
            // description and the 16x16 bitmap for the Map palette  
            SetName("IDS_CUSTOMSTRINGCONCATFUNCTOID_NAME");  
            SetTooltip("IDS_CUSTOMSTRINGCONCATFUNCTOID_TOOLTIP");  
            SetDescription("IDS_CUSTOMSTRINGCONCATFUNCTOID_DESCRIPTION");  
            SetBitmap("IDB_CUSTOMSTRINGCONCATFUNCTOID_BITMAP");  
  
            // Put this string handling function under the String   
            // Functoid tab in the Visual Studio toolbox for functoids  
            this.Category = FunctoidCategory.String;  
  
            // 2 required parameters, no optional parameters  
            this.SetMinParams(2);  
            this.SetMaxParams(2);  
  
            // Functoid accepts two inputs  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
  
            // Set the output connection type  
            this.OutputConnectionType = ConnectionType.AllExceptRecord;  
  
            // Set the function name that needs to be called  
            // when this functoid is invoked.  The resulting assembly  
            // must be present in the Global Assembly Cache  
            // to ensure its availability.  
            SetExternalFunctionName(GetType().Assembly.FullName, "Microsoft.Samples.BizTalk.CustomFunctoid.CustomStringConcatFunctoid", "ConCatStrings");  
        }  
  
        // This function is executed by BizTalk to do the concatenation  
        public string ConCatStrings(string val1, string val2)  
        {  
            return val2 + val1;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1629-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1629-108">See Also</span></span>  
 <span data-ttu-id="d1629-109">[使用 BaseFunctoid](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="d1629-109">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 <span data-ttu-id="d1629-110">[开发自定义的内联 Functoid](../core/developing-a-custom-inline-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="d1629-110">[Developing a Custom Inline Functoid](../core/developing-a-custom-inline-functoid.md) </span></span>  
 <span data-ttu-id="d1629-111">[开发自定义的累积 Functoid](../core/developing-a-custom-cumulative-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="d1629-111">[Developing a Custom Cumulative Functoid](../core/developing-a-custom-cumulative-functoid.md) </span></span>  
 [<span data-ttu-id="d1629-112">自定义 Functoid （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="d1629-112">Custom Functoid (BizTalk Server Sample)</span></span>](../core/custom-functoid-biztalk-server-sample.md)