---
title: "开发自定义组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12b7d99d-ac3c-427d-b6b6-286233fde541
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b61144b2acaf787d56468c23c04835b5ad79324
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="developing-custom-components"></a><span data-ttu-id="4f6b7-102">开发自定义组件</span><span class="sxs-lookup"><span data-stu-id="4f6b7-102">Developing Custom Components</span></span>
<span data-ttu-id="4f6b7-103">BizTalk Server 中开发的自定义组件可用于修改或扩展 BizTalk Server 的某些基础结构元素。</span><span class="sxs-lookup"><span data-stu-id="4f6b7-103">Custom components in BizTalk Server are developed and used to modify or extend certain infrastructure elements of BizTalk Server.</span></span>  <span data-ttu-id="4f6b7-104">主要原因是，这包括之类的内容： 发送或接收适配器组件是在基于适配器 Framework 且用来处理特定的传输协议;管道组件在任何发送或接收管道阶段;和 functoid 在地图中使用。</span><span class="sxs-lookup"><span data-stu-id="4f6b7-104">Primarily, this includes such things as:  send or receive adapter components which are based on the Adapter Framework and used to handle specific transport protocols; pipeline components used in any of the send or receive pipeline stages; and functoids used in maps.</span></span>  <span data-ttu-id="4f6b7-105">你可以扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用多种方式自定义代码。</span><span class="sxs-lookup"><span data-stu-id="4f6b7-105">You can extend [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with custom code in several ways.</span></span> <span data-ttu-id="4f6b7-106">下面的主题介绍了具体方法。</span><span class="sxs-lookup"><span data-stu-id="4f6b7-106">The following topics describe how to do this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f6b7-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="4f6b7-107">In This Section</span></span>  
  
-   [<span data-ttu-id="4f6b7-108">开发自定义适配器</span><span class="sxs-lookup"><span data-stu-id="4f6b7-108">Developing Custom Adapters</span></span>](../core/developing-custom-adapters.md)  
  
-   [<span data-ttu-id="4f6b7-109">开发自定义管道组件</span><span class="sxs-lookup"><span data-stu-id="4f6b7-109">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)  
  
-   [<span data-ttu-id="4f6b7-110">开发自定义 Functoid</span><span class="sxs-lookup"><span data-stu-id="4f6b7-110">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)