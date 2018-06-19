---
title: TransportType |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: 64eb00be-47c9-473f-aec6-03cb7f948e3b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d9636e7aa6dd8b09bb73678072242ed8b8725a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279333"
---
# <a name="transporttype"></a><span data-ttu-id="74884-102">TransportType</span><span class="sxs-lookup"><span data-stu-id="74884-102">TransportType</span></span>
<span data-ttu-id="74884-103">绑定文件的 SendHandler 节点的 TransportType 节点包含有关指定适配器的特定信息，该适配器是与随绑定文件一起导出的发送处理程序关联的适配器。</span><span class="sxs-lookup"><span data-stu-id="74884-103">The TransportType node of the SendHandler node of a binding file contains specific information about the adapter associated with a send handler that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="74884-104">TransportType 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="74884-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="74884-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="74884-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="74884-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="74884-106">**Name**</span></span>|<span data-ttu-id="74884-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="74884-107">**Node Type**</span></span>|<span data-ttu-id="74884-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="74884-108">**Data Type**</span></span>|<span data-ttu-id="74884-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="74884-109">**Description**</span></span>|<span data-ttu-id="74884-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="74884-110">**Restrictions**</span></span>|<span data-ttu-id="74884-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="74884-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="74884-112">Name</span><span class="sxs-lookup"><span data-stu-id="74884-112">Name</span></span>|<span data-ttu-id="74884-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="74884-113">Attribute</span></span>|<span data-ttu-id="74884-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="74884-114">xs:string</span></span>|<span data-ttu-id="74884-115">指定与发送处理程序相关联的适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="74884-115">Specifies the name of the adapter associated with the send handler.</span></span>|<span data-ttu-id="74884-116">可选</span><span class="sxs-lookup"><span data-stu-id="74884-116">Not required</span></span>|<span data-ttu-id="74884-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="74884-117">Default value: empty</span></span>|  
|<span data-ttu-id="74884-118">功能</span><span class="sxs-lookup"><span data-stu-id="74884-118">Capabilities</span></span>|<span data-ttu-id="74884-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="74884-119">Attribute</span></span>|<span data-ttu-id="74884-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="74884-120">xs:int</span></span>|<span data-ttu-id="74884-121">指定与发送处理程序相关联的适配器的功能。</span><span class="sxs-lookup"><span data-stu-id="74884-121">Specifies the capabilities of the adapter associated with the send handler.</span></span>|<span data-ttu-id="74884-122">Required</span><span class="sxs-lookup"><span data-stu-id="74884-122">Required</span></span>|<span data-ttu-id="74884-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="74884-123">Default value: none</span></span><br /><br /> <span data-ttu-id="74884-124">可能的值包括 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 枚举中的值。</span><span class="sxs-lookup"><span data-stu-id="74884-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="74884-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="74884-125">ConfigurationClsid</span></span>|<span data-ttu-id="74884-126">Attribute</span><span class="sxs-lookup"><span data-stu-id="74884-126">Attribute</span></span>|<span data-ttu-id="74884-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="74884-127">xs:string</span></span>|<span data-ttu-id="74884-128">指定与发送处理程序相关联的适配器的配置 GUID。</span><span class="sxs-lookup"><span data-stu-id="74884-128">Specifies the configuration GUID of the adapter associated with the send handler.</span></span>|<span data-ttu-id="74884-129">可选</span><span class="sxs-lookup"><span data-stu-id="74884-129">Not required</span></span>|<span data-ttu-id="74884-130">默认值：空</span><span class="sxs-lookup"><span data-stu-id="74884-130">Default value: empty</span></span>|