---
title: 端口 （服务节点） |Microsoft Docs
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
ms.openlocfilehash: e8c7c160529b23a66d2c7cb444908adbaff13184
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394814"
---
# <a name="ports-service-node"></a><span data-ttu-id="78065-102">端口 （服务节点）</span><span class="sxs-lookup"><span data-stu-id="78065-102">Ports (Service Node)</span></span>
<span data-ttu-id="78065-103">绑定文件的端口节点是所有端口节点包含有关绑定到与绑定文件一起导出的服务的端口的特定信息的父节点。</span><span class="sxs-lookup"><span data-stu-id="78065-103">The Ports node of a binding file is the parent node for all of the Port nodes which contain specific information about ports bound to a service that is exported with the binding file.</span></span>  
  
## <a name="node-in-the-ports-node"></a><span data-ttu-id="78065-104">在端口节点中的节点</span><span class="sxs-lookup"><span data-stu-id="78065-104">Node in the Ports node</span></span>  
 <span data-ttu-id="78065-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="78065-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="78065-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="78065-106">**Name**</span></span>|<span data-ttu-id="78065-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="78065-107">**Node Type**</span></span>|<span data-ttu-id="78065-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="78065-108">**Data Type**</span></span>|<span data-ttu-id="78065-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="78065-109">**Description**</span></span>|<span data-ttu-id="78065-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="78065-110">**Restrictions**</span></span>|<span data-ttu-id="78065-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="78065-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="78065-112">端口</span><span class="sxs-lookup"><span data-stu-id="78065-112">Port</span></span>](../core/port-ports-node.md)|<span data-ttu-id="78065-113">录制</span><span class="sxs-lookup"><span data-stu-id="78065-113">Record</span></span>|<span data-ttu-id="78065-114">ServicePortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="78065-114">ServicePortRef (ComplexType)</span></span>|<span data-ttu-id="78065-115">指定有关绑定到与绑定文件一起导出的服务的端口信息。</span><span class="sxs-lookup"><span data-stu-id="78065-115">Specifies information about a port that is bound to a service that is exported with the binding file.</span></span>|<span data-ttu-id="78065-116">可选</span><span class="sxs-lookup"><span data-stu-id="78065-116">Not required</span></span>|<span data-ttu-id="78065-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="78065-117">Default value: none</span></span>|