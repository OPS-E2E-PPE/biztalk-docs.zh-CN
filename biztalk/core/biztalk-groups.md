---
title: BizTalk 组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Management database, groups
- groups
- groups, Management database
- groups, about groups
ms.assetid: 197cbcf6-c722-4cbb-9642-3cb8a34757e2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 960f7afa1138e1be3293ae3bc0c65898539630d8
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528303"
---
# <a name="biztalk-groups"></a><span data-ttu-id="ae23f-102">BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="ae23f-102">BizTalk Groups</span></span>

## <a name="overview"></a><span data-ttu-id="ae23f-103">概述</span><span class="sxs-lookup"><span data-stu-id="ae23f-103">Overview</span></span>
<span data-ttu-id="ae23f-104">*BizTalk 组*是一种通常表示企业、 部门、 中心或其他业务部门的需要包含的 BizTalk Server 实现的组织单位。</span><span class="sxs-lookup"><span data-stu-id="ae23f-104">The *BizTalk group* is a unit of organization that usually represents an enterprise, department, hub, or other business unit that requires a contained BizTalk Server implementation.</span></span> <span data-ttu-id="ae23f-105">BizTalk 组拥有与 BizTalk Server 管理数据库的一对一关系 (称为 BizTalk Server 配置数据库中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="ae23f-105">The BizTalk group has a one-to-one relationship with a BizTalk Server Management database (known as the BizTalk Server Configuration database in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae23f-106">虽然[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组可能包含多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机时，任何给定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机都只能与一个相关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。</span><span class="sxs-lookup"><span data-stu-id="ae23f-106">While [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] groups may contain multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers, any given [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer may only be associated with a single [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span>  
  
 <span data-ttu-id="ae23f-107">BizTalk 管理数据库存储 BizTalk 组的配置信息和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]该组中的计算机。</span><span class="sxs-lookup"><span data-stu-id="ae23f-107">The BizTalk Management database stores configuration information for the BizTalk group and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers in that group.</span></span> <span data-ttu-id="ae23f-108">此配置信息指定为服务器和将以物理方式运行此逻辑的消息处理逻辑的一部分。</span><span class="sxs-lookup"><span data-stu-id="ae23f-108">This configuration information specifies part of the message-processing logic for the servers and where this logic will physically run.</span></span> <span data-ttu-id="ae23f-109">有关 BizTalk Server 管理数据库的详细信息，请参阅[BizTalk Server 中的数据库](../core/databases-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="ae23f-109">For more information about the BizTalk Server Management database, see [Databases in BizTalk Server](../core/databases-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="ae23f-110">必须指定组中每个服务器安装相同的 BizTalk Server 管理数据库，以便可以管理从管理控制台的每个服务器。</span><span class="sxs-lookup"><span data-stu-id="ae23f-110">You must specify the same BizTalk Server Management database for each server installation in the group so that you can administer each server from the administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae23f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae23f-111">See Also</span></span>  
 <span data-ttu-id="ae23f-112">[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="ae23f-112">[Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md) </span></span>  
 <span data-ttu-id="ae23f-113">[管理组](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="ae23f-113">[Managing Groups](../core/managing-groups.md) </span></span>  
 [<span data-ttu-id="ae23f-114">实体</span><span class="sxs-lookup"><span data-stu-id="ae23f-114">Entities</span></span>](../core/entities.md)