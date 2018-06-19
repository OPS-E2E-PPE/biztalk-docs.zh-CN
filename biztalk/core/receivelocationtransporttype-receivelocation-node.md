---
title: ReceiveLocationTransportType （接收位置节点） |Microsoft 文档
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
ms.openlocfilehash: d0eae3e2c4fd9f5f668cb12ffd630640b1b63c74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268717"
---
# <a name="receivelocationtransporttype-receivelocation-node"></a><span data-ttu-id="f4286-102">ReceiveLocationTransportType（“接收位置”节点）</span><span class="sxs-lookup"><span data-stu-id="f4286-102">ReceiveLocationTransportType (ReceiveLocation Node)</span></span>
<span data-ttu-id="f4286-103">绑定文件的“接收位置”节点的“接收位置传输类型”节点包含有关适配器的特定信息，该适配器与随同该绑定文件一起导出的传输相关联。</span><span class="sxs-lookup"><span data-stu-id="f4286-103">The ReceiveLocationTransportType node of the ReceiveLocation node of a binding file contains specific information about the adapter associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-receivelocationtransporttype-node"></a><span data-ttu-id="f4286-104">“接收位置传输类型”节点中的节点</span><span class="sxs-lookup"><span data-stu-id="f4286-104">Nodes in the ReceiveLocationTransportType node</span></span>  
 <span data-ttu-id="f4286-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="f4286-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="f4286-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="f4286-106">**Name**</span></span>|<span data-ttu-id="f4286-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="f4286-107">**Node Type**</span></span>|<span data-ttu-id="f4286-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f4286-108">**Data Type**</span></span>|<span data-ttu-id="f4286-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="f4286-109">**Description**</span></span>|<span data-ttu-id="f4286-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="f4286-110">**Restrictions**</span></span>|<span data-ttu-id="f4286-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="f4286-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="f4286-112">Name</span><span class="sxs-lookup"><span data-stu-id="f4286-112">Name</span></span>|<span data-ttu-id="f4286-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="f4286-113">Attribute</span></span>|<span data-ttu-id="f4286-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4286-114">xs:string</span></span>|<span data-ttu-id="f4286-115">指定与此传输关联的适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="f4286-115">Specifies the name of the adapter associated with the transport.</span></span>|<span data-ttu-id="f4286-116">可选</span><span class="sxs-lookup"><span data-stu-id="f4286-116">Not required</span></span>|<span data-ttu-id="f4286-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="f4286-117">Default value: empty</span></span>|  
|<span data-ttu-id="f4286-118">功能</span><span class="sxs-lookup"><span data-stu-id="f4286-118">Capabilities</span></span>|<span data-ttu-id="f4286-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="f4286-119">Attribute</span></span>|<span data-ttu-id="f4286-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="f4286-120">xs:int</span></span>|<span data-ttu-id="f4286-121">指定与此传输关联的适配器的功能。</span><span class="sxs-lookup"><span data-stu-id="f4286-121">Specifies the capabilities of the adapter associated with the transport.</span></span>|<span data-ttu-id="f4286-122">Required</span><span class="sxs-lookup"><span data-stu-id="f4286-122">Required</span></span>|<span data-ttu-id="f4286-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="f4286-123">Default value: none</span></span><br /><br /> <span data-ttu-id="f4286-124">可能的值包括 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 枚举中的值。</span><span class="sxs-lookup"><span data-stu-id="f4286-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="f4286-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="f4286-125">ConfigurationClsid</span></span>|<span data-ttu-id="f4286-126">Attribute</span><span class="sxs-lookup"><span data-stu-id="f4286-126">Attribute</span></span>|<span data-ttu-id="f4286-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4286-127">xs:string</span></span>|<span data-ttu-id="f4286-128">指定与此传输关联的适配器的配置 GUID。</span><span class="sxs-lookup"><span data-stu-id="f4286-128">Specifies the configuration GUID of the adapter associated with the transport.</span></span>|<span data-ttu-id="f4286-129">可选</span><span class="sxs-lookup"><span data-stu-id="f4286-129">Not required</span></span>|<span data-ttu-id="f4286-130">默认值：空</span><span class="sxs-lookup"><span data-stu-id="f4286-130">Default value: empty</span></span>|