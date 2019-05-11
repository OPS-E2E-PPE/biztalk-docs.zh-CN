---
title: 适配器 GetSchema 方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c83340c-a775-435c-9633-3a692611e99e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7a06e6eedb57ea0cbca1c4572ddf755b9915ca7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361472"
---
# <a name="adapter-getschema-method"></a><span data-ttu-id="c91cf-102">适配器 GetSchema 方法</span><span class="sxs-lookup"><span data-stu-id="c91cf-102">Adapter GetSchema Method</span></span>
<span data-ttu-id="c91cf-103">假设引用的 WSDL 文件只包含架构引用并且不包含嵌入的架构。</span><span class="sxs-lookup"><span data-stu-id="c91cf-103">Suppose the referenced WSDL file contains only schema references and does not contain embedded schemas.</span></span> <span data-ttu-id="c91cf-104">在这种情况下，使用**GetSchema**方法**IAdapterConfig**接口加载从 WSDL 文件中引用的架构。</span><span class="sxs-lookup"><span data-stu-id="c91cf-104">In this case, you use the **GetSchema** method of the **IAdapterConfig** interface to load a schema referenced from within a WSDL file.</span></span>  
  
 <span data-ttu-id="c91cf-105">在文件适配器示例中，修改中的代码**GetSchema** AdapterManagement.cs 返回不包含在 WSDL 文件的任何外部 XSD 文件的方法。</span><span class="sxs-lookup"><span data-stu-id="c91cf-105">In the file adapter sample, modify the code in the **GetSchema** method of AdapterManagement.cs to return any external XSD files that are not included with the WSDL files.</span></span>  
  
 <span data-ttu-id="c91cf-106">以下代码摘自**GetSchema** AdapterManagement.cs 文件的方法。</span><span class="sxs-lookup"><span data-stu-id="c91cf-106">The following code is from the **GetSchema** method of the AdapterManagement.cs file.</span></span> <span data-ttu-id="c91cf-107">它返回 null 此处因为 Service1.wsdl 文件包含嵌入的架构。</span><span class="sxs-lookup"><span data-stu-id="c91cf-107">It returns null here because the Service1.wsdl file contains embedded schemas.</span></span> <span data-ttu-id="c91cf-108">如果不这样，需要返回到 XSD 架构文件相对应的字符串。</span><span class="sxs-lookup"><span data-stu-id="c91cf-108">If that were not the case, a string corresponding to an XSD schema file would need to be returned.</span></span>  
  
```  
/// <summary>  
        /// Acquire externally referenced xsd's  
        /// </summary>  
        /// <param name="xsdLocation">Location of schema</param>  
        /// <param name="xsdNamespace">Namespace</param>  
        /// <param name="XSDFileName">Schmea file name (return)</param>  
        /// <returns>Outcome of acquisition</returns>  
        public Result GetSchema(string xsdLocation,  
                                string xsdNamespace,  
                        out string xsdSchema)   
      {  
            xsdSchema = null;  
            return Result.Continue;  
        }  
```