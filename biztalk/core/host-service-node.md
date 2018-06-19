---
title: 主机 （服务节点） |Microsoft 文档
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
ms.openlocfilehash: a9c70c23105a8d2f2ebe389b22ddf910b4166994
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246557"
---
# <a name="host-service-node"></a><span data-ttu-id="3f369-102">主机 （服务节点）</span><span class="sxs-lookup"><span data-stu-id="3f369-102">Host (Service Node)</span></span>
<span data-ttu-id="3f369-103">绑定文件的服务节点的主机节点描述与使用绑定文件导出的服务关联的主机。</span><span class="sxs-lookup"><span data-stu-id="3f369-103">The Host node of the Service node of a binding file describes the host associated with the service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-host-node"></a><span data-ttu-id="3f369-104">在主机节点的节点</span><span class="sxs-lookup"><span data-stu-id="3f369-104">Nodes in the Host node</span></span>  
 <span data-ttu-id="3f369-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="3f369-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="3f369-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="3f369-106">**Name**</span></span>|<span data-ttu-id="3f369-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="3f369-107">**Node Type**</span></span>|<span data-ttu-id="3f369-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3f369-108">**Data Type**</span></span>|<span data-ttu-id="3f369-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="3f369-109">**Description**</span></span>|<span data-ttu-id="3f369-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="3f369-110">**Restrictions**</span></span>|<span data-ttu-id="3f369-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="3f369-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="3f369-112">Name</span><span class="sxs-lookup"><span data-stu-id="3f369-112">Name</span></span>|<span data-ttu-id="3f369-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="3f369-113">Attribute</span></span>|<span data-ttu-id="3f369-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f369-114">xs:string</span></span>|<span data-ttu-id="3f369-115">指定的主机的名称。</span><span class="sxs-lookup"><span data-stu-id="3f369-115">Specifies the name of the host.</span></span>|<span data-ttu-id="3f369-116">可选</span><span class="sxs-lookup"><span data-stu-id="3f369-116">Not required</span></span>|<span data-ttu-id="3f369-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="3f369-117">Default value: empty</span></span>|  
|<span data-ttu-id="3f369-118">NTGroupName</span><span class="sxs-lookup"><span data-stu-id="3f369-118">NTGroupName</span></span>|<span data-ttu-id="3f369-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="3f369-119">Attribute</span></span>|<span data-ttu-id="3f369-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f369-120">xs:string</span></span>|<span data-ttu-id="3f369-121">指定与主机关联的 Windows NT 组名称。</span><span class="sxs-lookup"><span data-stu-id="3f369-121">Specifies the Windows NT Group name associated with the host.</span></span>|<span data-ttu-id="3f369-122">可选</span><span class="sxs-lookup"><span data-stu-id="3f369-122">Not required</span></span>|<span data-ttu-id="3f369-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="3f369-123">Default value: empty</span></span>|  
|<span data-ttu-id="3f369-124">类型</span><span class="sxs-lookup"><span data-stu-id="3f369-124">Type</span></span>|<span data-ttu-id="3f369-125">Attribute</span><span class="sxs-lookup"><span data-stu-id="3f369-125">Attribute</span></span>|<span data-ttu-id="3f369-126">xs:int</span><span class="sxs-lookup"><span data-stu-id="3f369-126">xs:int</span></span>|<span data-ttu-id="3f369-127">指定的主机类型，如下所示进程或隔离。</span><span class="sxs-lookup"><span data-stu-id="3f369-127">Specifies the host type as in process or isolated.</span></span>|<span data-ttu-id="3f369-128">必需</span><span class="sxs-lookup"><span data-stu-id="3f369-128">Required</span></span>|<span data-ttu-id="3f369-129">默认值：无</span><span class="sxs-lookup"><span data-stu-id="3f369-129">Default value: none</span></span><br /><br /> <span data-ttu-id="3f369-130">可能的值中所述[Microsoft.BizTalk.ExplorerOM.HostType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.hosttype.aspx)枚举。</span><span class="sxs-lookup"><span data-stu-id="3f369-130">Possible values are described in the [Microsoft.BizTalk.ExplorerOM.HostType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.hosttype.aspx) enumeration.</span></span>|  
|<span data-ttu-id="3f369-131">受信任</span><span class="sxs-lookup"><span data-stu-id="3f369-131">Trusted</span></span>|<span data-ttu-id="3f369-132">Attribute</span><span class="sxs-lookup"><span data-stu-id="3f369-132">Attribute</span></span>|<span data-ttu-id="3f369-133">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="3f369-133">xs:boolean</span></span>|<span data-ttu-id="3f369-134">指定 BizTalk 主机是否可以信任要收集的身份验证信息。</span><span class="sxs-lookup"><span data-stu-id="3f369-134">Specifies whether the BizTalk host can be trusted to collect authentication information.</span></span>|<span data-ttu-id="3f369-135">必需</span><span class="sxs-lookup"><span data-stu-id="3f369-135">Required</span></span>|<span data-ttu-id="3f369-136">默认值：无</span><span class="sxs-lookup"><span data-stu-id="3f369-136">Default value: none</span></span><br /><br /> <span data-ttu-id="3f369-137">设置为**true**如果主机是受信任，否则设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="3f369-137">Set to **true** if the host is trusted, otherwise set to **false**.</span></span>|