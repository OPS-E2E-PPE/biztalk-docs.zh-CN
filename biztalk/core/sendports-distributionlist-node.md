---
title: "发送端口 （DistributionList 节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SendPorts node [binding file]
ms.assetid: 9cb645fa-cb9c-44eb-9f98-2fc507b2be67
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9eaf692bd61913e604731fc2e2cea373fd31f48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sendports-distributionlist-node"></a><span data-ttu-id="c00e8-102">发送端口 （DistributionList 节点）</span><span class="sxs-lookup"><span data-stu-id="c00e8-102">SendPorts (DistributionList Node)</span></span>
<span data-ttu-id="c00e8-103">绑定文件 DistributionList 节点发送端口节点是通讯组列表中的发送端口引用的容器节点。</span><span class="sxs-lookup"><span data-stu-id="c00e8-103">The SendPorts node of the DistributionList node of a binding file is the container node for the send port references in the distribution list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c00e8-104">分发列表指 BizTalk 管理员中的发送端口组。</span><span class="sxs-lookup"><span data-stu-id="c00e8-104">A distribution list is referred to as a send port group in the BizTalk Administrator.</span></span>  
  
## <a name="nodes-in-the-sendports-node"></a><span data-ttu-id="c00e8-105">发送端口节点中的节点</span><span class="sxs-lookup"><span data-stu-id="c00e8-105">Nodes in the SendPorts node</span></span>  
 <span data-ttu-id="c00e8-106">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="c00e8-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="c00e8-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="c00e8-107">**Name**</span></span>|<span data-ttu-id="c00e8-108">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="c00e8-108">**Node Type**</span></span>|<span data-ttu-id="c00e8-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c00e8-109">**Data Type**</span></span>|<span data-ttu-id="c00e8-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="c00e8-110">**Description**</span></span>|<span data-ttu-id="c00e8-111">**限制**</span><span class="sxs-lookup"><span data-stu-id="c00e8-111">**Restrictions**</span></span>|<span data-ttu-id="c00e8-112">**注释**</span><span class="sxs-lookup"><span data-stu-id="c00e8-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="c00e8-113">SendPortRef</span><span class="sxs-lookup"><span data-stu-id="c00e8-113">SendPortRef</span></span>](../core/sendportref-sendports-node.md)|<span data-ttu-id="c00e8-114">录制</span><span class="sxs-lookup"><span data-stu-id="c00e8-114">Record</span></span>|<span data-ttu-id="c00e8-115">SendPortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="c00e8-115">SendPortRef (ComplexType)</span></span>|<span data-ttu-id="c00e8-116">容器的引用所做的通讯组列表发送端口的节点。</span><span class="sxs-lookup"><span data-stu-id="c00e8-116">Container node for a reference to a send port made by the distribution list.</span></span>|<span data-ttu-id="c00e8-117">可选</span><span class="sxs-lookup"><span data-stu-id="c00e8-117">Not required</span></span>|<span data-ttu-id="c00e8-118">默认值：无</span><span class="sxs-lookup"><span data-stu-id="c00e8-118">Default value: none</span></span>|