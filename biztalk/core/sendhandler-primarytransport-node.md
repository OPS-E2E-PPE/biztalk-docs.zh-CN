---
title: "发送处理程序 （PrimaryTransport 节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SendHandler node [binding file]
ms.assetid: c0b200ee-ecbc-4708-a2c8-c37cd6cd0060
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 029285e9b56aeb91bbca7a7c9eacf6abedc7ebbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sendhandler-primarytransport-node"></a><span data-ttu-id="4ee80-102">SendHandler（PrimaryTransport 节点）</span><span class="sxs-lookup"><span data-stu-id="4ee80-102">SendHandler (PrimaryTransport Node)</span></span>
<span data-ttu-id="4ee80-103">绑定文件的“PrimaryTransport”节点的“SendHandler”节点包含有关发送处理程序的特定信息，该处理程序与随同绑定文件一起导出的传输相关联。</span><span class="sxs-lookup"><span data-stu-id="4ee80-103">The SendHandler node of the PrimaryTransport node of a binding file contains specific information about the send handler associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-sendhandler-node"></a><span data-ttu-id="4ee80-104">发送处理程序节点中的节点</span><span class="sxs-lookup"><span data-stu-id="4ee80-104">Nodes in the SendHandler node</span></span>  
 <span data-ttu-id="4ee80-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="4ee80-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="4ee80-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="4ee80-106">**Name**</span></span>|<span data-ttu-id="4ee80-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="4ee80-107">**Node Type**</span></span>|<span data-ttu-id="4ee80-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4ee80-108">**Data Type**</span></span>|<span data-ttu-id="4ee80-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="4ee80-109">**Description**</span></span>|<span data-ttu-id="4ee80-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="4ee80-110">**Restrictions**</span></span>|<span data-ttu-id="4ee80-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="4ee80-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="4ee80-112">Name</span><span class="sxs-lookup"><span data-stu-id="4ee80-112">Name</span></span>|<span data-ttu-id="4ee80-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="4ee80-113">Attribute</span></span>|<span data-ttu-id="4ee80-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ee80-114">xs:string</span></span>|<span data-ttu-id="4ee80-115">指定发送处理程序与传输相关联的名称。</span><span class="sxs-lookup"><span data-stu-id="4ee80-115">Specifies the name of the send handler associated with the transport.</span></span>|<span data-ttu-id="4ee80-116">可选</span><span class="sxs-lookup"><span data-stu-id="4ee80-116">Not required</span></span>|<span data-ttu-id="4ee80-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="4ee80-117">Default value: empty</span></span>|  
|<span data-ttu-id="4ee80-118">HostTrusted</span><span class="sxs-lookup"><span data-stu-id="4ee80-118">HostTrusted</span></span>|<span data-ttu-id="4ee80-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="4ee80-119">Attribute</span></span>|<span data-ttu-id="4ee80-120">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="4ee80-120">xs:boolean</span></span>|<span data-ttu-id="4ee80-121">指定与发送处理程序关联的主机是否为受信任。</span><span class="sxs-lookup"><span data-stu-id="4ee80-121">Specifies whether the host associated with the send handler is trusted.</span></span>|<span data-ttu-id="4ee80-122">必需</span><span class="sxs-lookup"><span data-stu-id="4ee80-122">Required</span></span>|<span data-ttu-id="4ee80-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="4ee80-123">Default value: none</span></span><br /><br /> <span data-ttu-id="4ee80-124">设置为**true**如果主机是受信任，否则设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="4ee80-124">Set to **true** if host is trusted, otherwise set to **false**.</span></span>|  
|[<span data-ttu-id="4ee80-125">TransportType</span><span class="sxs-lookup"><span data-stu-id="4ee80-125">TransportType</span></span>](../core/transporttype.md)|<span data-ttu-id="4ee80-126">录制</span><span class="sxs-lookup"><span data-stu-id="4ee80-126">Record</span></span>|<span data-ttu-id="4ee80-127">ProtocolType (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="4ee80-127">ProtocolType (ComplexType)</span></span>|<span data-ttu-id="4ee80-128">指定的传输类型，它也是用于此发送处理程序适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="4ee80-128">Specifies the transport type, which is also the name of the adapter used with this send handler.</span></span>|<span data-ttu-id="4ee80-129">必需</span><span class="sxs-lookup"><span data-stu-id="4ee80-129">Required</span></span>|<span data-ttu-id="4ee80-130">默认值：无</span><span class="sxs-lookup"><span data-stu-id="4ee80-130">Default value: none</span></span>|