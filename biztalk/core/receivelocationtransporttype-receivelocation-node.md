---
title: 接收位置传输类型 （ReceiveLocation 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceiveLocationTransportType node [binding file]
ms.assetid: 375076c3-d5e6-4c25-b054-b452e29717e0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aba0abcf71824d1109bb7a47104ab928df247fd0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398134"
---
# <a name="receivelocationtransporttype-receivelocation-node"></a><span data-ttu-id="095a7-102">接收位置传输类型 （ReceiveLocation 节点）</span><span class="sxs-lookup"><span data-stu-id="095a7-102">ReceiveLocationTransportType (ReceiveLocation Node)</span></span>
<span data-ttu-id="095a7-103">绑定文件的 ReceiveLocation 节点的接收位置传输类型节点包含有关与绑定文件一起导出的传输相关联的适配器的特定信息。</span><span class="sxs-lookup"><span data-stu-id="095a7-103">The ReceiveLocationTransportType node of the ReceiveLocation node of a binding file contains specific information about the adapter associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-receivelocationtransporttype-node"></a><span data-ttu-id="095a7-104">节点中的接收位置传输类型节点</span><span class="sxs-lookup"><span data-stu-id="095a7-104">Nodes in the ReceiveLocationTransportType node</span></span>  
 <span data-ttu-id="095a7-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="095a7-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="095a7-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="095a7-106">**Name**</span></span>|<span data-ttu-id="095a7-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="095a7-107">**Node Type**</span></span>|<span data-ttu-id="095a7-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="095a7-108">**Data Type**</span></span>|<span data-ttu-id="095a7-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="095a7-109">**Description**</span></span>|<span data-ttu-id="095a7-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="095a7-110">**Restrictions**</span></span>|<span data-ttu-id="095a7-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="095a7-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="095a7-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="095a7-112">Name</span></span>|<span data-ttu-id="095a7-113">特性</span><span class="sxs-lookup"><span data-stu-id="095a7-113">Attribute</span></span>|<span data-ttu-id="095a7-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="095a7-114">xs:string</span></span>|<span data-ttu-id="095a7-115">指定与此传输关联的适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="095a7-115">Specifies the name of the adapter associated with the transport.</span></span>|<span data-ttu-id="095a7-116">可选</span><span class="sxs-lookup"><span data-stu-id="095a7-116">Not required</span></span>|<span data-ttu-id="095a7-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="095a7-117">Default value: empty</span></span>|  
|<span data-ttu-id="095a7-118">功能</span><span class="sxs-lookup"><span data-stu-id="095a7-118">Capabilities</span></span>|<span data-ttu-id="095a7-119">特性</span><span class="sxs-lookup"><span data-stu-id="095a7-119">Attribute</span></span>|<span data-ttu-id="095a7-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="095a7-120">xs:int</span></span>|<span data-ttu-id="095a7-121">指定与此传输关联的适配器的功能。</span><span class="sxs-lookup"><span data-stu-id="095a7-121">Specifies the capabilities of the adapter associated with the transport.</span></span>|<span data-ttu-id="095a7-122">Required</span><span class="sxs-lookup"><span data-stu-id="095a7-122">Required</span></span>|<span data-ttu-id="095a7-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="095a7-123">Default value: none</span></span><br /><br /> <span data-ttu-id="095a7-124">可能的值包括 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 枚举中的值。</span><span class="sxs-lookup"><span data-stu-id="095a7-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="095a7-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="095a7-125">ConfigurationClsid</span></span>|<span data-ttu-id="095a7-126">特性</span><span class="sxs-lookup"><span data-stu-id="095a7-126">Attribute</span></span>|<span data-ttu-id="095a7-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="095a7-127">xs:string</span></span>|<span data-ttu-id="095a7-128">指定与此传输关联的适配器的配置 GUID。</span><span class="sxs-lookup"><span data-stu-id="095a7-128">Specifies the configuration GUID of the adapter associated with the transport.</span></span>|<span data-ttu-id="095a7-129">可选</span><span class="sxs-lookup"><span data-stu-id="095a7-129">Not required</span></span>|<span data-ttu-id="095a7-130">默认值：空</span><span class="sxs-lookup"><span data-stu-id="095a7-130">Default value: empty</span></span>|