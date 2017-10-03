---
title: "使用错误处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc793386-d2ec-4e02-9283-3237f65c9e01
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00547917da65253123cb2067715a09633547eb4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-fault-handling"></a><span data-ttu-id="0c8c1-102">使用错误处理</span><span class="sxs-lookup"><span data-stu-id="0c8c1-102">Using Fault Handling</span></span>
<span data-ttu-id="0c8c1-103">期间[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]故障处理一条异常消息不返回到客户端，除非**FaultException** （或子类型） 引发或**FaultContract**实现。</span><span class="sxs-lookup"><span data-stu-id="0c8c1-103">During [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] fault handling an exception message is not returned to the client unless a **FaultException** (or a subtype) is thrown or a **FaultContract** is implemented.</span></span> <span data-ttu-id="0c8c1-104">因此你可以仅从错误消息本身在这些情况下跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="0c8c1-104">So you can only track data from the fault message itself in these scenarios.</span></span> <span data-ttu-id="0c8c1-105">在回调实现异常自动再次作为错误消息的同时**ServerFault**和**ClientFault**跟踪点。</span><span class="sxs-lookup"><span data-stu-id="0c8c1-105">An exception in callback implementations automatically comes back as a fault message for both **ServerFault** and **ClientFault** track points.</span></span> <span data-ttu-id="0c8c1-106">但是，它将始终返回泛型错误，该错误显示一条常规消息。</span><span class="sxs-lookup"><span data-stu-id="0c8c1-106">However, it will always return a generic fault with a generic message.</span></span> <span data-ttu-id="0c8c1-107">有关 WCF 错误协定的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=83132](http://go.microsoft.com/fwlink/?LinkId=83132)。</span><span class="sxs-lookup"><span data-stu-id="0c8c1-107">For more information about WCF fault contracts, see [http://go.microsoft.com/fwlink/?LinkId=83132](http://go.microsoft.com/fwlink/?LinkId=83132).</span></span>  
  
 <span data-ttu-id="0c8c1-108">你还可以跟踪常量和通过的错误跟踪点的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="0c8c1-108">You can also track constants and context properties through the fault track points.</span></span>  
  
 <span data-ttu-id="0c8c1-109">如果使用的错误中返回异常详细信息**IncludeExceptionDetailInFaults**属性，提取实际的异常消息都通过 XPath。</span><span class="sxs-lookup"><span data-stu-id="0c8c1-109">If exception details are returned in faults using the **IncludeExceptionDetailInFaults** attribute, you extract the actual exception message through the XPath.</span></span>  
  
 <span data-ttu-id="0c8c1-110">错误处理由中定义的错误跟踪点[GetServiceContractCallPoint](../core/getservicecontractcallpoint.md):</span><span class="sxs-lookup"><span data-stu-id="0c8c1-110">Fault handling is provided by the fault track points defined in [GetServiceContractCallPoint](../core/getservicecontractcallpoint.md):</span></span>  
  
-   <span data-ttu-id="0c8c1-111">ServiceFault</span><span class="sxs-lookup"><span data-stu-id="0c8c1-111">ServiceFault</span></span>  
  
-   <span data-ttu-id="0c8c1-112">ClientFault</span><span class="sxs-lookup"><span data-stu-id="0c8c1-112">ClientFault</span></span>  
  
-   <span data-ttu-id="0c8c1-113">CallbackFault</span><span class="sxs-lookup"><span data-stu-id="0c8c1-113">CallbackFault</span></span>  
  
 <span data-ttu-id="0c8c1-114">在使用这些错误跟踪点时，将始终保留错误数据，即使在基于事务的方案中运行。</span><span class="sxs-lookup"><span data-stu-id="0c8c1-114">When using these fault track points, fault data is always persisted, even when operating in a transaction-based scenario.</span></span> <span data-ttu-id="0c8c1-115">在所有非错误跟踪的数据保持事务完整性和非错误跟踪的数据作为回滚对错误的响应。</span><span class="sxs-lookup"><span data-stu-id="0c8c1-115">Transactional integrity is maintained on all non-fault tracked data and non-fault tracked data is rolled back as a response to the fault.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c8c1-116">这些跟踪点应用于的答复路径和仅适用于的 ServiceReply、 ClientReply 和 CallbackReply 服务协定调用点由[GetServiceContractCallPoint](../core/getservicecontractcallpoint.md)。</span><span class="sxs-lookup"><span data-stu-id="0c8c1-116">These track points are applied to the reply path and apply only to the ServiceReply, ClientReply and CallbackReply service contract call points provided by [GetServiceContractCallPoint](../core/getservicecontractcallpoint.md).</span></span>  
  
## <a name="fault-configuration-sample"></a><span data-ttu-id="0c8c1-117">错误配置示例</span><span class="sxs-lookup"><span data-stu-id="0c8c1-117">Fault Configuration Sample</span></span>  
 <span data-ttu-id="0c8c1-118">下面的示例演示如何在跟踪异常消息**ServiceFault**当服务引发**FaultException**中**AuthorizationServiceFault**事件;否则，它跟踪中的操作返回的布尔表达式**AuthorizationServiceReply**事件。</span><span class="sxs-lookup"><span data-stu-id="0c8c1-118">The following sample demonstrates tracking the exception message on a **ServiceFault** when the service throws a **FaultException** in the **AuthorizationServiceFault** event; otherwise it tracks the Boolean expression returned by the operation in the **AuthorizationServiceReply** event.</span></span> <span data-ttu-id="0c8c1-119">任一**AuthorizationServiceReply** OnEvent 或**AuthorizationServiceFault** OnEvent 保持不变。</span><span class="sxs-lookup"><span data-stu-id="0c8c1-119">Either the **AuthorizationServiceReply** OnEvent or the **AuthorizationServiceFault** OnEvent is persisted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c8c1-120">此示例的实现演示 ServiceReply 和 ServiceFault trackpoints 相互独占性。</span><span class="sxs-lookup"><span data-stu-id="0c8c1-120">The implementation of this sample demonstrates the mutual exclusivity of the ServiceReply and ServiceFault trackpoints.</span></span>  
  
```  
<ic:OnEvent IsBegin ="true" IsEnd="false" Name="AuthorizationServiceReply" Source="ESCreditCardService">  
  
  <ic:Filter>  
    <ic:Expression>  
      <wcf:Operation Name="GetServiceContractCallPoint"/>  
      <ic:Operation Name ="Constant">  
        <ic:Argument>ServiceReply</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals"/>  
      <wcf:Operation Name="GetOperationName" />  
      <ic:Operation Name="Constant">  
        <ic:Argument>AuthorizeWithDataContract</ic:Argument>  
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
  
  <ic:Update DataItemName="Status" Type="NVARCHAR">  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Success</ic:Argument>  
      </ic:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
  <ic:Update DataItemName="Result" Type="NVARCHAR">  
    <ic:Expression>  
      <wcf:Operation Name ="XPath">  
        <wcf:Argument>//s:Body/ccservice:*/ccservice:AuthorizeWithDataContractResult</wcf:Argument>  
      </wcf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
  <ic:Update DataItemName ="Service Call Date" Type ="DATETIME">  
    <ic:Expression>  
      <wcf:Operation Name ="GetContextProperty">  
        <wcf:Argument>EventTime</wcf:Argument>  
      </wcf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
</ic:OnEvent>  
  
<ic:OnEvent IsBegin ="true" IsEnd="false" Name="AuthorizationServiceFault" Source="ESCreditCardService">  
  
  <ic:Filter>  
    <ic:Expression>  
      <wcf:Operation Name="GetServiceContractCallPoint"/>  
      <ic:Operation Name ="Constant">  
        <ic:Argument>ServiceFault</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals"/>  
      <wcf:Operation Name="GetOperationName" />  
      <ic:Operation Name="Constant">  
        <ic:Argument>AuthorizeWithDataContract</ic:Argument>  
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
  
  <ic:Update DataItemName="Status" Type="NVARCHAR">  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Fault</ic:Argument>  
      </ic:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
      <ic:Update DataItemName="Source" Type="NVARCHAR">  
        <ic:Expression>  
          <wcf:Operation Name ="XPath">  
            <wcf:Argument>//s:Body/Fault/Reason/Text</wcf:Argument>  
          </wcf:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
  <ic:Update DataItemName ="Service Call Date" Type ="DATETIME">  
    <ic:Expression>  
      <wcf:Operation Name ="GetContextProperty">  
        <wcf:Argument>EventTime</wcf:Argument>  
      </wcf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
</ic:OnEvent>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c8c1-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c8c1-121">See Also</span></span>  
 [<span data-ttu-id="0c8c1-122">配置 WCF 适配器以截获 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="0c8c1-122">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)