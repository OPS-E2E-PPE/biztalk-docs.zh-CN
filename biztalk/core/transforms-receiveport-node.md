---
title: "转换 （接收端口节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Transforms node [binding file]
ms.assetid: cd32f2fe-b70a-4153-86ec-bb1aa9bad0e4
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7d039d95a1f28afa468078ff7547e9f298633bb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transforms-receiveport-node"></a><span data-ttu-id="a5f94-102">Transforms（ReceivePort 节点）</span><span class="sxs-lookup"><span data-stu-id="a5f94-102">Transforms (ReceivePort Node)</span></span>
<span data-ttu-id="a5f94-103">绑定文件的 ReceivePort 节点的 Transforms 节点包含与绑定文件一起导出的单向接收端口的入站转换集合。</span><span class="sxs-lookup"><span data-stu-id="a5f94-103">The Transforms node of the ReceivePort node of a binding file contains the collection of inbound transforms of a one way receive port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transforms-node"></a><span data-ttu-id="a5f94-104">Transforms 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="a5f94-104">Nodes in the Transforms node</span></span>  
 <span data-ttu-id="a5f94-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="a5f94-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="a5f94-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="a5f94-106">**Name**</span></span>|<span data-ttu-id="a5f94-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="a5f94-107">**Node Type**</span></span>|<span data-ttu-id="a5f94-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5f94-108">**Data Type**</span></span>|<span data-ttu-id="a5f94-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="a5f94-109">**Description**</span></span>|<span data-ttu-id="a5f94-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="a5f94-110">**Restrictions**</span></span>|<span data-ttu-id="a5f94-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="a5f94-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="a5f94-112">转换 （转换节点）</span><span class="sxs-lookup"><span data-stu-id="a5f94-112">Transform (Transforms Node)</span></span>](../core/transform-transforms-node.md)|<span data-ttu-id="a5f94-113">录制</span><span class="sxs-lookup"><span data-stu-id="a5f94-113">Record</span></span>|<span data-ttu-id="a5f94-114">转换 (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="a5f94-114">Transform (ComplexType)</span></span>|<span data-ttu-id="a5f94-115">指定 BizTalk Server 映射或转换，这是一个表示源架构和目标架构之间的映射项。</span><span class="sxs-lookup"><span data-stu-id="a5f94-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="a5f94-116">可选</span><span class="sxs-lookup"><span data-stu-id="a5f94-116">Not required</span></span>|<span data-ttu-id="a5f94-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="a5f94-117">Default value: none</span></span>|