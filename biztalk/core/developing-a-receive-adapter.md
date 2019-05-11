---
title: 开发接收适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd2623c4-dc92-435f-83d4-1b6213f3cf59
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f093b56569f3e61196921812df905d72f368b035
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351504"
---
# <a name="developing-a-receive-adapter"></a><span data-ttu-id="2a9bd-102">开发接收适配器</span><span class="sxs-lookup"><span data-stu-id="2a9bd-102">Developing a Receive Adapter</span></span>
<span data-ttu-id="2a9bd-103">本部分介绍了该对象接收适配器中发生的交互。</span><span class="sxs-lookup"><span data-stu-id="2a9bd-103">This section describes the object interactions that occur within receive adapters.</span></span> <span data-ttu-id="2a9bd-104">若要创建接收适配器时指导自定义适配器开发，或若要了解有关本地适配器的工作原理，可以使用此信息。</span><span class="sxs-lookup"><span data-stu-id="2a9bd-104">You can use this information to guide custom adapter development when creating receive adapters, or to learn about how the native adapters work.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a9bd-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="2a9bd-105">In This Section</span></span>  
  
-   [<span data-ttu-id="2a9bd-106">接收适配器的交换模式</span><span class="sxs-lookup"><span data-stu-id="2a9bd-106">Exchange Patterns for Receive Adapters</span></span>](../core/exchange-patterns-for-receive-adapters.md)  
  
-   [<span data-ttu-id="2a9bd-107">实例化和初始化接收适配器</span><span class="sxs-lookup"><span data-stu-id="2a9bd-107">Instantiating and Initializing a Receive Adapter</span></span>](../core/instantiating-and-initializing-a-receive-adapter.md)  
  
-   [<span data-ttu-id="2a9bd-108">接收适配器操作</span><span class="sxs-lookup"><span data-stu-id="2a9bd-108">Receive Adapter Operations</span></span>](../core/receive-adapter-operations.md)  
  
-   [<span data-ttu-id="2a9bd-109">为接收处理批处理消息</span><span class="sxs-lookup"><span data-stu-id="2a9bd-109">Batching Messages for Receive Processing</span></span>](../core/batching-messages-for-receive-processing.md)  
  
-   [<span data-ttu-id="2a9bd-110">接收适配器的接口</span><span class="sxs-lookup"><span data-stu-id="2a9bd-110">Interfaces for Receive Adapters</span></span>](../core/interfaces-for-receive-adapters.md)  
  
-   [<span data-ttu-id="2a9bd-111">接收适配器的 SSO 支持</span><span class="sxs-lookup"><span data-stu-id="2a9bd-111">SSO Support for Receive Adapters</span></span>](../core/sso-support-for-receive-adapters.md)