---
title: TransportType （接收处理程序节点） |Microsoft 文档
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
ms.openlocfilehash: df0e041a322b8bb9a144b9ea2bdab5ebb58ac01e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278989"
---
# <a name="transporttype-receivehandler-node"></a><span data-ttu-id="1c922-102">TransportType （接收处理程序节点）</span><span class="sxs-lookup"><span data-stu-id="1c922-102">TransportType (ReceiveHandler Node)</span></span>
<span data-ttu-id="1c922-103">绑定文件的 ReceiveHandler 节点的 TransportType 节点包含与随绑定文件导出的接收处理程序相关联的适配器有关的特定信息。</span><span class="sxs-lookup"><span data-stu-id="1c922-103">The TransportType node of the ReceiveHandler node of a binding file contains specific information about the adapter associated with a receive handler that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="1c922-104">TransportType 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="1c922-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="1c922-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="1c922-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="1c922-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="1c922-106">**Name**</span></span>|<span data-ttu-id="1c922-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="1c922-107">**Node Type**</span></span>|<span data-ttu-id="1c922-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1c922-108">**Data Type**</span></span>|<span data-ttu-id="1c922-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="1c922-109">**Description**</span></span>|<span data-ttu-id="1c922-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="1c922-110">**Restrictions**</span></span>|<span data-ttu-id="1c922-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="1c922-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="1c922-112">Name</span><span class="sxs-lookup"><span data-stu-id="1c922-112">Name</span></span>|<span data-ttu-id="1c922-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="1c922-113">Attribute</span></span>|<span data-ttu-id="1c922-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c922-114">xs:string</span></span>|<span data-ttu-id="1c922-115">指定与接收处理程序相关联的适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="1c922-115">Specifies the name of the adapter associated with the receive handler.</span></span>|<span data-ttu-id="1c922-116">不需要</span><span class="sxs-lookup"><span data-stu-id="1c922-116">Not Required</span></span>|<span data-ttu-id="1c922-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="1c922-117">Default value: empty</span></span>|  
|<span data-ttu-id="1c922-118">功能</span><span class="sxs-lookup"><span data-stu-id="1c922-118">Capabilities</span></span>|<span data-ttu-id="1c922-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="1c922-119">Attribute</span></span>|<span data-ttu-id="1c922-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="1c922-120">xs:int</span></span>|<span data-ttu-id="1c922-121">指定与接收处理程序相关联的适配器的功能。</span><span class="sxs-lookup"><span data-stu-id="1c922-121">Specifies the capabilities of the adapter associated with the receive handler.</span></span>|<span data-ttu-id="1c922-122">Required</span><span class="sxs-lookup"><span data-stu-id="1c922-122">Required</span></span>|<span data-ttu-id="1c922-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="1c922-123">Default value: none</span></span><br /><br /> <span data-ttu-id="1c922-124">可能的值包括 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 枚举中的值。</span><span class="sxs-lookup"><span data-stu-id="1c922-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="1c922-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="1c922-125">ConfigurationClsid</span></span>|<span data-ttu-id="1c922-126">Attribute</span><span class="sxs-lookup"><span data-stu-id="1c922-126">Attribute</span></span>|<span data-ttu-id="1c922-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c922-127">xs:string</span></span>|<span data-ttu-id="1c922-128">指定与接收处理程序相关联的适配器的配置 GUID。</span><span class="sxs-lookup"><span data-stu-id="1c922-128">Specifies the configuration GUID of the adapter associated with the receive handler.</span></span>|<span data-ttu-id="1c922-129">不需要</span><span class="sxs-lookup"><span data-stu-id="1c922-129">Not Required</span></span>|<span data-ttu-id="1c922-130">默认值：空</span><span class="sxs-lookup"><span data-stu-id="1c922-130">Default value: empty</span></span>|