---
title: 窗体中生成 MT MX InfoPath 表单生成器实用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41f2fd51-c492-499b-89aa-1b44ed5c9669
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 438744d534dd8806a708a2eec527569d8451508e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377575"
---
# <a name="form-generator-utility-to-generate-mtmx-infopath-forms"></a><span data-ttu-id="3a4f3-102">若要生成 MT/MX InfoPath 表单的表单生成器实用程序</span><span class="sxs-lookup"><span data-stu-id="3a4f3-102">Form Generator Utility to Generate MT/MX InfoPath Forms</span></span>
<span data-ttu-id="3a4f3-103">本文档的目的是说明如何生成和发布 MT 和 MX InfoPath 窗体使用窗体生成器实用程序。</span><span class="sxs-lookup"><span data-stu-id="3a4f3-103">The purpose of this document is to explain how to generate and publish MT and MX InfoPath 2010 forms using Form Generator Utility.</span></span> <span data-ttu-id="3a4f3-104">消息修复和新提交的功能使用这些窗体[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3a4f3-104">These forms are used by the Message Repair and New Submission feature of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span>  
  
 <span data-ttu-id="3a4f3-105">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="3a4f3-105">This section contains:</span></span>  
  
-   [<span data-ttu-id="3a4f3-106">实现示例</span><span class="sxs-lookup"><span data-stu-id="3a4f3-106">Implementing the Sample</span></span>](../../adapters-and-accelerators/accelerator-swift/implementing-the-sample.md)  
  
-   [<span data-ttu-id="3a4f3-107">MT 消息示例</span><span class="sxs-lookup"><span data-stu-id="3a4f3-107">Examples of MT Messages</span></span>](../../adapters-and-accelerators/accelerator-swift/examples-of-mt-messages.md)  
  
-   [<span data-ttu-id="3a4f3-108">生成类别 0 和 MT121 表单</span><span class="sxs-lookup"><span data-stu-id="3a4f3-108">Generating Category 0 and MT121 Forms</span></span>](../../adapters-and-accelerators/accelerator-swift/generating-category-0-and-mt121-forms.md)  
  
-   [<span data-ttu-id="3a4f3-109">MX 消息示例</span><span class="sxs-lookup"><span data-stu-id="3a4f3-109">Examples of MX Messages</span></span>](../../adapters-and-accelerators/accelerator-swift/examples-of-mx-messages.md)  
  
-   [<span data-ttu-id="3a4f3-110">在 SharePoint 站点上生成和发布 MT/MX 表单</span><span class="sxs-lookup"><span data-stu-id="3a4f3-110">Generating and Publishing MT/MX Forms on the SharePoint Site</span></span>](../../adapters-and-accelerators/accelerator-swift/generating-and-publishing-mt-mx-forms-on-the-sharepoint-site.md)  
  
-   [<span data-ttu-id="3a4f3-111">发布 MT 消息实例文件（创建新消息）</span><span class="sxs-lookup"><span data-stu-id="3a4f3-111">Publishing the MT Message Instance File (Creating New Messages)</span></span>](../../adapters-and-accelerators/accelerator-swift/publishing-the-mt-message-instance-file-creating-new-messages.md)  
  
-   [<span data-ttu-id="3a4f3-112">发布 MX 消息实例文件（创建新消息）</span><span class="sxs-lookup"><span data-stu-id="3a4f3-112">Publishing the MX Message Instance File (Creating New Messages)</span></span>](../../adapters-and-accelerators/accelerator-swift/publishing-the-mx-message-instance-file-creating-new-messages.md)  
  
-   [<span data-ttu-id="3a4f3-113">MX InfoPath 表单的多个视图</span><span class="sxs-lookup"><span data-stu-id="3a4f3-113">Multiple Views of MX InfoPath forms</span></span>](../../adapters-and-accelerators/accelerator-swift/multiple-views-of-mx-infopath-forms.md)