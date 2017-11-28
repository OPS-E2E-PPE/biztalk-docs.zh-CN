---
title: "InboundTransforms （发送端口节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: InboundTransforms node [binding file]
ms.assetid: 5ed239b9-13d8-4099-b779-08f589a722e9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03567b5ea6095e38370260e1f17055ab40da4d6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="inboundtransforms-sendport-node"></a><span data-ttu-id="cbe34-102">InboundTransforms（“发送端口”节点）</span><span class="sxs-lookup"><span data-stu-id="cbe34-102">InboundTransforms (SendPort Node)</span></span>
<span data-ttu-id="cbe34-103">绑定文件的发送端口节点的 InboundTransforms 节点包含的与绑定文件导出双向发送端口的入站转换的集合。</span><span class="sxs-lookup"><span data-stu-id="cbe34-103">The InboundTransforms node of the SendPort node of a binding file contains the collection of inbound transforms of a two-way send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-inboundtransforms-node"></a><span data-ttu-id="cbe34-104">InboundTransforms 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="cbe34-104">Nodes in the InboundTransforms node</span></span>  
 <span data-ttu-id="cbe34-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="cbe34-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="cbe34-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="cbe34-106">**Name**</span></span>|<span data-ttu-id="cbe34-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="cbe34-107">**Node Type**</span></span>|<span data-ttu-id="cbe34-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cbe34-108">**Data Type**</span></span>|<span data-ttu-id="cbe34-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="cbe34-109">**Description**</span></span>|<span data-ttu-id="cbe34-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="cbe34-110">**Restrictions**</span></span>|<span data-ttu-id="cbe34-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="cbe34-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="cbe34-112">转换 （InboundTransforms 节点）</span><span class="sxs-lookup"><span data-stu-id="cbe34-112">Transform (InboundTransforms Node)</span></span>](../core/transform-inboundtransforms-node.md)|<span data-ttu-id="cbe34-113">录制</span><span class="sxs-lookup"><span data-stu-id="cbe34-113">Record</span></span>|<span data-ttu-id="cbe34-114">转换 (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="cbe34-114">Transform (ComplexType)</span></span>|<span data-ttu-id="cbe34-115">指定 BizTalk Server 映射或转换，这是一个表示源架构和目标架构之间的映射项。</span><span class="sxs-lookup"><span data-stu-id="cbe34-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="cbe34-116">可选</span><span class="sxs-lookup"><span data-stu-id="cbe34-116">Not required</span></span>|<span data-ttu-id="cbe34-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="cbe34-117">Default value: none</span></span>|