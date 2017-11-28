---
title: "适配器编程管理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 38563b3c-6d52-4e4e-ac6e-74f46ce22c6a
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b19e3285357bb067614aae9472eb099470fe27f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-programming-administration"></a><span data-ttu-id="cfc22-102">适配器编程管理</span><span class="sxs-lookup"><span data-stu-id="cfc22-102">Adapter Programming Administration</span></span>
<span data-ttu-id="cfc22-103">适配器是一种特殊的配置应用商店应用程序： 即，适配器是与其他单一登录和配置应用商店应用程序共享一个命名空间的组件。</span><span class="sxs-lookup"><span data-stu-id="cfc22-103">An adapter is a special type of configuration store application: that is, an adapter is a component that shares a namespace with other Single Sign-On and configuration store applications.</span></span> <span data-ttu-id="cfc22-104">因此，您可以使用 ISSOConfigStore 访问有关适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="cfc22-104">Therefore, you can access information about an adapter using ISSOConfigStore.</span></span> <span data-ttu-id="cfc22-105">不过，与配置存储应用程序不同的是，针对适配器执行管理功能时并不使用 ISSOAdmin 界面，</span><span class="sxs-lookup"><span data-stu-id="cfc22-105">But unlike a configuration store application, you do not perform administrative functions on an adapter with the ISSOAdmin interface.</span></span> <span data-ttu-id="cfc22-106">而需通过 ISSOPSAdmin 来管理适配器。</span><span class="sxs-lookup"><span data-stu-id="cfc22-106">Instead, you administer an adapter through ISSOPSAdmin.</span></span> <span data-ttu-id="cfc22-107">使用专用适配器管理界面是为了使系统能够协调与配置存储之间的其他活动。</span><span class="sxs-lookup"><span data-stu-id="cfc22-107">The reason for a specialized adapter administration interface is so that the system can coordinate other activities with the configuration store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc22-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfc22-108">See Also</span></span>  
 <span data-ttu-id="cfc22-109">[适配器编程配置](../core/adapter-programming-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="cfc22-109">[Adapter Programming Configuration](../core/adapter-programming-configuration.md) </span></span>  
 <span data-ttu-id="cfc22-110">[适配器组和组适配器](../core/adapter-groups-and-group-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="cfc22-110">[Adapter Groups and Group Adapters](../core/adapter-groups-and-group-adapters.md) </span></span>  
 [<span data-ttu-id="cfc22-111">密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="cfc22-111">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)