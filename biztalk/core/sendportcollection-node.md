---
title: SendPortCollection 节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPortCollection node [binding file]
ms.assetid: 2084507e-ef70-4828-a15f-51d676b14333
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdb7f4e2074f8d9e9eaec013f578832405000e1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291851"
---
# <a name="sendportcollection-node"></a><span data-ttu-id="dd7a5-102">SendPortCollection 节点</span><span class="sxs-lookup"><span data-stu-id="dd7a5-102">SendPortCollection Node</span></span>
<span data-ttu-id="dd7a5-103">绑定文件的 SendPortCollection 节点是所有的发送端口节点包含有关与绑定文件一起导出的发送端口的特定信息的父节点。</span><span class="sxs-lookup"><span data-stu-id="dd7a5-103">The SendPortCollection node of a binding file is the parent node for all of the SendPort nodes which contain specific information about a send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-sendportcollection-node"></a><span data-ttu-id="dd7a5-104">SendPortCollection 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="dd7a5-104">Nodes in the SendPortCollection node</span></span>  
 <span data-ttu-id="dd7a5-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="dd7a5-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="dd7a5-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="dd7a5-106">**Name**</span></span>|<span data-ttu-id="dd7a5-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="dd7a5-107">**Node Type**</span></span>|<span data-ttu-id="dd7a5-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="dd7a5-108">**Data Type**</span></span>|<span data-ttu-id="dd7a5-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="dd7a5-109">**Description**</span></span>|<span data-ttu-id="dd7a5-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="dd7a5-110">**Restrictions**</span></span>|<span data-ttu-id="dd7a5-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="dd7a5-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="dd7a5-112">SendPort</span><span class="sxs-lookup"><span data-stu-id="dd7a5-112">SendPort</span></span>](../core/sendport-sendportcollection-node.md)|<span data-ttu-id="dd7a5-113">录制</span><span class="sxs-lookup"><span data-stu-id="dd7a5-113">Record</span></span>|<span data-ttu-id="dd7a5-114">发送端口 (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="dd7a5-114">SendPort (ComplexType)</span></span>|<span data-ttu-id="dd7a5-115">指定与绑定文件一起导出的发送端口有关的信息。</span><span class="sxs-lookup"><span data-stu-id="dd7a5-115">Specifies information about a send port that is exported with the binding file.</span></span>|<span data-ttu-id="dd7a5-116">可选</span><span class="sxs-lookup"><span data-stu-id="dd7a5-116">Not required</span></span>|<span data-ttu-id="dd7a5-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="dd7a5-117">Default value: none</span></span>|