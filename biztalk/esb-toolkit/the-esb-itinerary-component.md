---
title: ESB 路线组件 |Microsoft Docs
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
ms.openlocfilehash: d0e92c62f0ae764ed8123c578d7bc2975d4b10b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399800"
---
# <a name="the-esb-itinerary-component"></a><span data-ttu-id="d90f4-102">ESB 路线组件</span><span class="sxs-lookup"><span data-stu-id="d90f4-102">The ESB Itinerary Component</span></span>
<span data-ttu-id="d90f4-103">ESB 路线组件设置与消息一起发送到 ESB 路线接入点的 SOAP 标头上下文属性。</span><span class="sxs-lookup"><span data-stu-id="d90f4-103">The ESB Itinerary component sets the context properties from the SOAP header sent along with the message to an ESB itinerary on-ramp.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="d90f4-104">安装</span><span class="sxs-lookup"><span data-stu-id="d90f4-104">Installation</span></span>  
 <span data-ttu-id="d90f4-105">自动安装 ESB 核心安装**路线**BizTalk Server 管道组件文件夹中的管道组件。</span><span class="sxs-lookup"><span data-stu-id="d90f4-105">Installing the ESB Core automatically installs the **Itinerary** pipeline component in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="d90f4-106">其工作原理</span><span class="sxs-lookup"><span data-stu-id="d90f4-106">How It Works</span></span>  
 <span data-ttu-id="d90f4-107">ESB 路线组件是可以仅在接收管道中驻留的 Microsoft BizTalk 管道组件。</span><span class="sxs-lookup"><span data-stu-id="d90f4-107">The ESB Itinerary component is a Microsoft BizTalk pipeline component that can reside only in a receive pipeline.</span></span> <span data-ttu-id="d90f4-108">它将提升从 SOAP 消息标头或组件设置到消息上下文属性的值。</span><span class="sxs-lookup"><span data-stu-id="d90f4-108">It promotes values from either SOAP message headers or component settings into the message context as properties.</span></span> <span data-ttu-id="d90f4-109">您可以找到的升级中使用提供的路线接入点 Web 服务的 SOAP 标头示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d90f4-109">You can find an example of promoting SOAP headers in the Itinerary On-Ramp Web services provided with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="d90f4-110">这些 Web 服务作为其协定的一部分公开的 SOAP 标头和客户端应用程序必须设置标头。</span><span class="sxs-lookup"><span data-stu-id="d90f4-110">These Web services expose SOAP headers as part of their contracts, and client applications must set the headers.</span></span> <span data-ttu-id="d90f4-111">消息通过接收管道中的组件，该组件将读取 SOAP 标头值，并将升级 （写入） 到消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="d90f4-111">As the message passes through the component in a receive pipeline, the component reads the SOAP header values and promotes (writes) them to the message context properties.</span></span>  
  
## <a name="using-the-esb-itinerary-component"></a><span data-ttu-id="d90f4-112">使用 ESB 路线组件</span><span class="sxs-lookup"><span data-stu-id="d90f4-112">Using the ESB Itinerary Component</span></span>  
 <span data-ttu-id="d90f4-113">您可以将 ESB 路线组件添加到接收管道，然后在接收位置使用管道。</span><span class="sxs-lookup"><span data-stu-id="d90f4-113">You can add the ESB Itinerary component to a receive pipeline and then use the pipeline in a receive location.</span></span> <span data-ttu-id="d90f4-114">SOAP 标头值或传入消息的上下文属性的组件设置，会自动将升级该组件。</span><span class="sxs-lookup"><span data-stu-id="d90f4-114">The component automatically promotes SOAP header values or component settings into the context properties of the incoming message.</span></span>  
  
 <span data-ttu-id="d90f4-115">有关如何使用此组件的示例，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="d90f4-115">For an example of how to use this component, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>