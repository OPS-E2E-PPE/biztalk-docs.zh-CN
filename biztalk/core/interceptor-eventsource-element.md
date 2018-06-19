---
title: 拦截器 EventSource 元素 |Microsoft 文档
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
ms.openlocfilehash: 35b5cd6b2e872f689988f3d10d18df002f66d6a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257469"
---
# <a name="interceptor-eventsource-element"></a><span data-ttu-id="81df5-102">侦听器 EventSource 元素</span><span class="sxs-lookup"><span data-stu-id="81df5-102">Interceptor EventSource Element</span></span>
<span data-ttu-id="81df5-103">**EventSource**元素提供有关的一个或多个显示在侦听器配置文件中的事件源的信息。</span><span class="sxs-lookup"><span data-stu-id="81df5-103">The **EventSource** element provides information about the source of one or more of the events appearing in the interceptor configuration file.</span></span> <span data-ttu-id="81df5-104">除事件源名称之外，您还需要指示源的技术和清单。</span><span class="sxs-lookup"><span data-stu-id="81df5-104">In addition to an event source name, you need to indicate the technology and a manifest for the source.</span></span>  
  
## <a name="format"></a><span data-ttu-id="81df5-105">格式</span><span class="sxs-lookup"><span data-stu-id="81df5-105">Format</span></span>  
 <span data-ttu-id="81df5-106">`EventSource` 元素具有三个属性，该元素可能包含或不包含子元素，这取决于包含的架构。</span><span class="sxs-lookup"><span data-stu-id="81df5-106">The `EventSource` element has three attributes and may or may not have child elements depending upon which schemas are included.</span></span> <span data-ttu-id="81df5-107">例如，WCF 架构 WcfInterceptorConfiguration.xsd 提供 `NamespaceMapping` 元素。</span><span class="sxs-lookup"><span data-stu-id="81df5-107">For example, the WCF schema WcfInterceptorConfiguration.xsd provides for the `NamespaceMapping` element.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81df5-108">属性</span><span class="sxs-lookup"><span data-stu-id="81df5-108">Attributes</span></span>  
  
|<span data-ttu-id="81df5-109">属性名称</span><span class="sxs-lookup"><span data-stu-id="81df5-109">Attribute name</span></span>|<span data-ttu-id="81df5-110">Description</span><span class="sxs-lookup"><span data-stu-id="81df5-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="81df5-111">Name</span><span class="sxs-lookup"><span data-stu-id="81df5-111">Name</span></span>|<span data-ttu-id="81df5-112">该事件源的名称。</span><span class="sxs-lookup"><span data-stu-id="81df5-112">Name for this event source.</span></span> <span data-ttu-id="81df5-113">通过使用此名称**OnEvent**条目以引用源。</span><span class="sxs-lookup"><span data-stu-id="81df5-113">This name is used by **OnEvent** entries to refer to the source.</span></span>|  
|<span data-ttu-id="81df5-114">技术</span><span class="sxs-lookup"><span data-stu-id="81df5-114">Technology</span></span>|<span data-ttu-id="81df5-115">承载清单中指示的事件源的技术类型。</span><span class="sxs-lookup"><span data-stu-id="81df5-115">Technology type hosting the event source indicated in the manifest.</span></span> <span data-ttu-id="81df5-116">使用“WF”表示 Windows Workflow Foundation；使用“WCF”表示 Windows Communication Framework。</span><span class="sxs-lookup"><span data-stu-id="81df5-116">Use "WF" for Windows Workflow Foundation and "WCF" for Windows Communication Framework.</span></span>|  
|<span data-ttu-id="81df5-117">Manifest</span><span class="sxs-lookup"><span data-stu-id="81df5-117">Manifest</span></span>|<span data-ttu-id="81df5-118">用作事件源的类型的程序集限定类名。</span><span class="sxs-lookup"><span data-stu-id="81df5-118">Assembly-qualified class name of the type to use as an event source.</span></span> <span data-ttu-id="81df5-119">例如，使用 IPv4 地址 `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`</span><span class="sxs-lookup"><span data-stu-id="81df5-119">For example, `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`</span></span><br /><br /> <span data-ttu-id="81df5-120">如果你没有公钥标记，使用`PublicKeyToken=null`。</span><span class="sxs-lookup"><span data-stu-id="81df5-120">If you do not have a public key token, use `PublicKeyToken=null`.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="81df5-121">示例</span><span class="sxs-lookup"><span data-stu-id="81df5-121">Example</span></span>  
 <span data-ttu-id="81df5-122">下面的示例包含两个**EventSource**元素，一个目标 WF 和一个目标 WCF。</span><span class="sxs-lookup"><span data-stu-id="81df5-122">The following example contains two **EventSource** elements, one targeting WF and one targeting WCF.</span></span>  
  
```  
<!-- WF -->  
<ic:EventSource Name="OrderWorkflow" Technology="WF" Manifest="SimpleWorkflow.OrderWorkflow, SimpleWorkflow, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
<!-- WCF -->  
<ic:EventSource Name="PurchaseService" Technology="WCF" Manifest="Service.IProcessPOContract, DuplexService, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
```