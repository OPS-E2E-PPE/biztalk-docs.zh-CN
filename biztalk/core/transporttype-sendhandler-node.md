---
title: TransportType （SendHandler 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: ee87a409-33dd-4111-ba6a-ead3bacc80aa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd31acc6cd31e359c1fc448d3468918675553d84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401856"
---
# <a name="transporttype-sendhandler-node"></a><span data-ttu-id="0303f-102">TransportType （SendHandler 节点）</span><span class="sxs-lookup"><span data-stu-id="0303f-102">TransportType (SendHandler Node)</span></span>
<span data-ttu-id="0303f-103">绑定文件的 SendHandler 节点的 TransportType 节点包含有关指定适配器的特定信息，该适配器是与随绑定文件一起导出的发送处理程序关联的适配器。</span><span class="sxs-lookup"><span data-stu-id="0303f-103">The TransportType node of the SendHandler node of a binding file contains specific information about the adapter associated with a send handler that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="0303f-104">TransportType 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="0303f-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="0303f-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="0303f-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="0303f-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="0303f-106">**Name**</span></span>|<span data-ttu-id="0303f-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="0303f-107">**Node Type**</span></span>|<span data-ttu-id="0303f-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0303f-108">**Data Type**</span></span>|<span data-ttu-id="0303f-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="0303f-109">**Description**</span></span>|<span data-ttu-id="0303f-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="0303f-110">**Restrictions**</span></span>|<span data-ttu-id="0303f-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="0303f-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="0303f-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="0303f-112">Name</span></span>|<span data-ttu-id="0303f-113">特性</span><span class="sxs-lookup"><span data-stu-id="0303f-113">Attribute</span></span>|<span data-ttu-id="0303f-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="0303f-114">xs:string</span></span>|<span data-ttu-id="0303f-115">指定与发送处理程序相关联的适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="0303f-115">Specifies the name of the adapter associated with the send handler.</span></span>|<span data-ttu-id="0303f-116">可选</span><span class="sxs-lookup"><span data-stu-id="0303f-116">Not required</span></span>|<span data-ttu-id="0303f-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="0303f-117">Default value: empty</span></span>|  
|<span data-ttu-id="0303f-118">功能</span><span class="sxs-lookup"><span data-stu-id="0303f-118">Capabilities</span></span>|<span data-ttu-id="0303f-119">特性</span><span class="sxs-lookup"><span data-stu-id="0303f-119">Attribute</span></span>|<span data-ttu-id="0303f-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="0303f-120">xs:int</span></span>|<span data-ttu-id="0303f-121">指定与发送处理程序相关联的适配器的功能。</span><span class="sxs-lookup"><span data-stu-id="0303f-121">Specifies the capabilities of the adapter associated with the send handler.</span></span>|<span data-ttu-id="0303f-122">Required</span><span class="sxs-lookup"><span data-stu-id="0303f-122">Required</span></span>|<span data-ttu-id="0303f-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="0303f-123">Default value: none</span></span><br /><br /> <span data-ttu-id="0303f-124">可能的值包括 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 枚举中的值。</span><span class="sxs-lookup"><span data-stu-id="0303f-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="0303f-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="0303f-125">ConfigurationClsid</span></span>|<span data-ttu-id="0303f-126">特性</span><span class="sxs-lookup"><span data-stu-id="0303f-126">Attribute</span></span>|<span data-ttu-id="0303f-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0303f-127">xs:string</span></span>|<span data-ttu-id="0303f-128">指定与发送处理程序相关联的适配器的配置 GUID。</span><span class="sxs-lookup"><span data-stu-id="0303f-128">Specifies the configuration GUID of the adapter associated with the send handler.</span></span>|<span data-ttu-id="0303f-129">可选</span><span class="sxs-lookup"><span data-stu-id="0303f-129">Not required</span></span>|<span data-ttu-id="0303f-130">默认值：空</span><span class="sxs-lookup"><span data-stu-id="0303f-130">Default value: empty</span></span>|