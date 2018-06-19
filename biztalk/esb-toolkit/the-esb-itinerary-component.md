---
title: ESB 路线组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 379edc6a-7d53-4338-87a5-47b5238453a4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80aa7c1ef4bc53ad2e2821eaf8dc4184777900a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294965"
---
# <a name="the-esb-itinerary-component"></a><span data-ttu-id="a8a1e-102">ESB 路线组件</span><span class="sxs-lookup"><span data-stu-id="a8a1e-102">The ESB Itinerary Component</span></span>
<span data-ttu-id="a8a1e-103">ESB 路线组件从 ESB 路线入口随消息一起发送的 SOAP 标头设置的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="a8a1e-103">The ESB Itinerary component sets the context properties from the SOAP header sent along with the message to an ESB itinerary on-ramp.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="a8a1e-104">安装</span><span class="sxs-lookup"><span data-stu-id="a8a1e-104">Installation</span></span>  
 <span data-ttu-id="a8a1e-105">自动安装 ESB 核心安装**路线**BizTalk Server 管道组件文件夹中的管道组件。</span><span class="sxs-lookup"><span data-stu-id="a8a1e-105">Installing the ESB Core automatically installs the **Itinerary** pipeline component in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="a8a1e-106">它是如何工作</span><span class="sxs-lookup"><span data-stu-id="a8a1e-106">How It Works</span></span>  
 <span data-ttu-id="a8a1e-107">ESB 路线组件是可以仅位于接收管道的 Microsoft BizTalk 管道组件。</span><span class="sxs-lookup"><span data-stu-id="a8a1e-107">The ESB Itinerary component is a Microsoft BizTalk pipeline component that can reside only in a receive pipeline.</span></span> <span data-ttu-id="a8a1e-108">它将提升从 SOAP 消息标头或组件设置到消息上下文属性的值。</span><span class="sxs-lookup"><span data-stu-id="a8a1e-108">It promotes values from either SOAP message headers or component settings into the message context as properties.</span></span> <span data-ttu-id="a8a1e-109">你可以找到将提升随附路线上负载增加 Web 服务中的 SOAP 标头的一个示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a8a1e-109">You can find an example of promoting SOAP headers in the Itinerary On-Ramp Web services provided with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="a8a1e-110">这些 Web 服务公开 SOAP 标头作为其协定的一部分，并且客户端应用程序必须设置标头。</span><span class="sxs-lookup"><span data-stu-id="a8a1e-110">These Web services expose SOAP headers as part of their contracts, and client applications must set the headers.</span></span> <span data-ttu-id="a8a1e-111">如消息传递中接收管道的组件，该组件将读取的 SOAP 标头值，并促进 （写入） 到消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="a8a1e-111">As the message passes through the component in a receive pipeline, the component reads the SOAP header values and promotes (writes) them to the message context properties.</span></span>  
  
## <a name="using-the-esb-itinerary-component"></a><span data-ttu-id="a8a1e-112">使用 ESB 路线组件</span><span class="sxs-lookup"><span data-stu-id="a8a1e-112">Using the ESB Itinerary Component</span></span>  
 <span data-ttu-id="a8a1e-113">你可以将 ESB 路线组件添加到接收管道，然后在接收位置使用管道。</span><span class="sxs-lookup"><span data-stu-id="a8a1e-113">You can add the ESB Itinerary component to a receive pipeline and then use the pipeline in a receive location.</span></span> <span data-ttu-id="a8a1e-114">SOAP 标头值或传入消息的上下文属性的组件设置，会自动将升级组件。</span><span class="sxs-lookup"><span data-stu-id="a8a1e-114">The component automatically promotes SOAP header values or component settings into the context properties of the incoming message.</span></span>  
  
 <span data-ttu-id="a8a1e-115">有关如何使用此组件的示例，请参阅[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="a8a1e-115">For an example of how to use this component, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>