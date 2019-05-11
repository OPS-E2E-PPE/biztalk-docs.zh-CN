---
title: 使用链接指定记录和字段映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c669d93-e088-459e-8f45-87c359874a7e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b807bebaeb60a72287d0ef2694739c961ee29fd1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246441"
---
# <a name="using-links-to-specify-record-and-field-mappings"></a><span data-ttu-id="d04b2-102">使用链接指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="d04b2-102">Using Links to Specify Record and Field Mappings</span></span>
<span data-ttu-id="d04b2-103">在 BizTalk 映射器链接是在将源架构中的数据项与目标架构中的数据项关联的方法。</span><span class="sxs-lookup"><span data-stu-id="d04b2-103">In BizTalk Mapper, a link is the way you associate a data item in the source schema with a data item in the destination schema.</span></span> <span data-ttu-id="d04b2-104">通常情况下，已完成映射中有许多源架构和目标架构之间的链接。</span><span class="sxs-lookup"><span data-stu-id="d04b2-104">Typically, in a completed map there are many links between the source schema and the destination schema.</span></span> <span data-ttu-id="d04b2-105">所有内容的链接指定的源实例消息中的数据将如何转换为语义相同、 但语法不同，目标实例消息。</span><span class="sxs-lookup"><span data-stu-id="d04b2-105">All together the links specify how the data in the source instance messages will be transformed into a semantically equivalent, but syntactically distinct, destination instance messages.</span></span>  
  
 <span data-ttu-id="d04b2-106">本部分提供有关创建新的链接，使用现有链接，自动创建链接以及其他链接操作的特定于任务的信息。</span><span class="sxs-lookup"><span data-stu-id="d04b2-106">This section provides task-specific information about creating new links, working with existing links, creating links automatically, and other linking operations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d04b2-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="d04b2-107">In This Section</span></span>  
  
-   [<span data-ttu-id="d04b2-108">如何创建链接</span><span class="sxs-lookup"><span data-stu-id="d04b2-108">How to Create Links</span></span>](../core/how-to-create-links.md)  
  
-   [<span data-ttu-id="d04b2-109">如何编辑链接属性</span><span class="sxs-lookup"><span data-stu-id="d04b2-109">How to Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)  
  
-   [<span data-ttu-id="d04b2-110">如何自动链接记录</span><span class="sxs-lookup"><span data-stu-id="d04b2-110">How to Link Records Automatically</span></span>](../core/how-to-link-records-automatically.md)  
  
-   [<span data-ttu-id="d04b2-111">如何管理现有链接</span><span class="sxs-lookup"><span data-stu-id="d04b2-111">How to Manage Existing Links</span></span>](../core/how-to-manage-existing-links.md)  
  
-   [<span data-ttu-id="d04b2-112">如何配置节点层次级别匹配</span><span class="sxs-lookup"><span data-stu-id="d04b2-112">How to Configure Node Hierarchy Matching</span></span>](../core/how-to-configure-node-hierarchy-matching.md)  
  
-   [<span data-ttu-id="d04b2-113">如何设置源链接编译器值</span><span class="sxs-lookup"><span data-stu-id="d04b2-113">How to Set the Source Links Compiler Value</span></span>](../core/how-to-set-the-source-links-compiler-value.md)  
  
-   [<span data-ttu-id="d04b2-114">如何显示和隐藏编译器链接</span><span class="sxs-lookup"><span data-stu-id="d04b2-114">How to Show and Hide Compiler Links</span></span>](../core/how-to-show-and-hide-compiler-links.md)  
  
-   [<span data-ttu-id="d04b2-115">如何复制、 剪切和粘贴链接和 Functoid</span><span class="sxs-lookup"><span data-stu-id="d04b2-115">How to Copy, Cut, and Paste Links and Functoids</span></span>](../core/how-to-copy-cut-and-paste-links-and-functoids.md)  
  
-   [<span data-ttu-id="d04b2-116">如何标记链接</span><span class="sxs-lookup"><span data-stu-id="d04b2-116">How to Label a Link</span></span>](../core/how-to-label-a-link.md)  
  
-   [<span data-ttu-id="d04b2-117">如何选择多个链接和 Functoid</span><span class="sxs-lookup"><span data-stu-id="d04b2-117">How to Select Multiple Links and Functoids</span></span>](../core/how-to-select-multiple-links-and-functoids.md)  
  
-   [<span data-ttu-id="d04b2-118">如何在多个链接和 Functoid 上设置标签和注释</span><span class="sxs-lookup"><span data-stu-id="d04b2-118">How to Set Label and Comment on Multiple Links and Functoids</span></span>](../core/how-to-set-label-and-comment-on-multiple-links-and-functoids.md)