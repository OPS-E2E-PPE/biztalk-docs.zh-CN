---
title: TransportType （ReceiveHandler 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: d893b3ac-8e2c-41fb-926c-cea23f6f93b3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f1acfd92363a8378d46caaeaf907efd969c0337
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243237"
---
# <a name="transporttype-receivehandler-node"></a><span data-ttu-id="d89df-102">TransportType （ReceiveHandler 节点）</span><span class="sxs-lookup"><span data-stu-id="d89df-102">TransportType (ReceiveHandler Node)</span></span>
<span data-ttu-id="d89df-103">绑定文件的 ReceiveHandler 节点的 TransportType 节点包含与随绑定文件导出的接收处理程序相关联的适配器有关的特定信息。</span><span class="sxs-lookup"><span data-stu-id="d89df-103">The TransportType node of the ReceiveHandler node of a binding file contains specific information about the adapter associated with a receive handler that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="d89df-104">TransportType 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="d89df-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="d89df-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="d89df-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="d89df-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="d89df-106">**Name**</span></span>|<span data-ttu-id="d89df-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="d89df-107">**Node Type**</span></span>|<span data-ttu-id="d89df-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d89df-108">**Data Type**</span></span>|<span data-ttu-id="d89df-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="d89df-109">**Description**</span></span>|<span data-ttu-id="d89df-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="d89df-110">**Restrictions**</span></span>|<span data-ttu-id="d89df-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="d89df-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="d89df-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="d89df-112">Name</span></span>|<span data-ttu-id="d89df-113">特性</span><span class="sxs-lookup"><span data-stu-id="d89df-113">Attribute</span></span>|<span data-ttu-id="d89df-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="d89df-114">xs:string</span></span>|<span data-ttu-id="d89df-115">指定与接收处理程序相关联的适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="d89df-115">Specifies the name of the adapter associated with the receive handler.</span></span>|<span data-ttu-id="d89df-116">不需要</span><span class="sxs-lookup"><span data-stu-id="d89df-116">Not Required</span></span>|<span data-ttu-id="d89df-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="d89df-117">Default value: empty</span></span>|  
|<span data-ttu-id="d89df-118">功能</span><span class="sxs-lookup"><span data-stu-id="d89df-118">Capabilities</span></span>|<span data-ttu-id="d89df-119">特性</span><span class="sxs-lookup"><span data-stu-id="d89df-119">Attribute</span></span>|<span data-ttu-id="d89df-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="d89df-120">xs:int</span></span>|<span data-ttu-id="d89df-121">指定与接收处理程序相关联的适配器的功能。</span><span class="sxs-lookup"><span data-stu-id="d89df-121">Specifies the capabilities of the adapter associated with the receive handler.</span></span>|<span data-ttu-id="d89df-122">Required</span><span class="sxs-lookup"><span data-stu-id="d89df-122">Required</span></span>|<span data-ttu-id="d89df-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="d89df-123">Default value: none</span></span><br /><br /> <span data-ttu-id="d89df-124">可能的值包括 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 枚举中的值。</span><span class="sxs-lookup"><span data-stu-id="d89df-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="d89df-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="d89df-125">ConfigurationClsid</span></span>|<span data-ttu-id="d89df-126">特性</span><span class="sxs-lookup"><span data-stu-id="d89df-126">Attribute</span></span>|<span data-ttu-id="d89df-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d89df-127">xs:string</span></span>|<span data-ttu-id="d89df-128">指定与接收处理程序相关联的适配器的配置 GUID。</span><span class="sxs-lookup"><span data-stu-id="d89df-128">Specifies the configuration GUID of the adapter associated with the receive handler.</span></span>|<span data-ttu-id="d89df-129">不需要</span><span class="sxs-lookup"><span data-stu-id="d89df-129">Not Required</span></span>|<span data-ttu-id="d89df-130">默认值：空</span><span class="sxs-lookup"><span data-stu-id="d89df-130">Default value: empty</span></span>|