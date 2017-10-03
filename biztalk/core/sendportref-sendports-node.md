---
title: "SendPortRef （发送端口节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SendPortRef node [binding file]
ms.assetid: 6c799b23-a9a4-4686-a04e-0450b4eef889
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9290a535ebcaf0c23097cacbd3412f64c2808f40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sendportref-sendports-node"></a><span data-ttu-id="f218c-102">SendPortRef（“发送端口”节点）</span><span class="sxs-lookup"><span data-stu-id="f218c-102">SendPortRef (SendPorts Node)</span></span>
<span data-ttu-id="f218c-103">绑定文件的 SendPorts 节点的 SendPortRef 节点可指定分发列表所引用的发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="f218c-103">The SendPortRef node of the SendPorts node of a binding file specifies the name of a send port referenced by a distribution list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f218c-104">分发列表指 BizTalk 管理员中的发送端口组。</span><span class="sxs-lookup"><span data-stu-id="f218c-104">A distribution list is referred to as a send port group in the BizTalk Administrator.</span></span>  
  
## <a name="nodes-in-the-sendportref-node"></a><span data-ttu-id="f218c-105">SendPortRef 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="f218c-105">Nodes in the SendPortRef node</span></span>  
 <span data-ttu-id="f218c-106">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="f218c-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="f218c-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="f218c-107">**Name**</span></span>|<span data-ttu-id="f218c-108">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="f218c-108">**Node Type**</span></span>|<span data-ttu-id="f218c-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f218c-109">**Data Type**</span></span>|<span data-ttu-id="f218c-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="f218c-110">**Description**</span></span>|<span data-ttu-id="f218c-111">**限制**</span><span class="sxs-lookup"><span data-stu-id="f218c-111">**Restrictions**</span></span>|<span data-ttu-id="f218c-112">**注释**</span><span class="sxs-lookup"><span data-stu-id="f218c-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="f218c-113">Name</span><span class="sxs-lookup"><span data-stu-id="f218c-113">Name</span></span>|<span data-ttu-id="f218c-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="f218c-114">Attribute</span></span>|<span data-ttu-id="f218c-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="f218c-115">xs:string</span></span>|<span data-ttu-id="f218c-116">指定分发列表引用的发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="f218c-116">Specifies the name of the send port referenced by the distribution list.</span></span>|<span data-ttu-id="f218c-117">可选</span><span class="sxs-lookup"><span data-stu-id="f218c-117">Not required</span></span>|<span data-ttu-id="f218c-118">默认值：空</span><span class="sxs-lookup"><span data-stu-id="f218c-118">Default value: empty</span></span>|