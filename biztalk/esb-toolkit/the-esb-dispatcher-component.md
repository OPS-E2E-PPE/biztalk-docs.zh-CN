---
title: ESB 调度程序组件 |Microsoft 文档
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
ms.openlocfilehash: fe377221034637eab23b70c50ccf48a8454a23bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294901"
---
# <a name="the-esb-dispatcher-component"></a><span data-ttu-id="967a5-102">ESB 调度程序组件</span><span class="sxs-lookup"><span data-stu-id="967a5-102">The ESB Dispatcher Component</span></span>
<span data-ttu-id="967a5-103">ESB 调度程序组件内执行了基于消息的路线服务。</span><span class="sxs-lookup"><span data-stu-id="967a5-103">Messaging-based itinerary services are executed inside the ESB Dispatcher component.</span></span> <span data-ttu-id="967a5-104">调度程序组件可以还可以动态地设置出站消息的终结点位置属性，并动态转换消息。</span><span class="sxs-lookup"><span data-stu-id="967a5-104">The Dispatcher component can also dynamically set endpoint location properties for outbound messages and dynamically transform messages.</span></span>  
  
## <a name="component-properties"></a><span data-ttu-id="967a5-105">组件属性</span><span class="sxs-lookup"><span data-stu-id="967a5-105">Component Properties</span></span>  
 <span data-ttu-id="967a5-106">调度程序组件具有六个属性：</span><span class="sxs-lookup"><span data-stu-id="967a5-106">The Dispatcher component has six properties:</span></span>  
  
-   <span data-ttu-id="967a5-107">**RoutingServiceName**。</span><span class="sxs-lookup"><span data-stu-id="967a5-107">**RoutingServiceName**.</span></span> <span data-ttu-id="967a5-108">此属性指定基于消息的路由服务注册的名称。</span><span class="sxs-lookup"><span data-stu-id="967a5-108">This property specifies the registered name for the messaging-based routing service.</span></span> <span data-ttu-id="967a5-109">默认值是**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="967a5-109">The default value is **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
-   <span data-ttu-id="967a5-110">**TransformServiceName**。</span><span class="sxs-lookup"><span data-stu-id="967a5-110">**TransformServiceName**.</span></span> <span data-ttu-id="967a5-111">此属性指定为基于消息的转换服务注册的名称。</span><span class="sxs-lookup"><span data-stu-id="967a5-111">This property specifies the registered name for the messaging-based transform service.</span></span> <span data-ttu-id="967a5-112">默认值是**Microsoft.Practices.ESB.Services.Transform**。</span><span class="sxs-lookup"><span data-stu-id="967a5-112">The default value is **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
-   <span data-ttu-id="967a5-113">**验证**。</span><span class="sxs-lookup"><span data-stu-id="967a5-113">**Validate**.</span></span> <span data-ttu-id="967a5-114">此属性指定是否需要验证消息。</span><span class="sxs-lookup"><span data-stu-id="967a5-114">This property specifies whether a message needs to be validated.</span></span>  
  
-   <span data-ttu-id="967a5-115">**启用**。</span><span class="sxs-lookup"><span data-stu-id="967a5-115">**Enabled**.</span></span> <span data-ttu-id="967a5-116">此属性启用或禁用该组件。</span><span class="sxs-lookup"><span data-stu-id="967a5-116">This property enables or disables the component.</span></span>  
  
-   <span data-ttu-id="967a5-117">**终结点**。</span><span class="sxs-lookup"><span data-stu-id="967a5-117">**Endpoint**.</span></span> <span data-ttu-id="967a5-118">此属性是一种格式注册 BizTalk ESB 工具包中的冲突解决程序连接字符串。</span><span class="sxs-lookup"><span data-stu-id="967a5-118">This property is a resolver connection string in a format registered with BizTalk ESB Toolkit.</span></span>  
  
-   <span data-ttu-id="967a5-119">**映射名称**。</span><span class="sxs-lookup"><span data-stu-id="967a5-119">**Map Name**.</span></span> <span data-ttu-id="967a5-120">此属性为映射的完全限定的名称或连接字符串格式向注册[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="967a5-120">This property is either the fully qualified name of a map or a connection string format registered with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:</span></span>  
  
    -   <span data-ttu-id="967a5-121">下面是映射名称的示例：</span><span class="sxs-lookup"><span data-stu-id="967a5-121">The following is an example of a map name:</span></span>  
  
        ```  
        GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN, GlobalBank.ESB.DynamicResolution.Transforms, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a  
        ```