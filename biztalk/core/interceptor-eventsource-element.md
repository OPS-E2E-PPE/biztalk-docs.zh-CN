---
title: 侦听器 EventSource 元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d78846c1-3984-43af-a13f-9d5c0a66d3b5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 001dfe8c2e4fe09b71bcdd8c053f59938be76cc4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382022"
---
# <a name="interceptor-eventsource-element"></a>侦听器 EventSource 元素
**EventSource**元素提供有关一个或多个侦听器配置文件中显示的事件源的信息。 除了事件源名称，您需要指出的技术和源清单。  
  
## <a name="format"></a>格式  
 `EventSource`元素具有三个属性可能会或可能不包含子元素，具体取决于包含的哪些架构。 例如，WCF 架构 WcfInterceptorConfiguration.xsd 提供`NamespaceMapping`元素。  
  
### <a name="attributes"></a>特性  
  
|属性名称|Description|  
|--------------------|-----------------|  
|“属性”|此事件源的名称。 此名称由**OnEvent**条目以引用源。|  
|技术|承载清单中指示的事件源的技术类型。 "WF"用于 Windows Workflow Foundation 和"WCF"用于 Windows Communication Framework。|  
|清单|要用作事件源的类型的程序集限定类名。 例如： `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`<br /><br /> 如果没有公钥标记，使用`PublicKeyToken=null`。|  
  
## <a name="example"></a>示例  
 下面的示例包含两个**EventSource**元素，一个以 WF 为目标和一个以 WCF 为目标。  
  
```  
<!-- WF -->  
<ic:EventSource Name="OrderWorkflow" Technology="WF" Manifest="SimpleWorkflow.OrderWorkflow, SimpleWorkflow, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
<!-- WCF -->  
<ic:EventSource Name="PurchaseService" Technology="WCF" Manifest="Service.IProcessPOContract, DuplexService, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
```