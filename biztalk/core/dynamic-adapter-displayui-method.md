---
title: 动态适配器 DisplayUI 方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9183d2ee-4265-4fee-9d1d-7e2462d8ff37
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f64b6ca1a4f14f050a0d59344fe3233b55e88d74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389282"
---
# <a name="dynamic-adapter-displayui-method"></a><span data-ttu-id="25daa-102">动态适配器 DisplayUI 方法</span><span class="sxs-lookup"><span data-stu-id="25daa-102">Dynamic Adapter DisplayUI Method</span></span>
<span data-ttu-id="25daa-103">在此方法**IDynamicAdapterConfig**界面中显示自定义适配器的自定义用户界面。</span><span class="sxs-lookup"><span data-stu-id="25daa-103">This method on the **IDynamicAdapterConfig** interface displays the custom user interface for the custom adapter.</span></span> <span data-ttu-id="25daa-104">这使用户能够查看、 选择和导入其 BizTalk 项目基于所选的服务的相关支持文件。</span><span class="sxs-lookup"><span data-stu-id="25daa-104">This enables the user to view, select, and import the related supporting files based upon the selected services into their BizTalk project.</span></span>  
  
 <span data-ttu-id="25daa-105">在文件适配器中，修改中的代码**displayUI** AdapterManagement.cs 文件以便选择要接受的架构类型创建自定义用户界面 (UI) 的方法。</span><span class="sxs-lookup"><span data-stu-id="25daa-105">In the file adapter, modify the code within the **displayUI** method of the AdapterManagement.cs file to create a custom user interface (UI) for selecting the type of schema to accept.</span></span> <span data-ttu-id="25daa-106">选择架构后，选择适当的 WSDL 文件。</span><span class="sxs-lookup"><span data-stu-id="25daa-106">After a schema is selected, choose the appropriate WSDL file.</span></span>  
  
 <span data-ttu-id="25daa-107">以下代码摘自**displayUI** AdapterManagement.cs 文件的方法。</span><span class="sxs-lookup"><span data-stu-id="25daa-107">The following code is from the **displayUI** method of the AdapterManagement.cs file.</span></span>  
  
```  
/// <summary>  
        /// Acquire wsdl(s) from which to build the user interface  
        /// </summary>  
        /// <param name="endPointConfiguration"></param>  
        /// <param name="owner"></param>  
        /// <param name="WSDLList">Array of custom UI's WSDL (returned)</param>  
        /// <returns></returns>  
        public Result DisplayUI(IPropertyBag endPointConfiguration,   
            IWin32Window owner,  
            out string [] WSDLList)   
      {  
            WSDLList = new string[1];  
            WSDLList[0] = GetResource("AdapterManagement.service1.wsdl");  
            return Result.Continue;  
        }  
```