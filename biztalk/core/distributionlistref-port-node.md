---
title: "DistributionListRef （端口节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: DistributionListRef node [binding file]
ms.assetid: 5d0d0121-1bcc-4c26-a1a3-8937ac7c282a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 665b8c2115c5c4681f7cff057481b6ce7da320ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="distributionlistref-port-node"></a><span data-ttu-id="8fd17-102">DistributionListRef （端口节点）</span><span class="sxs-lookup"><span data-stu-id="8fd17-102">DistributionListRef (Port Node)</span></span>
<span data-ttu-id="8fd17-103">绑定文件“端口”节点的 DistributionListRef 节点包含有关服务引用的分发列表的信息。</span><span class="sxs-lookup"><span data-stu-id="8fd17-103">The DistributionListRef node of the Port node of a binding file contains information about a distribution list that is referenced by a service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fd17-104">通讯组列表被指在 BizTalk Server 管理控制台中发送端口组。</span><span class="sxs-lookup"><span data-stu-id="8fd17-104">Distribution lists are referred to as send port groups in the BizTalk Server Administration Console.</span></span>  
  
## <a name="nodes-in-the-distributionlistref-node"></a><span data-ttu-id="8fd17-105">DistributionListRef 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="8fd17-105">Nodes in the DistributionListRef node</span></span>  
 <span data-ttu-id="8fd17-106">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="8fd17-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="8fd17-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="8fd17-107">**Name**</span></span>|<span data-ttu-id="8fd17-108">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="8fd17-108">**Node Type**</span></span>|<span data-ttu-id="8fd17-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8fd17-109">**Data Type**</span></span>|<span data-ttu-id="8fd17-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="8fd17-110">**Description**</span></span>|<span data-ttu-id="8fd17-111">**限制**</span><span class="sxs-lookup"><span data-stu-id="8fd17-111">**Restrictions**</span></span>|<span data-ttu-id="8fd17-112">**注释**</span><span class="sxs-lookup"><span data-stu-id="8fd17-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="8fd17-113">Name</span><span class="sxs-lookup"><span data-stu-id="8fd17-113">Name</span></span>|<span data-ttu-id="8fd17-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="8fd17-114">Attribute</span></span>|<span data-ttu-id="8fd17-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="8fd17-115">xs:string</span></span>|<span data-ttu-id="8fd17-116">指定服务引用的分发列表的名称。</span><span class="sxs-lookup"><span data-stu-id="8fd17-116">Specifies the name of a distribution list that is referenced by a service.</span></span>|<span data-ttu-id="8fd17-117">可选</span><span class="sxs-lookup"><span data-stu-id="8fd17-117">Not required</span></span>|<span data-ttu-id="8fd17-118">默认值：空</span><span class="sxs-lookup"><span data-stu-id="8fd17-118">Default value: empty</span></span>|