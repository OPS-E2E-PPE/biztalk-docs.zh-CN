---
title: DistributionListRef （端口节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DistributionListRef node [binding file]
ms.assetid: 5d0d0121-1bcc-4c26-a1a3-8937ac7c282a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77bdfe705ac85be0e97492f84e39378b8da944bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351013"
---
# <a name="distributionlistref-port-node"></a><span data-ttu-id="182dc-102">DistributionListRef （端口节点）</span><span class="sxs-lookup"><span data-stu-id="182dc-102">DistributionListRef (Port Node)</span></span>
<span data-ttu-id="182dc-103">绑定文件的端口节点的 DistributionListRef 节点包含有关服务引用的通讯组列表的信息。</span><span class="sxs-lookup"><span data-stu-id="182dc-103">The DistributionListRef node of the Port node of a binding file contains information about a distribution list that is referenced by a service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="182dc-104">通讯组列表称为 BizTalk Server 管理控制台中的发送端口组。</span><span class="sxs-lookup"><span data-stu-id="182dc-104">Distribution lists are referred to as send port groups in the BizTalk Server Administration Console.</span></span>  
  
## <a name="nodes-in-the-distributionlistref-node"></a><span data-ttu-id="182dc-105">DistributionListRef 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="182dc-105">Nodes in the DistributionListRef node</span></span>  
 <span data-ttu-id="182dc-106">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="182dc-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="182dc-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="182dc-107">**Name**</span></span>|<span data-ttu-id="182dc-108">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="182dc-108">**Node Type**</span></span>|<span data-ttu-id="182dc-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="182dc-109">**Data Type**</span></span>|<span data-ttu-id="182dc-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="182dc-110">**Description**</span></span>|<span data-ttu-id="182dc-111">**限制**</span><span class="sxs-lookup"><span data-stu-id="182dc-111">**Restrictions**</span></span>|<span data-ttu-id="182dc-112">**注释**</span><span class="sxs-lookup"><span data-stu-id="182dc-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="182dc-113">“属性”</span><span class="sxs-lookup"><span data-stu-id="182dc-113">Name</span></span>|<span data-ttu-id="182dc-114">特性</span><span class="sxs-lookup"><span data-stu-id="182dc-114">Attribute</span></span>|<span data-ttu-id="182dc-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="182dc-115">xs:string</span></span>|<span data-ttu-id="182dc-116">指定服务引用的分发列表的名称。</span><span class="sxs-lookup"><span data-stu-id="182dc-116">Specifies the name of a distribution list that is referenced by a service.</span></span>|<span data-ttu-id="182dc-117">可选</span><span class="sxs-lookup"><span data-stu-id="182dc-117">Not required</span></span>|<span data-ttu-id="182dc-118">默认值：空</span><span class="sxs-lookup"><span data-stu-id="182dc-118">Default value: empty</span></span>|