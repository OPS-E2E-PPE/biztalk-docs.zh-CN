---
title: "拦截器 EventSource 元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d78846c1-3984-43af-a13f-9d5c0a66d3b5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35b5cd6b2e872f689988f3d10d18df002f66d6a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interceptor-eventsource-element"></a>侦听器 EventSource 元素
**EventSource**元素提供有关的一个或多个显示在侦听器配置文件中的事件源的信息。 除事件源名称之外，您还需要指示源的技术和清单。  
  
## <a name="format"></a>格式  
 `EventSource` 元素具有三个属性，该元素可能包含或不包含子元素，这取决于包含的架构。 例如，WCF 架构 WcfInterceptorConfiguration.xsd 提供 `NamespaceMapping` 元素。  
  
### <a name="attributes"></a>属性  
  
|属性名称|Description|  
|--------------------|-----------------|  
|Name|该事件源的名称。 通过使用此名称**OnEvent**条目以引用源。|  
|技术|承载清单中指示的事件源的技术类型。 使用“WF”表示 Windows Workflow Foundation；使用“WCF”表示 Windows Communication Framework。|  
|Manifest|用作事件源的类型的程序集限定类名。 例如，使用 IPv4 地址 `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`<br /><br /> 如果你没有公钥标记，使用`PublicKeyToken=null`。|  
  
## <a name="example"></a>示例  
 下面的示例包含两个**EventSource**元素，一个目标 WF 和一个目标 WCF。  
  
```  
<!-- WF -->  
<ic:EventSource Name="OrderWorkflow" Technology="WF" Manifest="SimpleWorkflow.OrderWorkflow, SimpleWorkflow, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
<!-- WCF -->  
<ic:EventSource Name="PurchaseService" Technology="WCF" Manifest="Service.IProcessPOContract, DuplexService, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
```