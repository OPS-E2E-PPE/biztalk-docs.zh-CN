---
title: OutboundTransforms （ReceivePort 节点） |Microsoft Docs
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
ms.openlocfilehash: 109995aa38731338ce53d4dea58226fa081fd17a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393424"
---
# <a name="outboundtransforms-receiveport-node"></a><span data-ttu-id="7a5fa-102">OutboundTransforms （ReceivePort 节点）</span><span class="sxs-lookup"><span data-stu-id="7a5fa-102">OutboundTransforms (ReceivePort Node)</span></span>
<span data-ttu-id="7a5fa-103">绑定文件的 ReceivePort 节点的 OutboundTransforms 节点包含集合的出站转换的双向接收端口的绑定文件一起导出。</span><span class="sxs-lookup"><span data-stu-id="7a5fa-103">The OutboundTransforms node of the ReceivePort node of a binding file contains the collection of outbound transforms of a two-way receive port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-outboundtransforms-node"></a><span data-ttu-id="7a5fa-104">节点中的 OutboundTransforms 节点</span><span class="sxs-lookup"><span data-stu-id="7a5fa-104">Nodes in the OutboundTransforms node</span></span>  
 <span data-ttu-id="7a5fa-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="7a5fa-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="7a5fa-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="7a5fa-106">**Name**</span></span>|<span data-ttu-id="7a5fa-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="7a5fa-107">**Node Type**</span></span>|<span data-ttu-id="7a5fa-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7a5fa-108">**Data Type**</span></span>|<span data-ttu-id="7a5fa-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="7a5fa-109">**Description**</span></span>|<span data-ttu-id="7a5fa-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="7a5fa-110">**Restrictions**</span></span>|<span data-ttu-id="7a5fa-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="7a5fa-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="7a5fa-112">Transform（“OutboundTransforms”节点）</span><span class="sxs-lookup"><span data-stu-id="7a5fa-112">Transform (OutboundTransforms Node)</span></span>](../core/transform-outboundtransforms-node.md)|<span data-ttu-id="7a5fa-113">录制</span><span class="sxs-lookup"><span data-stu-id="7a5fa-113">Record</span></span>|<span data-ttu-id="7a5fa-114">转换 (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="7a5fa-114">Transform (ComplexType)</span></span>|<span data-ttu-id="7a5fa-115">指定 BizTalk Server 映射或转换，这是一个表示源架构和目标架构之间的映射项。</span><span class="sxs-lookup"><span data-stu-id="7a5fa-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="7a5fa-116">可选</span><span class="sxs-lookup"><span data-stu-id="7a5fa-116">Not required</span></span>|<span data-ttu-id="7a5fa-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="7a5fa-117">Default value: none</span></span>|