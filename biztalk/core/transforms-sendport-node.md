---
title: Transforms （SendPort 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transforms node [binding file]
ms.assetid: b405397b-e394-44fa-b507-93896f800f66
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcae41bd04d094238778d16768316eb55fb2e5d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243176"
---
# <a name="transforms-sendport-node"></a><span data-ttu-id="4dca4-102">Transforms （SendPort 节点）</span><span class="sxs-lookup"><span data-stu-id="4dca4-102">Transforms (SendPort Node)</span></span>
<span data-ttu-id="4dca4-103">绑定文件的发送端口节点的 Transforms 节点包含随绑定文件一起导出的单向发送端口的出站转换的集合。</span><span class="sxs-lookup"><span data-stu-id="4dca4-103">The Transforms node of the SendPort node of a binding file contains the collection of outbound transforms of a one way send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transforms-node"></a><span data-ttu-id="4dca4-104">Transforms 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="4dca4-104">Nodes in the Transforms node</span></span>  
 <span data-ttu-id="4dca4-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="4dca4-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="4dca4-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="4dca4-106">**Name**</span></span>|<span data-ttu-id="4dca4-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="4dca4-107">**Node Type**</span></span>|<span data-ttu-id="4dca4-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4dca4-108">**Data Type**</span></span>|<span data-ttu-id="4dca4-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="4dca4-109">**Description**</span></span>|<span data-ttu-id="4dca4-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="4dca4-110">**Restrictions**</span></span>|<span data-ttu-id="4dca4-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="4dca4-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="4dca4-112">Transform（“SendPort-Transforms”节点）</span><span class="sxs-lookup"><span data-stu-id="4dca4-112">Transform (SendPort-Transforms Node)</span></span>](../core/transform-sendport-transforms-node.md)|<span data-ttu-id="4dca4-113">录制</span><span class="sxs-lookup"><span data-stu-id="4dca4-113">Record</span></span>|<span data-ttu-id="4dca4-114">转换 (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="4dca4-114">Transform (ComplexType)</span></span>|<span data-ttu-id="4dca4-115">指定 BizTalk Server 映射或转换，这是一个表示源架构和目标架构之间的映射项。</span><span class="sxs-lookup"><span data-stu-id="4dca4-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="4dca4-116">可选</span><span class="sxs-lookup"><span data-stu-id="4dca4-116">Not required</span></span>|<span data-ttu-id="4dca4-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="4dca4-117">Default value: none</span></span>|