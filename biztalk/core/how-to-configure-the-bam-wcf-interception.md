---
title: 如何配置 BAM WCF 侦听 |Microsoft Docs
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
ms.openlocfilehash: 51eb7a1a5e7fc8ac6c94af3f16051d85dd8731b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341225"
---
# <a name="how-to-configure-the-bam-wcf-interception"></a><span data-ttu-id="fabc6-102">如何配置 BAM WCF 侦听</span><span class="sxs-lookup"><span data-stu-id="fabc6-102">How to Configure the BAM WCF Interception</span></span>
<span data-ttu-id="fabc6-103">若要配置 BAM WCF 侦听，必须修改侦听器配置文件来访问正确的程序集清单的事件源。</span><span class="sxs-lookup"><span data-stu-id="fabc6-103">To configure BAM for WCF interception, you must modify the interceptor configuration file to access the proper assembly manifest for your event sources.</span></span>  
  
 <span data-ttu-id="fabc6-104">配置事件时必须指定正确格式[XPath](../core/xpath.md)的操作的表达式。</span><span class="sxs-lookup"><span data-stu-id="fabc6-104">When you are configuring the events you must specify properly formatted [XPath](../core/xpath.md) expressions for the actions.</span></span>  
  
 <span data-ttu-id="fabc6-105">您可以创建格式正确[XPath](../core/xpath.md)表达式要在中使用的侦听器配置启用 WCF 跟踪并运行应用程序生成的示例 WCF 日志，其中包含的消息。</span><span class="sxs-lookup"><span data-stu-id="fabc6-105">You can create properly formatted [XPath](../core/xpath.md) expressions to use in the interceptor configuration by enabling WCF tracing and running the application to produce a sample WCF log which contains the message.</span></span> <span data-ttu-id="fabc6-106">可以使用**Microsoft Service Trace Viewer** (SvcTraceViewer.exe) 来查看日志并提取消息。</span><span class="sxs-lookup"><span data-stu-id="fabc6-106">You can use the **Microsoft Service Trace Viewer** (SvcTraceViewer.exe) to view the log and extract the message.</span></span> <span data-ttu-id="fabc6-107">该查看器包含在 WCF sdk。</span><span class="sxs-lookup"><span data-stu-id="fabc6-107">The viewer is included with the WCF SDK.</span></span> <span data-ttu-id="fabc6-108">所需[XPath](../core/xpath.md)可根据消息构成和应用于侦听器配置表达式。</span><span class="sxs-lookup"><span data-stu-id="fabc6-108">The desired [XPath](../core/xpath.md) expression can then be formed based on the message and applied to the interceptor configuration.</span></span>  
  
 <span data-ttu-id="fabc6-109">在配置 BAM WCF 侦听时，很重要的 machine.config 文件中使用的行为扩展与接收位置的自定义行为配置中使用的扩展名匹配。</span><span class="sxs-lookup"><span data-stu-id="fabc6-109">When configuring the BAM WCF interception, it is essential that the behavior extension used in the machine.config file matches the extension used in the custom behavior configuration of the receive location.</span></span> <span data-ttu-id="fabc6-110">更改扩展名称的一个已配置接收位置在 machine.config 文件会导致无法加载的行为。</span><span class="sxs-lookup"><span data-stu-id="fabc6-110">Changing the extension name of a configured receive location in the machine.config file causes the behavior to fail to load.</span></span> <span data-ttu-id="fabc6-111">此外，接收位置的配置 UI 将失败。</span><span class="sxs-lookup"><span data-stu-id="fabc6-111">In addition, the configuration UI of the receive location will fail.</span></span>  
  
 <span data-ttu-id="fabc6-112">对于群集方案中，由于自定义行为仅配置一次，您必须确保群集中的计算机上的所有 machine.config 文件都指定相同的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="fabc6-112">In case of a clustered scenario, since the custom behavior is configured only once, you must ensure that all the machine.config files on the computers in the cluster specify the same file name extension.</span></span>  
  
### <a name="to-set-the-manifest"></a><span data-ttu-id="fabc6-113">若要设置清单</span><span class="sxs-lookup"><span data-stu-id="fabc6-113">To set the manifest</span></span>  
  
1.  <span data-ttu-id="fabc6-114">设置在清单中 eventsource 中侦听配置到 Microsoft.BizTalk.Adapter.Wcf.Runtime.ITwoWayAsyncVoid，Microsoft.BizTalk.Adapter.Wcf.Runtime，版本 = 3.0.1.0，区域性 = 中性，PublicKeyToken = 31bf3856ad364e35</span><span class="sxs-lookup"><span data-stu-id="fabc6-114">Set the manifest in the EventSource in the Interception Configuration to 'Microsoft.BizTalk.Adapter.Wcf.Runtime.ITwoWayAsyncVoid, Microsoft.BizTalk.Adapter.Wcf.Runtime, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fabc6-115">界面更改使用的服务/接收端口的类型。</span><span class="sxs-lookup"><span data-stu-id="fabc6-115">The interface changes based on the type of service/receive port used.</span></span> <span data-ttu-id="fabc6-116">更改清单行，以反映根据下表使用的端口的类型。</span><span class="sxs-lookup"><span data-stu-id="fabc6-116">Change the manifest line to reflect the type of port you are using according to the table below.</span></span>  
  
    |<span data-ttu-id="fabc6-117">端口类型</span><span class="sxs-lookup"><span data-stu-id="fabc6-117">Port Type</span></span>|<span data-ttu-id="fabc6-118">改用</span><span class="sxs-lookup"><span data-stu-id="fabc6-118">Use</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="fabc6-119">双向端口</span><span class="sxs-lookup"><span data-stu-id="fabc6-119">Two-way ports</span></span>|<span data-ttu-id="fabc6-120">ITwoWayAsync</span><span class="sxs-lookup"><span data-stu-id="fabc6-120">ITwoWayAsync</span></span>|  
    |<span data-ttu-id="fabc6-121">单向端口与绑定，它本质上是两个 2 方法 (例如，HTTP)。</span><span class="sxs-lookup"><span data-stu-id="fabc6-121">One-way ports with binding that are inherently two 2 way (for example, HTTP).</span></span>|<span data-ttu-id="fabc6-122">ITwoWayAsyncVoid</span><span class="sxs-lookup"><span data-stu-id="fabc6-122">ITwoWayAsyncVoid</span></span>|  
    |<span data-ttu-id="fabc6-123">单向端口与绑定，它本质上是两个双向事务。</span><span class="sxs-lookup"><span data-stu-id="fabc6-123">One-way ports with binding that are inherently two two-way with transactions.</span></span>|<span data-ttu-id="fabc6-124">ITwoWayAsyncVoidTxn</span><span class="sxs-lookup"><span data-stu-id="fabc6-124">ITwoWayAsyncVoidTxn</span></span>|  
    |<span data-ttu-id="fabc6-125">是一种方式 (例如，MSMQ) 的绑定。</span><span class="sxs-lookup"><span data-stu-id="fabc6-125">Bindings that are one way (for example, MSMQ).</span></span>|<span data-ttu-id="fabc6-126">IOneWayAsync</span><span class="sxs-lookup"><span data-stu-id="fabc6-126">IOneWayAsync</span></span>|  
    |<span data-ttu-id="fabc6-127">事务的单向绑定。</span><span class="sxs-lookup"><span data-stu-id="fabc6-127">Bindings that are one way with transactions.</span></span>|<span data-ttu-id="fabc6-128">IOneWayAsyncTxn</span><span class="sxs-lookup"><span data-stu-id="fabc6-128">IOneWayAsyncTxn</span></span>|  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="fabc6-129">中的筛选器，而不是使用[GetOperationName](../core/getoperationname.md)操作，在下面的示例中突出显示的那样使用 XPath 操作。</span><span class="sxs-lookup"><span data-stu-id="fabc6-129">In the filter, instead of using the [GetOperationName](../core/getoperationname.md) operation, use XPath operation as highlighted in the following sample.</span></span> <span data-ttu-id="fabc6-130">对于泛型协定的所有消息都到达某一泛型操作，此时它们会路由到基于消息本身 （操作属性） 的特定操作。</span><span class="sxs-lookup"><span data-stu-id="fabc6-130">For generic contracts all messages arrive at some generic operation, at which point they get routed to specific operations based on the message itself (Action attribute).</span></span>  
  
2.  <span data-ttu-id="fabc6-131">操作名称将始终是相同的此位置。</span><span class="sxs-lookup"><span data-stu-id="fabc6-131">The operation name will always be the same at this point.</span></span> <span data-ttu-id="fabc6-132">（它使用泛型协定） 的 WCF 适配器使用的方法为 BizTalkSubmit。</span><span class="sxs-lookup"><span data-stu-id="fabc6-132">In case of WCF adapters (which uses generic contracts) the method used is BizTalkSubmit.</span></span> <span data-ttu-id="fabc6-133">可以使用而不是 GetOperationName 操作节点的 XPath 来检索操作名称。</span><span class="sxs-lookup"><span data-stu-id="fabc6-133">You can use an XPath for the Action node instead of GetOperationName to retrieve the operation name.</span></span> <span data-ttu-id="fabc6-134">然后可以对操作名称进行筛选。</span><span class="sxs-lookup"><span data-stu-id="fabc6-134">You can then filter on the operation name.</span></span>  
  
## <a name="sample-interceptor-configurations"></a><span data-ttu-id="fabc6-135">示例侦听器配置</span><span class="sxs-lookup"><span data-stu-id="fabc6-135">Sample Interceptor Configurations</span></span>  
 <span data-ttu-id="fabc6-136">此示例演示 WCF 适配器的 ServiceRequest 和 ServiceReply 的使用情况。</span><span class="sxs-lookup"><span data-stu-id="fabc6-136">This sample shows the usage of ServiceRequest and ServiceReply for the WCF adapter.</span></span> <span data-ttu-id="fabc6-137">在突出显示部分[XPath](../core/xpath.md)要执行的操作的表达式用于筛选而不是使用操作[GetOperationName](../core/getoperationname.md)。</span><span class="sxs-lookup"><span data-stu-id="fabc6-137">In the highlighted section an [XPath](../core/xpath.md) expression on the Action is used to filter on the operation instead of using [GetOperationName](../core/getoperationname.md).</span></span> <span data-ttu-id="fabc6-138">您可以筛选答复，但只能在 ITwoWayAsync 情况下。</span><span class="sxs-lookup"><span data-stu-id="fabc6-138">You can filter on the reply as well, but only in the case of ITwoWayAsync.</span></span> <span data-ttu-id="fabc6-139">所有其他接口不返回任何内容，或者返回空。</span><span class="sxs-lookup"><span data-stu-id="fabc6-139">All other interfaces return nothing or void.</span></span>  
  
### <a name="servicerequest"></a><span data-ttu-id="fabc6-140">ServiceRequest</span><span class="sxs-lookup"><span data-stu-id="fabc6-140">ServiceRequest</span></span>  
  
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
  
### <a name="servicereply"></a><span data-ttu-id="fabc6-141">ServiceReply</span><span class="sxs-lookup"><span data-stu-id="fabc6-141">ServiceReply</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fabc6-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="fabc6-142">See Also</span></span>  
 [<span data-ttu-id="fabc6-143">配置 WCF 适配器以侦听 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="fabc6-143">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)