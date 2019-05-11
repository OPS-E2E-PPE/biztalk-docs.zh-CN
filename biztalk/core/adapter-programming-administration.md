---
title: 适配器编程管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38563b3c-6d52-4e4e-ac6e-74f46ce22c6a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c81d056e9775ec0e9273f01aa11be384f632647
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361344"
---
# <a name="adapter-programming-administration"></a><span data-ttu-id="bb29f-102">适配器编程管理</span><span class="sxs-lookup"><span data-stu-id="bb29f-102">Adapter Programming Administration</span></span>
<span data-ttu-id="bb29f-103">适配器是一种特殊的配置存储应用程序： 即适配器是与其他单一登录和配置应用商店应用程序共享命名空间的组件。</span><span class="sxs-lookup"><span data-stu-id="bb29f-103">An adapter is a special type of configuration store application: that is, an adapter is a component that shares a namespace with other Single Sign-On and configuration store applications.</span></span> <span data-ttu-id="bb29f-104">因此，您可以访问有关适配器使用 ISSOConfigStore 的信息。</span><span class="sxs-lookup"><span data-stu-id="bb29f-104">Therefore, you can access information about an adapter using ISSOConfigStore.</span></span> <span data-ttu-id="bb29f-105">但与不同的配置应用商店应用程序，您在使用 ISSOAdmin 接口的适配器不执行管理功能。</span><span class="sxs-lookup"><span data-stu-id="bb29f-105">But unlike a configuration store application, you do not perform administrative functions on an adapter with the ISSOAdmin interface.</span></span> <span data-ttu-id="bb29f-106">相反，你管理通过 issopsadmin 来适配器。</span><span class="sxs-lookup"><span data-stu-id="bb29f-106">Instead, you administer an adapter through ISSOPSAdmin.</span></span> <span data-ttu-id="bb29f-107">专用的适配器管理界面的原因是，以便系统能够协调与配置存储的其他活动。</span><span class="sxs-lookup"><span data-stu-id="bb29f-107">The reason for a specialized adapter administration interface is so that the system can coordinate other activities with the configuration store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb29f-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb29f-108">See Also</span></span>  
 <span data-ttu-id="bb29f-109">[适配器编程配置](../core/adapter-programming-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="bb29f-109">[Adapter Programming Configuration](../core/adapter-programming-configuration.md) </span></span>  
 <span data-ttu-id="bb29f-110">[适配器组和组适配器](../core/adapter-groups-and-group-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="bb29f-110">[Adapter Groups and Group Adapters](../core/adapter-groups-and-group-adapters.md) </span></span>  
 [<span data-ttu-id="bb29f-111">密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="bb29f-111">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)