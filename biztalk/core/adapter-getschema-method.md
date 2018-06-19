---
title: 适配器 GetSchema 方法 |Microsoft 文档
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
ms.openlocfilehash: 9c40e698b3c373aa4e10a8de2362650a42e71a1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225189"
---
# <a name="adapter-getschema-method"></a>适配器 GetSchema 方法
假定引用的 WSDL 文件只包含架构引用并且不包含嵌入的架构。 在这种情况下，使用**GetSchema**方法**IAdapterConfig**接口以加载 WSDL 文件中从引用的架构。  
  
 在文件适配器示例中，修改中的代码**GetSchema** AdapterManagement.cs 返回不包含在 WSDL 文件的任何外部 XSD 文件的方法。  
  
 下面的代码是从**GetSchema** AdapterManagement.cs 文件的方法。 它在此处将返回空，因为 Service1.wsdl 文件包含嵌入的架构。 如果不是这一情况，将需要返回与 XSD 架构文件相对应的字符串。  
  
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