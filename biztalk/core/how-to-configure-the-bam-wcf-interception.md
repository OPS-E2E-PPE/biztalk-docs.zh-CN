---
title: 如何配置 BAM WCF 截获 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d85aa130-3219-4df1-8974-a44a51a15002
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90577a73abc0291635bf4b7d9bad34a11d1f806
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249205"
---
# <a name="how-to-configure-the-bam-wcf-interception"></a><span data-ttu-id="d7494-102">如何配置 BAM WCF 侦听</span><span class="sxs-lookup"><span data-stu-id="d7494-102">How to Configure the BAM WCF Interception</span></span>
<span data-ttu-id="d7494-103">若要配置用于 WCF 侦听的 BAM，必须修改侦听器配置文件，以便访问事件源的相应程序集清单。</span><span class="sxs-lookup"><span data-stu-id="d7494-103">To configure BAM for WCF interception, you must modify the interceptor configuration file to access the proper assembly manifest for your event sources.</span></span>  
  
 <span data-ttu-id="d7494-104">配置事件时必须指定格式正确[XPath](../core/xpath.md)的操作的表达式。</span><span class="sxs-lookup"><span data-stu-id="d7494-104">When you are configuring the events you must specify properly formatted [XPath](../core/xpath.md) expressions for the actions.</span></span>  
  
 <span data-ttu-id="d7494-105">你可以创建格式正确[XPath](../core/xpath.md)表达式使用在侦听器配置中通过启用 WCF 跟踪和运行应用程序来生成示例 WCF 日志，其中包含该消息。</span><span class="sxs-lookup"><span data-stu-id="d7494-105">You can create properly formatted [XPath](../core/xpath.md) expressions to use in the interceptor configuration by enabling WCF tracing and running the application to produce a sample WCF log which contains the message.</span></span> <span data-ttu-id="d7494-106">你可以使用**Microsoft 服务跟踪查看器**(SvcTraceViewer.exe) 查看日志和提取消息。</span><span class="sxs-lookup"><span data-stu-id="d7494-106">You can use the **Microsoft Service Trace Viewer** (SvcTraceViewer.exe) to view the log and extract the message.</span></span> <span data-ttu-id="d7494-107">该查看器包含在 WCF SDK 中。</span><span class="sxs-lookup"><span data-stu-id="d7494-107">The viewer is included with the WCF SDK.</span></span> <span data-ttu-id="d7494-108">所需[XPath](../core/xpath.md)表达式然后可以在消息形成基于并应用于的侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="d7494-108">The desired [XPath](../core/xpath.md) expression can then be formed based on the message and applied to the interceptor configuration.</span></span>  
  
 <span data-ttu-id="d7494-109">配置 BAM WCF 侦听时，machine.config 文件中使用的行为扩展名应与在接收位置的自定义行为配置中使用的扩展名匹配，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="d7494-109">When configuring the BAM WCF interception, it is essential that the behavior extension used in the machine.config file matches the extension used in the custom behavior configuration of the receive location.</span></span> <span data-ttu-id="d7494-110">在 machine.config 文件中更改已配置的接收位置的扩展名将导致无法加载行为。</span><span class="sxs-lookup"><span data-stu-id="d7494-110">Changing the extension name of a configured receive location in the machine.config file causes the behavior to fail to load.</span></span> <span data-ttu-id="d7494-111">此外，接收位置的配置 UI 将失败。</span><span class="sxs-lookup"><span data-stu-id="d7494-111">In addition, the configuration UI of the receive location will fail.</span></span>  
  
 <span data-ttu-id="d7494-112">就群集方案而言，由于自定义行为仅配置一次，因此必须确保群集中计算机上的所有 machine.config 文件都指定相同文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="d7494-112">In case of a clustered scenario, since the custom behavior is configured only once, you must ensure that all the machine.config files on the computers in the cluster specify the same file name extension.</span></span>  
  
### <a name="to-set-the-manifest"></a><span data-ttu-id="d7494-113">设置清单</span><span class="sxs-lookup"><span data-stu-id="d7494-113">To set the manifest</span></span>  
  
1.  <span data-ttu-id="d7494-114">将侦听配置中 EventSource 中的清单设置为“Microsoft.BizTalk.Adapter.Wcf.Runtime.ITwoWayAsyncVoid, Microsoft.BizTalk.Adapter.Wcf.Runtime, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35”</span><span class="sxs-lookup"><span data-stu-id="d7494-114">Set the manifest in the EventSource in the Interception Configuration to 'Microsoft.BizTalk.Adapter.Wcf.Runtime.ITwoWayAsyncVoid, Microsoft.BizTalk.Adapter.Wcf.Runtime, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7494-115">接口基于使用的服务/接收端口的类型发生更改。</span><span class="sxs-lookup"><span data-stu-id="d7494-115">The interface changes based on the type of service/receive port used.</span></span> <span data-ttu-id="d7494-116">根据下表更改清单行，以反映正在使用的端口类型。</span><span class="sxs-lookup"><span data-stu-id="d7494-116">Change the manifest line to reflect the type of port you are using according to the table below.</span></span>  
  
    |<span data-ttu-id="d7494-117">端口类型</span><span class="sxs-lookup"><span data-stu-id="d7494-117">Port Type</span></span>|<span data-ttu-id="d7494-118">改用</span><span class="sxs-lookup"><span data-stu-id="d7494-118">Use</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="d7494-119">双向端口</span><span class="sxs-lookup"><span data-stu-id="d7494-119">Two-way ports</span></span>|<span data-ttu-id="d7494-120">ITwoWayAsync</span><span class="sxs-lookup"><span data-stu-id="d7494-120">ITwoWayAsync</span></span>|  
    |<span data-ttu-id="d7494-121">带有本质上为两个双向绑定的单向端口（例如 HTTP）。</span><span class="sxs-lookup"><span data-stu-id="d7494-121">One-way ports with binding that are inherently two 2 way (for example, HTTP).</span></span>|<span data-ttu-id="d7494-122">ITwoWayAsyncVoid</span><span class="sxs-lookup"><span data-stu-id="d7494-122">ITwoWayAsyncVoid</span></span>|  
    |<span data-ttu-id="d7494-123">带有本质上为事务的两个双向绑定的单向端口。</span><span class="sxs-lookup"><span data-stu-id="d7494-123">One-way ports with binding that are inherently two two-way with transactions.</span></span>|<span data-ttu-id="d7494-124">ITwoWayAsyncVoidTxn</span><span class="sxs-lookup"><span data-stu-id="d7494-124">ITwoWayAsyncVoidTxn</span></span>|  
    |<span data-ttu-id="d7494-125">单向绑定（例如 MSMQ）。</span><span class="sxs-lookup"><span data-stu-id="d7494-125">Bindings that are one way (for example, MSMQ).</span></span>|<span data-ttu-id="d7494-126">IOneWayAsync</span><span class="sxs-lookup"><span data-stu-id="d7494-126">IOneWayAsync</span></span>|  
    |<span data-ttu-id="d7494-127">事务的单向绑定。</span><span class="sxs-lookup"><span data-stu-id="d7494-127">Bindings that are one way with transactions.</span></span>|<span data-ttu-id="d7494-128">IOneWayAsyncTxn</span><span class="sxs-lookup"><span data-stu-id="d7494-128">IOneWayAsyncTxn</span></span>|  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d7494-129">在筛选器，而不是使用[GetOperationName](../core/getoperationname.md)操作，作为在下面的示例中突出显示使用 XPath 操作。</span><span class="sxs-lookup"><span data-stu-id="d7494-129">In the filter, instead of using the [GetOperationName](../core/getoperationname.md) operation, use XPath operation as highlighted in the following sample.</span></span> <span data-ttu-id="d7494-130">对于泛型协定，所有消息都在某一泛型操作中到达，此时，消息将基于消息本身路由到特定操作（“操作”属性）。</span><span class="sxs-lookup"><span data-stu-id="d7494-130">For generic contracts all messages arrive at some generic operation, at which point they get routed to specific operations based on the message itself (Action attribute).</span></span>  
  
2.  <span data-ttu-id="d7494-131">此时，操作名称始终相同。</span><span class="sxs-lookup"><span data-stu-id="d7494-131">The operation name will always be the same at this point.</span></span> <span data-ttu-id="d7494-132">就使用泛型协定的 WCF 适配器而言，采用的方法为 BizTalkSubmit。</span><span class="sxs-lookup"><span data-stu-id="d7494-132">In case of WCF adapters (which uses generic contracts) the method used is BizTalkSubmit.</span></span> <span data-ttu-id="d7494-133">您可以使用“操作”节点的 XPath（而不是 GetOperationName）来检索操作名称。</span><span class="sxs-lookup"><span data-stu-id="d7494-133">You can use an XPath for the Action node instead of GetOperationName to retrieve the operation name.</span></span> <span data-ttu-id="d7494-134">然后可对操作名称进行筛选。</span><span class="sxs-lookup"><span data-stu-id="d7494-134">You can then filter on the operation name.</span></span>  
  
## <a name="sample-interceptor-configurations"></a><span data-ttu-id="d7494-135">示例侦听器配置</span><span class="sxs-lookup"><span data-stu-id="d7494-135">Sample Interceptor Configurations</span></span>  
 <span data-ttu-id="d7494-136">本示例显示如何使用 WCF 适配器的 ServiceRequest 和 ServiceReply。</span><span class="sxs-lookup"><span data-stu-id="d7494-136">This sample shows the usage of ServiceRequest and ServiceReply for the WCF adapter.</span></span> <span data-ttu-id="d7494-137">突出显示部分中[XPath](../core/xpath.md)操作的表达式用于筛选而不是使用操作[GetOperationName](../core/getoperationname.md)。</span><span class="sxs-lookup"><span data-stu-id="d7494-137">In the highlighted section an [XPath](../core/xpath.md) expression on the Action is used to filter on the operation instead of using [GetOperationName](../core/getoperationname.md).</span></span> <span data-ttu-id="d7494-138">同样，您还可以筛选答复，但只能在 ITwoWayAsync 情况下筛选。</span><span class="sxs-lookup"><span data-stu-id="d7494-138">You can filter on the reply as well, but only in the case of ITwoWayAsync.</span></span> <span data-ttu-id="d7494-139">所有其他接口不会返回任何内容，或者返回空。</span><span class="sxs-lookup"><span data-stu-id="d7494-139">All other interfaces return nothing or void.</span></span>  
  
### <a name="servicerequest"></a><span data-ttu-id="d7494-140">serviceRequest</span><span class="sxs-lookup"><span data-stu-id="d7494-140">ServiceRequest</span></span>  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="WCFServiceRequest" Source="WCFService">  
      <ic:Filter>  
        <ic:Expression>  
          <wcf:Operation Name="GetServiceContractCallPoint"/>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>ServiceRequest</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
          <wcf:Operation Name ="XPath">  
            <wcf:Argument>//s:Header/a:Action</wcf:Argument>  
          </wcf:Operation>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>Operation1</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
          <ic:Operation Name ="And" />  
        </ic:Expression>  
      </ic:Filter>  
  
      <ic:CorrelationID>  
        <ic:Expression>  
          <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
        </ic:Expression>  
      </ic:CorrelationID>  
  
      <ic:Update DataItemName ="Activity Date" Type ="DATETIME">  
        <ic:Expression>  
          <wcf:Operation Name ="GetContextProperty">  
            <wcf:Argument>EventTime</wcf:Argument>  
          </wcf:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
      <ic:Update DataItemName ="Source" Type ="NVARCHAR">  
        <ic:Expression>  
          <ic:Operation Name="Constant">  
            <ic:Argument>WcfAdapter_ServiceRequest</ic:Argument>  
          </ic:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
    </ic:OnEvent>  
```  
  
### <a name="servicereply"></a><span data-ttu-id="d7494-141">ServiceReply</span><span class="sxs-lookup"><span data-stu-id="d7494-141">ServiceReply</span></span>  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="WCFServiceReply" Source="WCFService">  
      <ic:Filter>  
        <ic:Expression>  
          <wcf:Operation Name="GetServiceContractCallPoint"/>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>ServiceReply</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
        </ic:Expression>  
      </ic:Filter>  
  
      <ic:CorrelationID>  
        <ic:Expression>  
          <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
        </ic:Expression>  
      </ic:CorrelationID>  
  
      <ic:Update DataItemName ="Activity Date" Type ="DATETIME">  
        <ic:Expression>  
          <wcf:Operation Name ="GetContextProperty">  
            <wcf:Argument>EventTime</wcf:Argument>  
          </wcf:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
      <ic:Update DataItemName ="Name" Type ="NVARCHAR">  
        <ic:Expression>  
          <ic:Operation Name="Constant">  
            <ic:Argument>WcfAdapter_ServiceReply</ic:Argument>  
          </ic:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
    </ic:OnEvent>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7494-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7494-142">See Also</span></span>  
 [<span data-ttu-id="d7494-143">配置 WCF 适配器以截获 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="d7494-143">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)