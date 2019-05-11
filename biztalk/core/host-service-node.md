---
title: 主机 （服务节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Host node [binding file]
ms.assetid: 597522db-0336-43b1-b464-d17cffbf25be
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a408b8f1bd269ff45881b31cd8a75d26bbc89a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387520"
---
# <a name="host-service-node"></a><span data-ttu-id="78d2a-102">主机 （服务节点）</span><span class="sxs-lookup"><span data-stu-id="78d2a-102">Host (Service Node)</span></span>
<span data-ttu-id="78d2a-103">绑定文件的服务节点的主机节点描述了与绑定文件一起导出的服务关联的主机。</span><span class="sxs-lookup"><span data-stu-id="78d2a-103">The Host node of the Service node of a binding file describes the host associated with the service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-host-node"></a><span data-ttu-id="78d2a-104">节点中的主机节点</span><span class="sxs-lookup"><span data-stu-id="78d2a-104">Nodes in the Host node</span></span>  
 <span data-ttu-id="78d2a-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="78d2a-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="78d2a-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="78d2a-106">**Name**</span></span>|<span data-ttu-id="78d2a-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="78d2a-107">**Node Type**</span></span>|<span data-ttu-id="78d2a-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="78d2a-108">**Data Type**</span></span>|<span data-ttu-id="78d2a-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="78d2a-109">**Description**</span></span>|<span data-ttu-id="78d2a-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="78d2a-110">**Restrictions**</span></span>|<span data-ttu-id="78d2a-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="78d2a-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="78d2a-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="78d2a-112">Name</span></span>|<span data-ttu-id="78d2a-113">特性</span><span class="sxs-lookup"><span data-stu-id="78d2a-113">Attribute</span></span>|<span data-ttu-id="78d2a-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="78d2a-114">xs:string</span></span>|<span data-ttu-id="78d2a-115">指定的主机的名称。</span><span class="sxs-lookup"><span data-stu-id="78d2a-115">Specifies the name of the host.</span></span>|<span data-ttu-id="78d2a-116">可选</span><span class="sxs-lookup"><span data-stu-id="78d2a-116">Not required</span></span>|<span data-ttu-id="78d2a-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="78d2a-117">Default value: empty</span></span>|  
|<span data-ttu-id="78d2a-118">NTGroupName</span><span class="sxs-lookup"><span data-stu-id="78d2a-118">NTGroupName</span></span>|<span data-ttu-id="78d2a-119">特性</span><span class="sxs-lookup"><span data-stu-id="78d2a-119">Attribute</span></span>|<span data-ttu-id="78d2a-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="78d2a-120">xs:string</span></span>|<span data-ttu-id="78d2a-121">指定与主机关联的 Windows NT 组名称。</span><span class="sxs-lookup"><span data-stu-id="78d2a-121">Specifies the Windows NT Group name associated with the host.</span></span>|<span data-ttu-id="78d2a-122">可选</span><span class="sxs-lookup"><span data-stu-id="78d2a-122">Not required</span></span>|<span data-ttu-id="78d2a-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="78d2a-123">Default value: empty</span></span>|  
|<span data-ttu-id="78d2a-124">类型</span><span class="sxs-lookup"><span data-stu-id="78d2a-124">Type</span></span>|<span data-ttu-id="78d2a-125">特性</span><span class="sxs-lookup"><span data-stu-id="78d2a-125">Attribute</span></span>|<span data-ttu-id="78d2a-126">xs:int</span><span class="sxs-lookup"><span data-stu-id="78d2a-126">xs:int</span></span>|<span data-ttu-id="78d2a-127">指定进程或独立的主机类型。</span><span class="sxs-lookup"><span data-stu-id="78d2a-127">Specifies the host type as in process or isolated.</span></span>|<span data-ttu-id="78d2a-128">Required</span><span class="sxs-lookup"><span data-stu-id="78d2a-128">Required</span></span>|<span data-ttu-id="78d2a-129">默认值：无</span><span class="sxs-lookup"><span data-stu-id="78d2a-129">Default value: none</span></span><br /><br /> <span data-ttu-id="78d2a-130">可能的值所述[Microsoft.BizTalk.ExplorerOM.HostType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.hosttype.aspx)枚举。</span><span class="sxs-lookup"><span data-stu-id="78d2a-130">Possible values are described in the [Microsoft.BizTalk.ExplorerOM.HostType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.hosttype.aspx) enumeration.</span></span>|  
|<span data-ttu-id="78d2a-131">受信任</span><span class="sxs-lookup"><span data-stu-id="78d2a-131">Trusted</span></span>|<span data-ttu-id="78d2a-132">特性</span><span class="sxs-lookup"><span data-stu-id="78d2a-132">Attribute</span></span>|<span data-ttu-id="78d2a-133">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="78d2a-133">xs:boolean</span></span>|<span data-ttu-id="78d2a-134">指定的 BizTalk 主机是否可信任，以收集身份验证信息。</span><span class="sxs-lookup"><span data-stu-id="78d2a-134">Specifies whether the BizTalk host can be trusted to collect authentication information.</span></span>|<span data-ttu-id="78d2a-135">Required</span><span class="sxs-lookup"><span data-stu-id="78d2a-135">Required</span></span>|<span data-ttu-id="78d2a-136">默认值：无</span><span class="sxs-lookup"><span data-stu-id="78d2a-136">Default value: none</span></span><br /><br /> <span data-ttu-id="78d2a-137">设置为 **，则返回 true**如果主机是受信任，否则设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="78d2a-137">Set to **true** if the host is trusted, otherwise set to **false**.</span></span>|