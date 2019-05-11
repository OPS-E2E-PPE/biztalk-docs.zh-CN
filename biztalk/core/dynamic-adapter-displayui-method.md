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
# <a name="dynamic-adapter-displayui-method"></a>动态适配器 DisplayUI 方法
在此方法**IDynamicAdapterConfig**界面中显示自定义适配器的自定义用户界面。 这使用户能够查看、 选择和导入其 BizTalk 项目基于所选的服务的相关支持文件。  
  
 在文件适配器中，修改中的代码**displayUI** AdapterManagement.cs 文件以便选择要接受的架构类型创建自定义用户界面 (UI) 的方法。 选择架构后，选择适当的 WSDL 文件。  
  
 以下代码摘自**displayUI** AdapterManagement.cs 文件的方法。  
  
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