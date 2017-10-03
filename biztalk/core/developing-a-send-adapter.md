---
title: "开发发送适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11b430da-ddba-4827-b9a1-c61338b9c647
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a186aa40ea97c1139521ecf16b4aedac30e57da9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="developing-a-send-adapter"></a><span data-ttu-id="b875b-102">开发发送适配器</span><span class="sxs-lookup"><span data-stu-id="b875b-102">Developing a Send Adapter</span></span>
<span data-ttu-id="b875b-103">本部分介绍在发送适配器中发生的对象交互。</span><span class="sxs-lookup"><span data-stu-id="b875b-103">This section describes the object interactions that occur within send adapters.</span></span> <span data-ttu-id="b875b-104">您可以使用此信息在创建发送适配器时指导自定义适配器开发，或了解本地适配器的工作方式。</span><span class="sxs-lookup"><span data-stu-id="b875b-104">You can use this information to guide custom adapter development when creating send adapters, or to learn about how the native adapters work.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b875b-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="b875b-105">In This Section</span></span>  
  
-   [<span data-ttu-id="b875b-106">发送适配器的交换模式</span><span class="sxs-lookup"><span data-stu-id="b875b-106">Exchange Patterns for Send Adapters</span></span>](../core/exchange-patterns-for-send-adapters.md)  
  
-   [<span data-ttu-id="b875b-107">实例化和初始化发送适配器</span><span class="sxs-lookup"><span data-stu-id="b875b-107">Instantiating and Initializing a Send Adapter</span></span>](../core/instantiating-and-initializing-a-send-adapter.md)  
  
-   [<span data-ttu-id="b875b-108">发送适配器操作</span><span class="sxs-lookup"><span data-stu-id="b875b-108">Send Adapter Operations</span></span>](../core/send-adapter-operations.md)  
  
-   [<span data-ttu-id="b875b-109">对消息进行批处理的发送处理</span><span class="sxs-lookup"><span data-stu-id="b875b-109">Batching Messages for Send Processing</span></span>](../core/batching-messages-for-send-processing.md)  
  
-   [<span data-ttu-id="b875b-110">发送适配器的接口</span><span class="sxs-lookup"><span data-stu-id="b875b-110">Interfaces for Send Adapters</span></span>](../core/interfaces-for-send-adapters.md)  
  
-   [<span data-ttu-id="b875b-111">SSO 支持个发送适配器</span><span class="sxs-lookup"><span data-stu-id="b875b-111">SSO Support for Send Adapters</span></span>](../core/sso-support-for-send-adapters.md)