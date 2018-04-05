---
title: OutboundTransforms （接收端口节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- OutboundTransforms node [binding file]
ms.assetid: 6deea062-4eb0-47ed-869c-ed6ec9290ea7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc6fa0bc804fad0d0ddea79614c392769452f1c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="outboundtransforms-receiveport-node"></a><span data-ttu-id="e8d16-102">OutboundTransforms （接收端口节点）</span><span class="sxs-lookup"><span data-stu-id="e8d16-102">OutboundTransforms (ReceivePort Node)</span></span>
<span data-ttu-id="e8d16-103">绑定文件的 ReceivePort 节点的 OutboundTransforms 节点包含与绑定文件一起导出的双向接收端口的出站转换集合。</span><span class="sxs-lookup"><span data-stu-id="e8d16-103">The OutboundTransforms node of the ReceivePort node of a binding file contains the collection of outbound transforms of a two-way receive port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-outboundtransforms-node"></a><span data-ttu-id="e8d16-104">OutboundTransforms 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="e8d16-104">Nodes in the OutboundTransforms node</span></span>  
 <span data-ttu-id="e8d16-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="e8d16-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="e8d16-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="e8d16-106">**Name**</span></span>|<span data-ttu-id="e8d16-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="e8d16-107">**Node Type**</span></span>|<span data-ttu-id="e8d16-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e8d16-108">**Data Type**</span></span>|<span data-ttu-id="e8d16-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="e8d16-109">**Description**</span></span>|<span data-ttu-id="e8d16-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="e8d16-110">**Restrictions**</span></span>|<span data-ttu-id="e8d16-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="e8d16-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="e8d16-112">转换 （OutboundTransforms 节点）</span><span class="sxs-lookup"><span data-stu-id="e8d16-112">Transform (OutboundTransforms Node)</span></span>](../core/transform-outboundtransforms-node.md)|<span data-ttu-id="e8d16-113">录制</span><span class="sxs-lookup"><span data-stu-id="e8d16-113">Record</span></span>|<span data-ttu-id="e8d16-114">转换 (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="e8d16-114">Transform (ComplexType)</span></span>|<span data-ttu-id="e8d16-115">指定 BizTalk Server 映射或转换，这是一个表示源架构和目标架构之间的映射项。</span><span class="sxs-lookup"><span data-stu-id="e8d16-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="e8d16-116">可选</span><span class="sxs-lookup"><span data-stu-id="e8d16-116">Not required</span></span>|<span data-ttu-id="e8d16-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="e8d16-117">Default value: none</span></span>|