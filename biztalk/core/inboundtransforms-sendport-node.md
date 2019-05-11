---
title: InboundTransforms （SendPort 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- InboundTransforms node [binding file]
ms.assetid: 5ed239b9-13d8-4099-b779-08f589a722e9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59d13d48da9f4b9e3e04cb0753eb302484b6b169
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382187"
---
# <a name="inboundtransforms-sendport-node"></a><span data-ttu-id="87a66-102">InboundTransforms （SendPort 节点）</span><span class="sxs-lookup"><span data-stu-id="87a66-102">InboundTransforms (SendPort Node)</span></span>
<span data-ttu-id="87a66-103">绑定文件的发送端口节点的 InboundTransforms 节点包含随绑定文件一起导出的双向发送端口的入站转换的集合。</span><span class="sxs-lookup"><span data-stu-id="87a66-103">The InboundTransforms node of the SendPort node of a binding file contains the collection of inbound transforms of a two-way send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-inboundtransforms-node"></a><span data-ttu-id="87a66-104">节点中的 InboundTransforms 节点</span><span class="sxs-lookup"><span data-stu-id="87a66-104">Nodes in the InboundTransforms node</span></span>  
 <span data-ttu-id="87a66-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="87a66-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="87a66-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="87a66-106">**Name**</span></span>|<span data-ttu-id="87a66-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="87a66-107">**Node Type**</span></span>|<span data-ttu-id="87a66-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="87a66-108">**Data Type**</span></span>|<span data-ttu-id="87a66-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="87a66-109">**Description**</span></span>|<span data-ttu-id="87a66-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="87a66-110">**Restrictions**</span></span>|<span data-ttu-id="87a66-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="87a66-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="87a66-112">Transform（“InboundTransforms”节点）</span><span class="sxs-lookup"><span data-stu-id="87a66-112">Transform (InboundTransforms Node)</span></span>](../core/transform-inboundtransforms-node.md)|<span data-ttu-id="87a66-113">录制</span><span class="sxs-lookup"><span data-stu-id="87a66-113">Record</span></span>|<span data-ttu-id="87a66-114">转换 (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="87a66-114">Transform (ComplexType)</span></span>|<span data-ttu-id="87a66-115">指定 BizTalk Server 映射或转换，这是一个表示源架构和目标架构之间的映射项。</span><span class="sxs-lookup"><span data-stu-id="87a66-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="87a66-116">可选</span><span class="sxs-lookup"><span data-stu-id="87a66-116">Not required</span></span>|<span data-ttu-id="87a66-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="87a66-117">Default value: none</span></span>|