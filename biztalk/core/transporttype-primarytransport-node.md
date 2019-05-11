---
title: TransportType （PrimaryTransport 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: 9eb377ec-35d8-4b72-85f9-f264f6553c5a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9b3bf1461d13a1de375b3aaa76d959e68f15088
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243360"
---
# <a name="transporttype-primarytransport-node"></a><span data-ttu-id="283ea-102">TransportType （PrimaryTransport 节点）</span><span class="sxs-lookup"><span data-stu-id="283ea-102">TransportType (PrimaryTransport Node)</span></span>
<span data-ttu-id="283ea-103">绑定文件的 PrimaryTransport 节点的 TransportType 节点包含有关与绑定文件一起导出的传输相关联的适配器的特定信息。</span><span class="sxs-lookup"><span data-stu-id="283ea-103">The TransportType node of the PrimaryTransport node of a binding file contains specific information about the adapter associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="283ea-104">TransportType 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="283ea-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="283ea-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="283ea-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="283ea-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="283ea-106">**Name**</span></span>|<span data-ttu-id="283ea-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="283ea-107">**Node Type**</span></span>|<span data-ttu-id="283ea-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="283ea-108">**Data Type**</span></span>|<span data-ttu-id="283ea-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="283ea-109">**Description**</span></span>|<span data-ttu-id="283ea-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="283ea-110">**Restrictions**</span></span>|<span data-ttu-id="283ea-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="283ea-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="283ea-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="283ea-112">Name</span></span>|<span data-ttu-id="283ea-113">特性</span><span class="sxs-lookup"><span data-stu-id="283ea-113">Attribute</span></span>|<span data-ttu-id="283ea-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="283ea-114">xs:string</span></span>|<span data-ttu-id="283ea-115">指定与此传输关联的适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="283ea-115">Specifies the name of the adapter associated with the transport.</span></span>|<span data-ttu-id="283ea-116">可选</span><span class="sxs-lookup"><span data-stu-id="283ea-116">Not required</span></span>|<span data-ttu-id="283ea-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="283ea-117">Default value: empty</span></span>|  
|<span data-ttu-id="283ea-118">功能</span><span class="sxs-lookup"><span data-stu-id="283ea-118">Capabilities</span></span>|<span data-ttu-id="283ea-119">特性</span><span class="sxs-lookup"><span data-stu-id="283ea-119">Attribute</span></span>|<span data-ttu-id="283ea-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="283ea-120">xs:int</span></span>|<span data-ttu-id="283ea-121">指定与此传输关联的适配器的功能。</span><span class="sxs-lookup"><span data-stu-id="283ea-121">Specifies the capabilities of the adapter associated with the transport.</span></span>|<span data-ttu-id="283ea-122">Required</span><span class="sxs-lookup"><span data-stu-id="283ea-122">Required</span></span>|<span data-ttu-id="283ea-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="283ea-123">Default value: none</span></span><br /><br /> <span data-ttu-id="283ea-124">可能的值包括 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 枚举中的值。</span><span class="sxs-lookup"><span data-stu-id="283ea-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="283ea-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="283ea-125">ConfigurationClsid</span></span>|<span data-ttu-id="283ea-126">特性</span><span class="sxs-lookup"><span data-stu-id="283ea-126">Attribute</span></span>|<span data-ttu-id="283ea-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="283ea-127">xs:string</span></span>|<span data-ttu-id="283ea-128">指定与此传输关联的适配器的配置 GUID。</span><span class="sxs-lookup"><span data-stu-id="283ea-128">Specifies the configuration GUID of the adapter associated with the transport.</span></span>|<span data-ttu-id="283ea-129">可选</span><span class="sxs-lookup"><span data-stu-id="283ea-129">Not required</span></span>|<span data-ttu-id="283ea-130">默认值：空</span><span class="sxs-lookup"><span data-stu-id="283ea-130">Default value: empty</span></span>|