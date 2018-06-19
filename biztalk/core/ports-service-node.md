---
title: 端口 （服务节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Ports node [binding file]
ms.assetid: 498d4310-4e9e-4e74-bc3d-5cbf1319c4ff
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31e09470b9f3287cce5ce15c2941d2165157ec48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263453"
---
# <a name="ports-service-node"></a><span data-ttu-id="e6700-102">端口 （服务节点）</span><span class="sxs-lookup"><span data-stu-id="e6700-102">Ports (Service Node)</span></span>
<span data-ttu-id="e6700-103">绑定文件的“Ports”节点是所有端口节点的父节点，端口节点包含与各个端口（这些端口绑定到与绑定文件一起导出的服务）有关的特定信息。</span><span class="sxs-lookup"><span data-stu-id="e6700-103">The Ports node of a binding file is the parent node for all of the Port nodes which contain specific information about ports bound to a service that is exported with the binding file.</span></span>  
  
## <a name="node-in-the-ports-node"></a><span data-ttu-id="e6700-104">“Ports”节点中的节点</span><span class="sxs-lookup"><span data-stu-id="e6700-104">Node in the Ports node</span></span>  
 <span data-ttu-id="e6700-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="e6700-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="e6700-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="e6700-106">**Name**</span></span>|<span data-ttu-id="e6700-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="e6700-107">**Node Type**</span></span>|<span data-ttu-id="e6700-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e6700-108">**Data Type**</span></span>|<span data-ttu-id="e6700-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="e6700-109">**Description**</span></span>|<span data-ttu-id="e6700-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="e6700-110">**Restrictions**</span></span>|<span data-ttu-id="e6700-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="e6700-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="e6700-112">端口</span><span class="sxs-lookup"><span data-stu-id="e6700-112">Port</span></span>](../core/port-ports-node.md)|<span data-ttu-id="e6700-113">录制</span><span class="sxs-lookup"><span data-stu-id="e6700-113">Record</span></span>|<span data-ttu-id="e6700-114">ServicePortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="e6700-114">ServicePortRef (ComplexType)</span></span>|<span data-ttu-id="e6700-115">指定绑定到与绑定文件一起导出的服务的端口有关的信息。</span><span class="sxs-lookup"><span data-stu-id="e6700-115">Specifies information about a port that is bound to a service that is exported with the binding file.</span></span>|<span data-ttu-id="e6700-116">可选</span><span class="sxs-lookup"><span data-stu-id="e6700-116">Not required</span></span>|<span data-ttu-id="e6700-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="e6700-117">Default value: none</span></span>|