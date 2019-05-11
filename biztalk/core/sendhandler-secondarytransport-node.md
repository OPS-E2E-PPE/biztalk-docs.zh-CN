---
title: 发送处理程序 （secondarytransport 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendHandler node [binding file]
ms.assetid: 32eb3e87-25ac-461e-9c09-3d6d9bcba3b2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58ab2b9f2ed41bd3fa132a73e28e38866ef18b53
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254402"
---
# <a name="sendhandler-secondarytransport-node"></a><span data-ttu-id="da5ee-102">发送处理程序 （secondarytransport 节点）</span><span class="sxs-lookup"><span data-stu-id="da5ee-102">SendHandler (SecondaryTransport Node)</span></span>
<span data-ttu-id="da5ee-103">绑定文件的 SecondaryTransport 节点的 SendHandler 节点包含有关与绑定文件一起导出的传输相关联的发送处理程序的特定信息。</span><span class="sxs-lookup"><span data-stu-id="da5ee-103">The SendHandler node of the SecondaryTransport node of a binding file contains specific information about the send handler associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-sendhandler-node"></a><span data-ttu-id="da5ee-104">中的 SendHandler 节点的节点</span><span class="sxs-lookup"><span data-stu-id="da5ee-104">Nodes in the SendHandler node</span></span>  
 <span data-ttu-id="da5ee-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="da5ee-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="da5ee-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="da5ee-106">**Name**</span></span>|<span data-ttu-id="da5ee-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="da5ee-107">**Node Type**</span></span>|<span data-ttu-id="da5ee-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="da5ee-108">**Data Type**</span></span>|<span data-ttu-id="da5ee-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="da5ee-109">**Description**</span></span>|<span data-ttu-id="da5ee-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="da5ee-110">**Restrictions**</span></span>|<span data-ttu-id="da5ee-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="da5ee-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="da5ee-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="da5ee-112">Name</span></span>|<span data-ttu-id="da5ee-113">特性</span><span class="sxs-lookup"><span data-stu-id="da5ee-113">Attribute</span></span>|<span data-ttu-id="da5ee-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="da5ee-114">xs:string</span></span>|<span data-ttu-id="da5ee-115">指定与此传输关联的发送处理程序的名称。</span><span class="sxs-lookup"><span data-stu-id="da5ee-115">Specifies the name of the send handler associated with the transport.</span></span>|<span data-ttu-id="da5ee-116">可选</span><span class="sxs-lookup"><span data-stu-id="da5ee-116">Not required</span></span>|<span data-ttu-id="da5ee-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="da5ee-117">Default value: empty</span></span>|  
|<span data-ttu-id="da5ee-118">HostTrusted</span><span class="sxs-lookup"><span data-stu-id="da5ee-118">HostTrusted</span></span>|<span data-ttu-id="da5ee-119">特性</span><span class="sxs-lookup"><span data-stu-id="da5ee-119">Attribute</span></span>|<span data-ttu-id="da5ee-120">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="da5ee-120">xs:boolean</span></span>|<span data-ttu-id="da5ee-121">指定与发送处理程序关联的主机是否受信任。</span><span class="sxs-lookup"><span data-stu-id="da5ee-121">Specifies whether the host associated with the send handler is trusted.</span></span>|<span data-ttu-id="da5ee-122">Required</span><span class="sxs-lookup"><span data-stu-id="da5ee-122">Required</span></span>|<span data-ttu-id="da5ee-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="da5ee-123">Default value: none</span></span><br /><br /> <span data-ttu-id="da5ee-124">设置为 **，则返回 true**如果受信任主机，否则设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="da5ee-124">Set to **true** if host is trusted, otherwise set to **false**.</span></span>|  
|[<span data-ttu-id="da5ee-125">TransportType（“SendHandler”节点）</span><span class="sxs-lookup"><span data-stu-id="da5ee-125">TransportType (SendHandler Node)</span></span>](../core/transporttype-sendhandler-node.md)|<span data-ttu-id="da5ee-126">录制</span><span class="sxs-lookup"><span data-stu-id="da5ee-126">Record</span></span>|<span data-ttu-id="da5ee-127">ProtocolType (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="da5ee-127">ProtocolType (ComplexType)</span></span>|<span data-ttu-id="da5ee-128">指定传输类型，也是与此发送处理程序所用的适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="da5ee-128">Specifies the transport type, which is also the name of the adapter used with this send handler.</span></span>|<span data-ttu-id="da5ee-129">Required</span><span class="sxs-lookup"><span data-stu-id="da5ee-129">Required</span></span>|<span data-ttu-id="da5ee-130">默认值：无</span><span class="sxs-lookup"><span data-stu-id="da5ee-130">Default value: none</span></span>|