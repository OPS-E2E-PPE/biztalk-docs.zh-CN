---
title: TransportType （secondarytransport 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: ed66c7ef-32b6-4110-b932-f96a45a29618
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42e3816287f975370bc411bec593da4f8166481c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243346"
---
# <a name="transporttype-secondarytransport-node"></a><span data-ttu-id="f0502-102">TransportType （secondarytransport 节点）</span><span class="sxs-lookup"><span data-stu-id="f0502-102">TransportType (SecondaryTransport Node)</span></span>
<span data-ttu-id="f0502-103">绑定文件的“SecondaryTransport”节点的“TransportType”节点包含有关适配器的特定信息，该适配器与随同该绑定文件一起导出的传输相关联。</span><span class="sxs-lookup"><span data-stu-id="f0502-103">The TransportType node of the SecondaryTransport node of a binding file contains specific information about the adapter associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="f0502-104">TransportType 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="f0502-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="f0502-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="f0502-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="f0502-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="f0502-106">**Name**</span></span>|<span data-ttu-id="f0502-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="f0502-107">**Node Type**</span></span>|<span data-ttu-id="f0502-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f0502-108">**Data Type**</span></span>|<span data-ttu-id="f0502-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="f0502-109">**Description**</span></span>|<span data-ttu-id="f0502-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="f0502-110">**Restrictions**</span></span>|<span data-ttu-id="f0502-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="f0502-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="f0502-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="f0502-112">Name</span></span>|<span data-ttu-id="f0502-113">特性</span><span class="sxs-lookup"><span data-stu-id="f0502-113">Attribute</span></span>|<span data-ttu-id="f0502-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0502-114">xs:string</span></span>|<span data-ttu-id="f0502-115">指定与此传输关联的适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="f0502-115">Specifies the name of the adapter associated with the transport.</span></span>|<span data-ttu-id="f0502-116">可选</span><span class="sxs-lookup"><span data-stu-id="f0502-116">Not required</span></span>|<span data-ttu-id="f0502-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="f0502-117">Default value: empty</span></span>|  
|<span data-ttu-id="f0502-118">功能</span><span class="sxs-lookup"><span data-stu-id="f0502-118">Capabilities</span></span>|<span data-ttu-id="f0502-119">特性</span><span class="sxs-lookup"><span data-stu-id="f0502-119">Attribute</span></span>|<span data-ttu-id="f0502-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="f0502-120">xs:int</span></span>|<span data-ttu-id="f0502-121">指定与此传输关联的适配器的功能。</span><span class="sxs-lookup"><span data-stu-id="f0502-121">Specifies the capabilities of the adapter associated with the transport.</span></span>|<span data-ttu-id="f0502-122">Required</span><span class="sxs-lookup"><span data-stu-id="f0502-122">Required</span></span>|<span data-ttu-id="f0502-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="f0502-123">Default value: none</span></span><br /><br /> <span data-ttu-id="f0502-124">可能的值包括 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 枚举中的值。</span><span class="sxs-lookup"><span data-stu-id="f0502-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="f0502-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="f0502-125">ConfigurationClsid</span></span>|<span data-ttu-id="f0502-126">特性</span><span class="sxs-lookup"><span data-stu-id="f0502-126">Attribute</span></span>|<span data-ttu-id="f0502-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0502-127">xs:string</span></span>|<span data-ttu-id="f0502-128">指定与此传输关联的适配器的配置 GUID。</span><span class="sxs-lookup"><span data-stu-id="f0502-128">Specifies the configuration GUID of the adapter associated with the transport.</span></span>|<span data-ttu-id="f0502-129">可选</span><span class="sxs-lookup"><span data-stu-id="f0502-129">Not required</span></span>|<span data-ttu-id="f0502-130">默认值：空</span><span class="sxs-lookup"><span data-stu-id="f0502-130">Default value: empty</span></span>|