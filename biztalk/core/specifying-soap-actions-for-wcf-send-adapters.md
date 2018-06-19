---
title: 指定的 SOAP 操作，wcf 发送适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send adapters, mapping
- send adapters, WCF services
- mapping, send adapters
- mapping, WCF send adapters
ms.assetid: fa9878eb-65b5-4ccc-b727-ff7e09ba6302
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 385e92f7801dc2512fbd038bd0b005d95c503e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276637"
---
# <a name="specifying-soap-actions-for-wcf-send-adapters"></a><span data-ttu-id="45d66-102">为 WCF 发送适配器指定 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="45d66-102">Specifying SOAP Actions for WCF Send Adapters</span></span>
<span data-ttu-id="45d66-103">你可以设置**WCF。操作**WCF 发送适配器传输属性对话框中或业务流程中的上下文属性**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="45d66-103">You can set the **WCF.Action** context property in the WCF send adapter transport properties dialog box or in the orchestration **Expression** shapes.</span></span> <span data-ttu-id="45d66-104">如果你设置**WCF。操作**业务流程中的上下文属性，您需要离开**操作**字段保留为空白中静态发送端口的 WCF 适配器传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="45d66-104">If you set the **WCF.Action** context property in the orchestration, you need to leave the **Action** field blank in the WCF adapter transport properties dialog box for the static send ports.</span></span> <span data-ttu-id="45d66-105">如果你还在静态发送端口中，指定操作**WCF。操作**将替代在业务流程中设置的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="45d66-105">If you also specify an action in the static send ports, the **WCF.Action** context property you set in the orchestration will be overridden.</span></span>  
  
 <span data-ttu-id="45d66-106">此外，有两种方法来指定此属性： 单个操作格式和操作映射格式。</span><span class="sxs-lookup"><span data-stu-id="45d66-106">Moreover, there are two ways to specify this property: the single action format and the action mapping format.</span></span> <span data-ttu-id="45d66-107">如果采用单一操作格式设置此属性（例如 http://MyService/IMyContract/MyAction1），则传出消息的“WCF 发送适配器传输属性”对话框中的 SOAP 操作将始终设置为在此属性中指定的值。</span><span class="sxs-lookup"><span data-stu-id="45d66-107">If you set this property in the single action format—for example, http://MyService/IMyContract/MyAction1—the SOAP action in the WCF send adapter transport properties dialog box for outgoing messages is always set to the value specified in this property.</span></span> <span data-ttu-id="45d66-108">或者，可以在业务流程中设置的单个操作格式**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="45d66-108">Alternatively, you can set the single action format in the orchestration **Expression** shape.</span></span> <span data-ttu-id="45d66-109">例如：</span><span class="sxs-lookup"><span data-stu-id="45d66-109">For example,</span></span>  
  
```  
OutboundMessage(WCF.Action)="http://MyService/IMyContract/MyAction1";  
```  
  
 <span data-ttu-id="45d66-110">如果在操作映射格式设置此属性，传出的 SOAP 操作由**BTS。操作**上下文属性。</span><span class="sxs-lookup"><span data-stu-id="45d66-110">If you set this property in the action mapping format, the outgoing SOAP action is determined by the **BTS.Operation** context property.</span></span> <span data-ttu-id="45d66-111">例如，如果此属性设置为 WCF 中的以下 XML 格式发送适配器传输属性对话框中和**BTS。操作**属性设置为**Operation_1**在发送端口业务流程中，WCF 发送适配器使用 http://MyService/IMyContract/MyAction1 传出的 SOAP 操作的。</span><span class="sxs-lookup"><span data-stu-id="45d66-111">For example, if this property is set to the following XML format in the WCF send adapter transport properties dialog box and the **BTS.Operation** property is set to **Operation_1** in the send port in the orchestration, the WCF send adapter uses http://MyService/IMyContract/MyAction1 for the outgoing SOAP action.</span></span>  
  
```  
BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<Operation Name="Operation_1" Action="http://MyService/IMyContract/MyAction1" />  
<Operation Name="Operation_2" Action="http://MyService/IMyContract/MyAction2" />  
<Operation Name="Operation_3" Action="http://MyService/IMyContract/MyAction3" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="45d66-112">指定操作映射**WCF。操作**中**表达式**形状不支持。</span><span class="sxs-lookup"><span data-stu-id="45d66-112">Specifying action mapping for **WCF.Action** in an **Expression** shape is not supported.</span></span> <span data-ttu-id="45d66-113">您需要在 WCF 传输属性对话框中指定操作映射。</span><span class="sxs-lookup"><span data-stu-id="45d66-113">You need to specify the action mapping in the WCF transport properties dialog box.</span></span> <span data-ttu-id="45d66-114">然后 WCF 适配器将通过查找的 SOAP 操作**BTS。操作**上下文属性，业务流程将设置为发送消息所在的端口上操作的名称。</span><span class="sxs-lookup"><span data-stu-id="45d66-114">Then the WCF adapter will look up the SOAP action by using the **BTS.Operation** context property, which the orchestration sets to the name of the operation on the port where the message is sent.</span></span>  
  
 <span data-ttu-id="45d66-115">如果使用基于内容的路由 (CBR) 其中路由传出消息**http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**属性未设置，WCF 发送适配器将设置整个操作映射连接到传出的 WCF 消息的操作字符串。</span><span class="sxs-lookup"><span data-stu-id="45d66-115">If outgoing messages are routed with content-based routing (CBR) where the **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** property is not set, WCF send adapters will set the whole action mapping string to the action of the outgoing WCF messages.</span></span> <span data-ttu-id="45d66-116">若要解决此问题，你可以执行下列其中一项：</span><span class="sxs-lookup"><span data-stu-id="45d66-116">To work around this, you can do one of the following:</span></span>  
  
-   <span data-ttu-id="45d66-117">将发送端口上的操作字段设置为 http://MyService/IMyContract/MyAction1。</span><span class="sxs-lookup"><span data-stu-id="45d66-117">Set the action field on the send port to http://MyService/IMyContract/MyAction1.</span></span>  
  
-   <span data-ttu-id="45d66-118">设置**BTS。操作**在管道中的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="45d66-118">Set the **BTS.Operation** context property in a pipeline.</span></span> <span data-ttu-id="45d66-119">例如，设置的值**http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**到 Operation1。</span><span class="sxs-lookup"><span data-stu-id="45d66-119">For example, set the value of **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** to Operation1.</span></span>  
  
-   <span data-ttu-id="45d66-120">将操作字段保留为空，改用传入消息中的操作。</span><span class="sxs-lookup"><span data-stu-id="45d66-120">Leave the action field blank and use the action from the incoming message instead.</span></span>  
  
 <span data-ttu-id="45d66-121">您也可以通过 BizTalk WCF 服务使用向导来使用包含单一操作或操作映射的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="45d66-121">You can also use the BizTalk WCF Service Consuming Wizard to consume the WCF services with single action or action mapping.</span></span> <span data-ttu-id="45d66-122">有关更多详细信息，请参阅[如何使用 BizTalk WCF 服务使用向导来使用 WCF 服务](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="45d66-122">For more details, see [How to Use the BizTalk WCF Service Consuming Wizard to Consume a WCF Service](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d66-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45d66-123">See Also</span></span>  
 [<span data-ttu-id="45d66-124">配置动态发送端口使用 WCF 适配器上下文属性</span><span class="sxs-lookup"><span data-stu-id="45d66-124">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)