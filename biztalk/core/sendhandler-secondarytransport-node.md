---
title: 发送处理程序 （SecondaryTransport 节点） |Microsoft 文档
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
ms.openlocfilehash: 1f5ecdbb1860c9132133835b8928f85b1e0e1cfb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sendhandler-secondarytransport-node"></a><span data-ttu-id="198ff-102">发送处理程序 （SecondaryTransport 节点）</span><span class="sxs-lookup"><span data-stu-id="198ff-102">SendHandler (SecondaryTransport Node)</span></span>
<span data-ttu-id="198ff-103">绑定文件 SecondaryTransport 节点的发送处理程序节点包含有关发送处理程序与使用绑定文件导出传输关联的特定信息。</span><span class="sxs-lookup"><span data-stu-id="198ff-103">The SendHandler node of the SecondaryTransport node of a binding file contains specific information about the send handler associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-sendhandler-node"></a><span data-ttu-id="198ff-104">发送处理程序节点中的节点</span><span class="sxs-lookup"><span data-stu-id="198ff-104">Nodes in the SendHandler node</span></span>  
 <span data-ttu-id="198ff-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="198ff-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="198ff-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="198ff-106">**Name**</span></span>|<span data-ttu-id="198ff-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="198ff-107">**Node Type**</span></span>|<span data-ttu-id="198ff-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="198ff-108">**Data Type**</span></span>|<span data-ttu-id="198ff-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="198ff-109">**Description**</span></span>|<span data-ttu-id="198ff-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="198ff-110">**Restrictions**</span></span>|<span data-ttu-id="198ff-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="198ff-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="198ff-112">Name</span><span class="sxs-lookup"><span data-stu-id="198ff-112">Name</span></span>|<span data-ttu-id="198ff-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="198ff-113">Attribute</span></span>|<span data-ttu-id="198ff-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="198ff-114">xs:string</span></span>|<span data-ttu-id="198ff-115">指定发送处理程序与传输相关联的名称。</span><span class="sxs-lookup"><span data-stu-id="198ff-115">Specifies the name of the send handler associated with the transport.</span></span>|<span data-ttu-id="198ff-116">可选</span><span class="sxs-lookup"><span data-stu-id="198ff-116">Not required</span></span>|<span data-ttu-id="198ff-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="198ff-117">Default value: empty</span></span>|  
|<span data-ttu-id="198ff-118">HostTrusted</span><span class="sxs-lookup"><span data-stu-id="198ff-118">HostTrusted</span></span>|<span data-ttu-id="198ff-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="198ff-119">Attribute</span></span>|<span data-ttu-id="198ff-120">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="198ff-120">xs:boolean</span></span>|<span data-ttu-id="198ff-121">指定与发送处理程序关联的主机是否为受信任。</span><span class="sxs-lookup"><span data-stu-id="198ff-121">Specifies whether the host associated with the send handler is trusted.</span></span>|<span data-ttu-id="198ff-122">必需</span><span class="sxs-lookup"><span data-stu-id="198ff-122">Required</span></span>|<span data-ttu-id="198ff-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="198ff-123">Default value: none</span></span><br /><br /> <span data-ttu-id="198ff-124">设置为**true**如果主机是受信任，否则设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="198ff-124">Set to **true** if host is trusted, otherwise set to **false**.</span></span>|  
|[<span data-ttu-id="198ff-125">TransportType （发送处理程序节点）</span><span class="sxs-lookup"><span data-stu-id="198ff-125">TransportType (SendHandler Node)</span></span>](../core/transporttype-sendhandler-node.md)|<span data-ttu-id="198ff-126">录制</span><span class="sxs-lookup"><span data-stu-id="198ff-126">Record</span></span>|<span data-ttu-id="198ff-127">ProtocolType (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="198ff-127">ProtocolType (ComplexType)</span></span>|<span data-ttu-id="198ff-128">指定的传输类型，它也是用于此发送处理程序适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="198ff-128">Specifies the transport type, which is also the name of the adapter used with this send handler.</span></span>|<span data-ttu-id="198ff-129">必需</span><span class="sxs-lookup"><span data-stu-id="198ff-129">Required</span></span>|<span data-ttu-id="198ff-130">默认值：无</span><span class="sxs-lookup"><span data-stu-id="198ff-130">Default value: none</span></span>|