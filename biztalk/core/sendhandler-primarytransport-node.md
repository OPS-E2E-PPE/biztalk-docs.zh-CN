---
title: SendHandler （PrimaryTransport 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendHandler node [binding file]
ms.assetid: c0b200ee-ecbc-4708-a2c8-c37cd6cd0060
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6128a66f766bad0275957f343fd536f01140e80d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254453"
---
# <a name="sendhandler-primarytransport-node"></a><span data-ttu-id="ff3c8-102">SendHandler （PrimaryTransport 节点）</span><span class="sxs-lookup"><span data-stu-id="ff3c8-102">SendHandler (PrimaryTransport Node)</span></span>
<span data-ttu-id="ff3c8-103">绑定文件的 PrimaryTransport 节点的 SendHandler 节点包含有关与绑定文件一起导出的传输相关联的发送处理程序的特定信息。</span><span class="sxs-lookup"><span data-stu-id="ff3c8-103">The SendHandler node of the PrimaryTransport node of a binding file contains specific information about the send handler associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-sendhandler-node"></a><span data-ttu-id="ff3c8-104">中的 SendHandler 节点的节点</span><span class="sxs-lookup"><span data-stu-id="ff3c8-104">Nodes in the SendHandler node</span></span>  
 <span data-ttu-id="ff3c8-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="ff3c8-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="ff3c8-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="ff3c8-106">**Name**</span></span>|<span data-ttu-id="ff3c8-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="ff3c8-107">**Node Type**</span></span>|<span data-ttu-id="ff3c8-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ff3c8-108">**Data Type**</span></span>|<span data-ttu-id="ff3c8-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="ff3c8-109">**Description**</span></span>|<span data-ttu-id="ff3c8-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="ff3c8-110">**Restrictions**</span></span>|<span data-ttu-id="ff3c8-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="ff3c8-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="ff3c8-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="ff3c8-112">Name</span></span>|<span data-ttu-id="ff3c8-113">特性</span><span class="sxs-lookup"><span data-stu-id="ff3c8-113">Attribute</span></span>|<span data-ttu-id="ff3c8-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="ff3c8-114">xs:string</span></span>|<span data-ttu-id="ff3c8-115">指定与此传输关联的发送处理程序的名称。</span><span class="sxs-lookup"><span data-stu-id="ff3c8-115">Specifies the name of the send handler associated with the transport.</span></span>|<span data-ttu-id="ff3c8-116">可选</span><span class="sxs-lookup"><span data-stu-id="ff3c8-116">Not required</span></span>|<span data-ttu-id="ff3c8-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="ff3c8-117">Default value: empty</span></span>|  
|<span data-ttu-id="ff3c8-118">HostTrusted</span><span class="sxs-lookup"><span data-stu-id="ff3c8-118">HostTrusted</span></span>|<span data-ttu-id="ff3c8-119">特性</span><span class="sxs-lookup"><span data-stu-id="ff3c8-119">Attribute</span></span>|<span data-ttu-id="ff3c8-120">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="ff3c8-120">xs:boolean</span></span>|<span data-ttu-id="ff3c8-121">指定与发送处理程序关联的主机是否受信任。</span><span class="sxs-lookup"><span data-stu-id="ff3c8-121">Specifies whether the host associated with the send handler is trusted.</span></span>|<span data-ttu-id="ff3c8-122">Required</span><span class="sxs-lookup"><span data-stu-id="ff3c8-122">Required</span></span>|<span data-ttu-id="ff3c8-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="ff3c8-123">Default value: none</span></span><br /><br /> <span data-ttu-id="ff3c8-124">设置为 **，则返回 true**如果受信任主机，否则设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="ff3c8-124">Set to **true** if host is trusted, otherwise set to **false**.</span></span>|  
|[<span data-ttu-id="ff3c8-125">TransportType</span><span class="sxs-lookup"><span data-stu-id="ff3c8-125">TransportType</span></span>](../core/transporttype.md)|<span data-ttu-id="ff3c8-126">录制</span><span class="sxs-lookup"><span data-stu-id="ff3c8-126">Record</span></span>|<span data-ttu-id="ff3c8-127">ProtocolType (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="ff3c8-127">ProtocolType (ComplexType)</span></span>|<span data-ttu-id="ff3c8-128">指定传输类型，也是与此发送处理程序所用的适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="ff3c8-128">Specifies the transport type, which is also the name of the adapter used with this send handler.</span></span>|<span data-ttu-id="ff3c8-129">Required</span><span class="sxs-lookup"><span data-stu-id="ff3c8-129">Required</span></span>|<span data-ttu-id="ff3c8-130">默认值：无</span><span class="sxs-lookup"><span data-stu-id="ff3c8-130">Default value: none</span></span>|