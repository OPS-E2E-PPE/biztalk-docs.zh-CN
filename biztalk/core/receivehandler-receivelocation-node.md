---
title: 接收处理程序 （ReceiveLocation 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceiveHandler node [binding file]
ms.assetid: dd105052-ec71-4762-aa74-e8cdb806a6bf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e04d45b94641703b045a3d3d8d571d7586424c57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398163"
---
# <a name="receivehandler-receivelocation-node"></a><span data-ttu-id="38d6a-102">接收处理程序 （ReceiveLocation 节点）</span><span class="sxs-lookup"><span data-stu-id="38d6a-102">ReceiveHandler (ReceiveLocation Node)</span></span>
<span data-ttu-id="38d6a-103">绑定文件的 ReceiveLocation 节点的 ReceiveHandler 节点包含有关与绑定文件一起导出的传输相关联的接收处理程序的特定信息。</span><span class="sxs-lookup"><span data-stu-id="38d6a-103">The ReceiveHandler node of the ReceiveLocation node of a binding file contains specific information about the receive handler associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-receivehandler-node"></a><span data-ttu-id="38d6a-104">节点中的 ReceiveHandler 节点</span><span class="sxs-lookup"><span data-stu-id="38d6a-104">Nodes in the ReceiveHandler node</span></span>  
 <span data-ttu-id="38d6a-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="38d6a-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="38d6a-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="38d6a-106">**Name**</span></span>|<span data-ttu-id="38d6a-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="38d6a-107">**Node Type**</span></span>|<span data-ttu-id="38d6a-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="38d6a-108">**Data Type**</span></span>|<span data-ttu-id="38d6a-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="38d6a-109">**Description**</span></span>|<span data-ttu-id="38d6a-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="38d6a-110">**Restrictions**</span></span>|<span data-ttu-id="38d6a-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="38d6a-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="38d6a-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="38d6a-112">Name</span></span>|<span data-ttu-id="38d6a-113">特性</span><span class="sxs-lookup"><span data-stu-id="38d6a-113">Attribute</span></span>|<span data-ttu-id="38d6a-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="38d6a-114">xs:string</span></span>|<span data-ttu-id="38d6a-115">指定与此传输关联的接收处理程序的名称。</span><span class="sxs-lookup"><span data-stu-id="38d6a-115">Specifies the name of the receive handler associated with the transport.</span></span>|<span data-ttu-id="38d6a-116">可选</span><span class="sxs-lookup"><span data-stu-id="38d6a-116">Not required</span></span>|<span data-ttu-id="38d6a-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="38d6a-117">Default value: empty</span></span>|  
|<span data-ttu-id="38d6a-118">HostTrusted</span><span class="sxs-lookup"><span data-stu-id="38d6a-118">HostTrusted</span></span>|<span data-ttu-id="38d6a-119">特性</span><span class="sxs-lookup"><span data-stu-id="38d6a-119">Attribute</span></span>|<span data-ttu-id="38d6a-120">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="38d6a-120">xs:boolean</span></span>|<span data-ttu-id="38d6a-121">指定与接收处理程序相关联的主机是否受信任。</span><span class="sxs-lookup"><span data-stu-id="38d6a-121">Specifies whether the host associated with the receive handler is trusted.</span></span>|<span data-ttu-id="38d6a-122">Required</span><span class="sxs-lookup"><span data-stu-id="38d6a-122">Required</span></span>|<span data-ttu-id="38d6a-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="38d6a-123">Default value: none</span></span><br /><br /> <span data-ttu-id="38d6a-124">设置为 **，则返回 true**如果受信任主机，否则设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="38d6a-124">Set to **true** if host is trusted, otherwise set to **false**.</span></span>|  
|[<span data-ttu-id="38d6a-125">TransportType（“ReceiveHandler”节点）</span><span class="sxs-lookup"><span data-stu-id="38d6a-125">TransportType (ReceiveHandler Node)</span></span>](../core/transporttype-receivehandler-node.md)|<span data-ttu-id="38d6a-126">录制</span><span class="sxs-lookup"><span data-stu-id="38d6a-126">Record</span></span>|<span data-ttu-id="38d6a-127">ProtocolType (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="38d6a-127">ProtocolType (ComplexType)</span></span>|<span data-ttu-id="38d6a-128">指定传输类型，同时也是使用与此适配器的名称的接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="38d6a-128">Specifies the transport type, which is also the name of the adapter used with this receive handler.</span></span>|<span data-ttu-id="38d6a-129">Required</span><span class="sxs-lookup"><span data-stu-id="38d6a-129">Required</span></span>|<span data-ttu-id="38d6a-130">默认值：无</span><span class="sxs-lookup"><span data-stu-id="38d6a-130">Default value: none</span></span>|