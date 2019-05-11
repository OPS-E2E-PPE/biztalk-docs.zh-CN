---
title: SAP 适配器配置动态端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic ports, configuring
- configuring, dynamic ports
ms.assetid: 4d6569f9-e513-47f3-b2c1-4c21bafb2bf2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72b2f02382c9b6825b91c802bf1fcb6d669284dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373877"
---
# <a name="configure-dynamic-ports-in-the-sap-adapter"></a><span data-ttu-id="510cb-102">SAP 适配器配置动态端口</span><span class="sxs-lookup"><span data-stu-id="510cb-102">Configure dynamic ports in the SAP adapter</span></span>
## <a name="use-message-context-properties"></a><span data-ttu-id="510cb-103">使用消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="510cb-103">Use message context properties</span></span>
<span data-ttu-id="510cb-104">在中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，可以配置有关的动态端口[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="510cb-104">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="510cb-105">因为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是基于 WCF 的适配器，您可以动态地配置的端口[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过使用消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="510cb-105">Because [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by using message context properties.</span></span>  
  
 <span data-ttu-id="510cb-106">有关[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，URI、 操作和绑定可能会确定传入消息上的属性和在表达式形状中，然后指定，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="510cb-106">For the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], the URI, action, and binding might be determined from a property on an incoming message, and then specified in the Expression shape, as shown in the following example:</span></span>  
  
```  
Request2=Request1;  
Request2(WCF.Action)="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET";  
Request2(WCF.BindingType)="sapBinding";  
Request2(WCF.UserName)="YourUserName";  
Request2(WCF.Password)="YourPassword";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="sap://CLIENT=800;LANG=EN;@A/YourSAPHost/00";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="510cb-107">使用中的 WCF-SAP 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您还可以指定的传输类型为`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SAPAdapter"`，其中**SAPAdapter**是添加中的 WCF SAP 适配器的名称[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="510cb-107">If you are using a WCF-SAP adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SAPAdapter"`, where **SAPAdapter** is the name with which you added the WCF-SAP adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="510cb-108">在前面的示例：</span><span class="sxs-lookup"><span data-stu-id="510cb-108">In the preceding example:</span></span>  
  
- <span data-ttu-id="510cb-109">正在从 Request1 消息创建请求 2 消息。</span><span class="sxs-lookup"><span data-stu-id="510cb-109">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="510cb-110">两条消息将映射到操作架构，这在生成使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="510cb-110">Both the messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
- <span data-ttu-id="510cb-111">发送端口是 BizTalk 业务流程中的逻辑发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="510cb-111">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
  <span data-ttu-id="510cb-112">在表达式形状是 BizTalk 业务流程的一部分。</span><span class="sxs-lookup"><span data-stu-id="510cb-112">The Expression shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="510cb-113">在部署业务流程时，还会创建 Wcf-custom 发送端口。</span><span class="sxs-lookup"><span data-stu-id="510cb-113">When you deploy the orchestration, the WCF-Custom send port is also created.</span></span>  
  
  <span data-ttu-id="510cb-114">配置动态端口的详细信息，请参阅[配置动态发送端口使用 WCF 适配器上下文属性](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="510cb-114">For more information on configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="510cb-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="510cb-115">See Also</span></span>  
[<span data-ttu-id="510cb-116">生成块以创建 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="510cb-116">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)