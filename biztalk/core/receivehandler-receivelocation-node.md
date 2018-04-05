---
title: 接收处理程序 （接收位置节点） |Microsoft 文档
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
ms.openlocfilehash: e865886624731414f979c77f3f2e898e417c8b11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receivehandler-receivelocation-node"></a><span data-ttu-id="459c8-102">接收处理程序 （接收位置节点）</span><span class="sxs-lookup"><span data-stu-id="459c8-102">ReceiveHandler (ReceiveLocation Node)</span></span>
<span data-ttu-id="459c8-103">绑定文件的 ReceiveLocation 节点的 ReceiveHandler 节点包含有关接收处理程序的特定信息，该接收处理程序与随同该绑定文件一起导出的传输相关联。</span><span class="sxs-lookup"><span data-stu-id="459c8-103">The ReceiveHandler node of the ReceiveLocation node of a binding file contains specific information about the receive handler associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-receivehandler-node"></a><span data-ttu-id="459c8-104">ReceiveHandler 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="459c8-104">Nodes in the ReceiveHandler node</span></span>  
 <span data-ttu-id="459c8-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="459c8-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="459c8-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="459c8-106">**Name**</span></span>|<span data-ttu-id="459c8-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="459c8-107">**Node Type**</span></span>|<span data-ttu-id="459c8-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="459c8-108">**Data Type**</span></span>|<span data-ttu-id="459c8-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="459c8-109">**Description**</span></span>|<span data-ttu-id="459c8-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="459c8-110">**Restrictions**</span></span>|<span data-ttu-id="459c8-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="459c8-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="459c8-112">Name</span><span class="sxs-lookup"><span data-stu-id="459c8-112">Name</span></span>|<span data-ttu-id="459c8-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="459c8-113">Attribute</span></span>|<span data-ttu-id="459c8-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="459c8-114">xs:string</span></span>|<span data-ttu-id="459c8-115">指定与传输关联的接收处理程序的名称。</span><span class="sxs-lookup"><span data-stu-id="459c8-115">Specifies the name of the receive handler associated with the transport.</span></span>|<span data-ttu-id="459c8-116">可选</span><span class="sxs-lookup"><span data-stu-id="459c8-116">Not required</span></span>|<span data-ttu-id="459c8-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="459c8-117">Default value: empty</span></span>|  
|<span data-ttu-id="459c8-118">HostTrusted</span><span class="sxs-lookup"><span data-stu-id="459c8-118">HostTrusted</span></span>|<span data-ttu-id="459c8-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="459c8-119">Attribute</span></span>|<span data-ttu-id="459c8-120">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="459c8-120">xs:boolean</span></span>|<span data-ttu-id="459c8-121">指定与此接收处理程序关联的主机是否可信任。</span><span class="sxs-lookup"><span data-stu-id="459c8-121">Specifies whether the host associated with the receive handler is trusted.</span></span>|<span data-ttu-id="459c8-122">必需</span><span class="sxs-lookup"><span data-stu-id="459c8-122">Required</span></span>|<span data-ttu-id="459c8-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="459c8-123">Default value: none</span></span><br /><br /> <span data-ttu-id="459c8-124">设置为**true**如果主机是受信任，否则设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="459c8-124">Set to **true** if host is trusted, otherwise set to **false**.</span></span>|  
|[<span data-ttu-id="459c8-125">TransportType （接收处理程序节点）</span><span class="sxs-lookup"><span data-stu-id="459c8-125">TransportType (ReceiveHandler Node)</span></span>](../core/transporttype-receivehandler-node.md)|<span data-ttu-id="459c8-126">录制</span><span class="sxs-lookup"><span data-stu-id="459c8-126">Record</span></span>|<span data-ttu-id="459c8-127">ProtocolType (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="459c8-127">ProtocolType (ComplexType)</span></span>|<span data-ttu-id="459c8-128">指定传输类型，同时也是与此接收处理程序一同使用的适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="459c8-128">Specifies the transport type, which is also the name of the adapter used with this receive handler.</span></span>|<span data-ttu-id="459c8-129">必需</span><span class="sxs-lookup"><span data-stu-id="459c8-129">Required</span></span>|<span data-ttu-id="459c8-130">默认值：无</span><span class="sxs-lookup"><span data-stu-id="459c8-130">Default value: none</span></span>|