---
title: 开发发送适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11b430da-ddba-4827-b9a1-c61338b9c647
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6909d181b2dbc76597b1e091e0a1a9cf0beaea9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389670"
---
# <a name="developing-a-send-adapter"></a><span data-ttu-id="1b134-102">开发发送适配器</span><span class="sxs-lookup"><span data-stu-id="1b134-102">Developing a Send Adapter</span></span>
<span data-ttu-id="1b134-103">本部分介绍了发送适配器中发生的对象交互。</span><span class="sxs-lookup"><span data-stu-id="1b134-103">This section describes the object interactions that occur within send adapters.</span></span> <span data-ttu-id="1b134-104">若要创建发送适配器时指导自定义适配器开发，或若要了解有关本地适配器的工作原理，可以使用此信息。</span><span class="sxs-lookup"><span data-stu-id="1b134-104">You can use this information to guide custom adapter development when creating send adapters, or to learn about how the native adapters work.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b134-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="1b134-105">In This Section</span></span>  
  
-   [<span data-ttu-id="1b134-106">发送适配器的交换模式</span><span class="sxs-lookup"><span data-stu-id="1b134-106">Exchange Patterns for Send Adapters</span></span>](../core/exchange-patterns-for-send-adapters.md)  
  
-   [<span data-ttu-id="1b134-107">实例化和初始化发送适配器</span><span class="sxs-lookup"><span data-stu-id="1b134-107">Instantiating and Initializing a Send Adapter</span></span>](../core/instantiating-and-initializing-a-send-adapter.md)  
  
-   [<span data-ttu-id="1b134-108">发送适配器操作</span><span class="sxs-lookup"><span data-stu-id="1b134-108">Send Adapter Operations</span></span>](../core/send-adapter-operations.md)  
  
-   [<span data-ttu-id="1b134-109">为发送处理批处理消息</span><span class="sxs-lookup"><span data-stu-id="1b134-109">Batching Messages for Send Processing</span></span>](../core/batching-messages-for-send-processing.md)  
  
-   [<span data-ttu-id="1b134-110">发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="1b134-110">Interfaces for Send Adapters</span></span>](../core/interfaces-for-send-adapters.md)  
  
-   [<span data-ttu-id="1b134-111">发送适配器的 SSO 支持</span><span class="sxs-lookup"><span data-stu-id="1b134-111">SSO Support for Send Adapters</span></span>](../core/sso-support-for-send-adapters.md)