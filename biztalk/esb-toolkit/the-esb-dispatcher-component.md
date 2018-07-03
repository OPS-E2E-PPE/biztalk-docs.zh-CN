---
title: ESB 调度程序组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85655b5f-4717-42d1-b005-0a5592d5653b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16281ff49da6470212e9e8396a051270adf1eef7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982126"
---
# <a name="the-esb-dispatcher-component"></a><span data-ttu-id="b073e-102">ESB 调度程序组件</span><span class="sxs-lookup"><span data-stu-id="b073e-102">The ESB Dispatcher Component</span></span>
<span data-ttu-id="b073e-103">ESB 调度程序组件内执行基于消息传送的路线服务。</span><span class="sxs-lookup"><span data-stu-id="b073e-103">Messaging-based itinerary services are executed inside the ESB Dispatcher component.</span></span> <span data-ttu-id="b073e-104">调度程序组件可以动态地设置终结点的出站消息的位置属性，并动态转换消息。</span><span class="sxs-lookup"><span data-stu-id="b073e-104">The Dispatcher component can also dynamically set endpoint location properties for outbound messages and dynamically transform messages.</span></span>  
  
## <a name="component-properties"></a><span data-ttu-id="b073e-105">组件属性</span><span class="sxs-lookup"><span data-stu-id="b073e-105">Component Properties</span></span>  
 <span data-ttu-id="b073e-106">调度程序组件具有六个属性：</span><span class="sxs-lookup"><span data-stu-id="b073e-106">The Dispatcher component has six properties:</span></span>  
  
- <span data-ttu-id="b073e-107">**RoutingServiceName**。</span><span class="sxs-lookup"><span data-stu-id="b073e-107">**RoutingServiceName**.</span></span> <span data-ttu-id="b073e-108">此属性指定的基于消息的路由服务的注册的名称。</span><span class="sxs-lookup"><span data-stu-id="b073e-108">This property specifies the registered name for the messaging-based routing service.</span></span> <span data-ttu-id="b073e-109">默认值是**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="b073e-109">The default value is **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
- <span data-ttu-id="b073e-110">**TransformServiceName**。</span><span class="sxs-lookup"><span data-stu-id="b073e-110">**TransformServiceName**.</span></span> <span data-ttu-id="b073e-111">此属性指定的基于消息的转换服务的注册的名称。</span><span class="sxs-lookup"><span data-stu-id="b073e-111">This property specifies the registered name for the messaging-based transform service.</span></span> <span data-ttu-id="b073e-112">默认值是**Microsoft.Practices.ESB.Services.Transform**。</span><span class="sxs-lookup"><span data-stu-id="b073e-112">The default value is **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
- <span data-ttu-id="b073e-113">**验证**。</span><span class="sxs-lookup"><span data-stu-id="b073e-113">**Validate**.</span></span> <span data-ttu-id="b073e-114">此属性指定是否需要验证一条消息。</span><span class="sxs-lookup"><span data-stu-id="b073e-114">This property specifies whether a message needs to be validated.</span></span>  
  
- <span data-ttu-id="b073e-115">**启用**。</span><span class="sxs-lookup"><span data-stu-id="b073e-115">**Enabled**.</span></span> <span data-ttu-id="b073e-116">此属性启用或禁用该组件。</span><span class="sxs-lookup"><span data-stu-id="b073e-116">This property enables or disables the component.</span></span>  
  
- <span data-ttu-id="b073e-117">**终结点**。</span><span class="sxs-lookup"><span data-stu-id="b073e-117">**Endpoint**.</span></span> <span data-ttu-id="b073e-118">此属性是注册到 BizTalk ESB 工具包的格式中的冲突解决程序连接字符串。</span><span class="sxs-lookup"><span data-stu-id="b073e-118">This property is a resolver connection string in a format registered with BizTalk ESB Toolkit.</span></span>  
  
- <span data-ttu-id="b073e-119">**将名称映射**。</span><span class="sxs-lookup"><span data-stu-id="b073e-119">**Map Name**.</span></span> <span data-ttu-id="b073e-120">此属性为映射的完全限定的名称或连接字符串格式向注册[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b073e-120">This property is either the fully qualified name of a map or a connection string format registered with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:</span></span>  
  
  -   <span data-ttu-id="b073e-121">下面是映射名称的一个示例：</span><span class="sxs-lookup"><span data-stu-id="b073e-121">The following is an example of a map name:</span></span>  
  
      ```  
      GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN, GlobalBank.ESB.DynamicResolution.Transforms, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a  
      ```