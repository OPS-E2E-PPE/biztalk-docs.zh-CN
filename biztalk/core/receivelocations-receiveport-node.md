---
title: "接收位置 （接收端口节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ReceiveLocations node [binding file]
ms.assetid: c12acc1b-f8fe-4a27-8386-d9f4f4455e3f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c9fb5b64466e32ae27d53852b3383eb79531d60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receivelocations-receiveport-node"></a><span data-ttu-id="b8b5d-102">ReceiveLocations（ReceivePort 节点）</span><span class="sxs-lookup"><span data-stu-id="b8b5d-102">ReceiveLocations (ReceivePort Node)</span></span>
<span data-ttu-id="b8b5d-103">绑定文件的 ReceivePort 节点的 ReceiveLocations 节点是所有 ReceiveLocation 节点的父节点，ReceiveLocation 节点包含有关与此绑定文件一起导出的接收位置的特定信息。</span><span class="sxs-lookup"><span data-stu-id="b8b5d-103">The ReceiveLocations node of the ReceivePort node of a binding file is the parent node for all of the ReceiveLocation nodes which contain specific information about the receive locations that are exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-receivelocations-node"></a><span data-ttu-id="b8b5d-104">ReceiveLocations 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="b8b5d-104">Nodes in the ReceiveLocations node</span></span>  
 <span data-ttu-id="b8b5d-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="b8b5d-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="b8b5d-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="b8b5d-106">**Name**</span></span>|<span data-ttu-id="b8b5d-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="b8b5d-107">**Node Type**</span></span>|<span data-ttu-id="b8b5d-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b8b5d-108">**Data Type**</span></span>|<span data-ttu-id="b8b5d-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="b8b5d-109">**Description**</span></span>|<span data-ttu-id="b8b5d-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="b8b5d-110">**Restrictions**</span></span>|<span data-ttu-id="b8b5d-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="b8b5d-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="b8b5d-112">接收位置</span><span class="sxs-lookup"><span data-stu-id="b8b5d-112">ReceiveLocation</span></span>](../core/receivelocation-receivelocations-node.md)|<span data-ttu-id="b8b5d-113">录制</span><span class="sxs-lookup"><span data-stu-id="b8b5d-113">Record</span></span>|<span data-ttu-id="b8b5d-114">ReceiveLocation (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="b8b5d-114">ReceiveLocation (ComplexType)</span></span>|<span data-ttu-id="b8b5d-115">指定与绑定文件一起导出的接收位置有关的信息。</span><span class="sxs-lookup"><span data-stu-id="b8b5d-115">Specifies information about a receive location that is exported with the binding file.</span></span>|<span data-ttu-id="b8b5d-116">可选</span><span class="sxs-lookup"><span data-stu-id="b8b5d-116">Not required</span></span>|<span data-ttu-id="b8b5d-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="b8b5d-117">Default value: none</span></span>|