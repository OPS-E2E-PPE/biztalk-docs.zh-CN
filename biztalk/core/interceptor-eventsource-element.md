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
# <a name="interceptor-eventsource-element"></a><span data-ttu-id="0c44c-102">侦听器 EventSource 元素</span><span class="sxs-lookup"><span data-stu-id="0c44c-102">Interceptor EventSource Element</span></span>
<span data-ttu-id="0c44c-103">**EventSource**元素提供有关一个或多个侦听器配置文件中显示的事件源的信息。</span><span class="sxs-lookup"><span data-stu-id="0c44c-103">The **EventSource** element provides information about the source of one or more of the events appearing in the interceptor configuration file.</span></span> <span data-ttu-id="0c44c-104">除了事件源名称，您需要指出的技术和源清单。</span><span class="sxs-lookup"><span data-stu-id="0c44c-104">In addition to an event source name, you need to indicate the technology and a manifest for the source.</span></span>  
  
## <a name="format"></a><span data-ttu-id="0c44c-105">格式</span><span class="sxs-lookup"><span data-stu-id="0c44c-105">Format</span></span>  
 <span data-ttu-id="0c44c-106">`EventSource`元素具有三个属性可能会或可能不包含子元素，具体取决于包含的哪些架构。</span><span class="sxs-lookup"><span data-stu-id="0c44c-106">The `EventSource` element has three attributes and may or may not have child elements depending upon which schemas are included.</span></span> <span data-ttu-id="0c44c-107">例如，WCF 架构 WcfInterceptorConfiguration.xsd 提供`NamespaceMapping`元素。</span><span class="sxs-lookup"><span data-stu-id="0c44c-107">For example, the WCF schema WcfInterceptorConfiguration.xsd provides for the `NamespaceMapping` element.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c44c-108">特性</span><span class="sxs-lookup"><span data-stu-id="0c44c-108">Attributes</span></span>  
  
|<span data-ttu-id="0c44c-109">属性名称</span><span class="sxs-lookup"><span data-stu-id="0c44c-109">Attribute name</span></span>|<span data-ttu-id="0c44c-110">Description</span><span class="sxs-lookup"><span data-stu-id="0c44c-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0c44c-111">“属性”</span><span class="sxs-lookup"><span data-stu-id="0c44c-111">Name</span></span>|<span data-ttu-id="0c44c-112">此事件源的名称。</span><span class="sxs-lookup"><span data-stu-id="0c44c-112">Name for this event source.</span></span> <span data-ttu-id="0c44c-113">此名称由**OnEvent**条目以引用源。</span><span class="sxs-lookup"><span data-stu-id="0c44c-113">This name is used by **OnEvent** entries to refer to the source.</span></span>|  
|<span data-ttu-id="0c44c-114">技术</span><span class="sxs-lookup"><span data-stu-id="0c44c-114">Technology</span></span>|<span data-ttu-id="0c44c-115">承载清单中指示的事件源的技术类型。</span><span class="sxs-lookup"><span data-stu-id="0c44c-115">Technology type hosting the event source indicated in the manifest.</span></span> <span data-ttu-id="0c44c-116">"WF"用于 Windows Workflow Foundation 和"WCF"用于 Windows Communication Framework。</span><span class="sxs-lookup"><span data-stu-id="0c44c-116">Use "WF" for Windows Workflow Foundation and "WCF" for Windows Communication Framework.</span></span>|  
|<span data-ttu-id="0c44c-117">清单</span><span class="sxs-lookup"><span data-stu-id="0c44c-117">Manifest</span></span>|<span data-ttu-id="0c44c-118">要用作事件源的类型的程序集限定类名。</span><span class="sxs-lookup"><span data-stu-id="0c44c-118">Assembly-qualified class name of the type to use as an event source.</span></span> <span data-ttu-id="0c44c-119">例如： `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`</span><span class="sxs-lookup"><span data-stu-id="0c44c-119">For example, `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`</span></span><br /><br /> <span data-ttu-id="0c44c-120">如果没有公钥标记，使用`PublicKeyToken=null`。</span><span class="sxs-lookup"><span data-stu-id="0c44c-120">If you do not have a public key token, use `PublicKeyToken=null`.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0c44c-121">示例</span><span class="sxs-lookup"><span data-stu-id="0c44c-121">Example</span></span>  
 <span data-ttu-id="0c44c-122">下面的示例包含两个**EventSource**元素，一个以 WF 为目标和一个以 WCF 为目标。</span><span class="sxs-lookup"><span data-stu-id="0c44c-122">The following example contains two **EventSource** elements, one targeting WF and one targeting WCF.</span></span>  
  
```  
<!-- WF -->  
<ic:EventSource Name="OrderWorkflow" Technology="WF" Manifest="SimpleWorkflow.OrderWorkflow, SimpleWorkflow, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
<!-- WCF -->  
<ic:EventSource Name="PurchaseService" Technology="WCF" Manifest="Service.IProcessPOContract, DuplexService, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
```