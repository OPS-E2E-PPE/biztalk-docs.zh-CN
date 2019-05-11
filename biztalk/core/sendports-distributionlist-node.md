---
title: 发送端口 （DistributionList 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPorts node [binding file]
ms.assetid: 9cb645fa-cb9c-44eb-9f98-2fc507b2be67
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63fda2724291b15492ecb4d9a035d33cddc0b5d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393352"
---
# <a name="sendports-distributionlist-node"></a><span data-ttu-id="66a0a-102">发送端口 （DistributionList 节点）</span><span class="sxs-lookup"><span data-stu-id="66a0a-102">SendPorts (DistributionList Node)</span></span>
<span data-ttu-id="66a0a-103">绑定文件的 DistributionList 节点的发送端口节点是通讯组列表中的发送端口引用的容器节点。</span><span class="sxs-lookup"><span data-stu-id="66a0a-103">The SendPorts node of the DistributionList node of a binding file is the container node for the send port references in the distribution list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66a0a-104">通讯组列表称为发送端口组在 BizTalk 管理器。</span><span class="sxs-lookup"><span data-stu-id="66a0a-104">A distribution list is referred to as a send port group in the BizTalk Administrator.</span></span>  
  
## <a name="nodes-in-the-sendports-node"></a><span data-ttu-id="66a0a-105">节点中的发送端口节点</span><span class="sxs-lookup"><span data-stu-id="66a0a-105">Nodes in the SendPorts node</span></span>  
 <span data-ttu-id="66a0a-106">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="66a0a-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="66a0a-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="66a0a-107">**Name**</span></span>|<span data-ttu-id="66a0a-108">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="66a0a-108">**Node Type**</span></span>|<span data-ttu-id="66a0a-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="66a0a-109">**Data Type**</span></span>|<span data-ttu-id="66a0a-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="66a0a-110">**Description**</span></span>|<span data-ttu-id="66a0a-111">**限制**</span><span class="sxs-lookup"><span data-stu-id="66a0a-111">**Restrictions**</span></span>|<span data-ttu-id="66a0a-112">**注释**</span><span class="sxs-lookup"><span data-stu-id="66a0a-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="66a0a-113">SendPortRef</span><span class="sxs-lookup"><span data-stu-id="66a0a-113">SendPortRef</span></span>](../core/sendportref-sendports-node.md)|<span data-ttu-id="66a0a-114">录制</span><span class="sxs-lookup"><span data-stu-id="66a0a-114">Record</span></span>|<span data-ttu-id="66a0a-115">SendPortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="66a0a-115">SendPortRef (ComplexType)</span></span>|<span data-ttu-id="66a0a-116">对所做的通讯组列表的发送端口的引用的容器节点。</span><span class="sxs-lookup"><span data-stu-id="66a0a-116">Container node for a reference to a send port made by the distribution list.</span></span>|<span data-ttu-id="66a0a-117">可选</span><span class="sxs-lookup"><span data-stu-id="66a0a-117">Not required</span></span>|<span data-ttu-id="66a0a-118">默认值：无</span><span class="sxs-lookup"><span data-stu-id="66a0a-118">Default value: none</span></span>|