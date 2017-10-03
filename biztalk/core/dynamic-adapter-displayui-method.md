---
title: "动态适配器 DisplayUI 方法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9183d2ee-4265-4fee-9d1d-7e2462d8ff37
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd26bc5e5e344f53537e16135bf0a30b8b1443c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-adapter-displayui-method"></a>动态适配器 DisplayUI 方法
上的此方法**IDynamicAdapterConfig**界面显示的自定义适配器的自定义用户界面。 这使用户能够查看、选择基于所选服务的相关支持文件并将它们导入其 BizTalk 项目中。  
  
 在文件适配器中，修改的代码内**displayUI** AdapterManagement.cs 文件以创建用于选择要接受架构类型的自定义用户界面 (UI) 的方法。 选择架构后，选择适当的 WSDL 文件。  
  
 下面的代码是从**displayUI** AdapterManagement.cs 文件的方法。  
  
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