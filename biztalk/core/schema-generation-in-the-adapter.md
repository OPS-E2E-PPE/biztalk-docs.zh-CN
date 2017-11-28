---
title: "适配器中的架构生成 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, generating
- writing, schemas
ms.assetid: 43b69383-bae0-401b-9620-d4302db799b2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d10d927e4ede59e716b3f9838c96bac8cd144a81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="schema-generation-in-the-adapter"></a><span data-ttu-id="66f84-102">适配器中的架构生成</span><span class="sxs-lookup"><span data-stu-id="66f84-102">Schema Generation in the Adapter</span></span>
<span data-ttu-id="66f84-103">TIBCO Rendezvous 系统中没有消息类型存储库。</span><span class="sxs-lookup"><span data-stu-id="66f84-103">A TIBCO Rendezvous system does not include a message types repository.</span></span> <span data-ttu-id="66f84-104">所有消息构造和解析都在 Rendezvous 应用程序级别隐藏了。</span><span class="sxs-lookup"><span data-stu-id="66f84-104">All the message construction and parsing is buried at the Rendezvous application level.</span></span> <span data-ttu-id="66f84-105">由于这个限制，用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器无法提供架构生成功能。</span><span class="sxs-lookup"><span data-stu-id="66f84-105">Because of this limitation, Microsoft BizTalk Adapter for TIBCO Rendezvous cannot provide schema-generation capabilities.</span></span>  
  
## <a name="writing-schemas"></a><span data-ttu-id="66f84-106">编写架构</span><span class="sxs-lookup"><span data-stu-id="66f84-106">Writing Schemas</span></span>  
 <span data-ttu-id="66f84-107">你必须编写架构和使用**添加现有项**在 Visual Studio 中将其导入在业务流程中使用。</span><span class="sxs-lookup"><span data-stu-id="66f84-107">You must write a schema and use **Add Existing Item** in Visual Studio to import it for use in orchestrations.</span></span> <span data-ttu-id="66f84-108">架构对于 BizTalk Server 开发工具和 Visual Studio 中的集成都非常重要。</span><span class="sxs-lookup"><span data-stu-id="66f84-108">Schemas are very important for BizTalk Server development tools and for integration in Visual Studio.</span></span> <span data-ttu-id="66f84-109">BizTalk Server 开发人员可以选择提供完整架构、最低限要求的架构，或介于二者之间的版本。</span><span class="sxs-lookup"><span data-stu-id="66f84-109">BizTalk Server developers can choose to provide a complete schema, a minimalist schema, or a version somewhere in between.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66f84-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66f84-110">See Also</span></span>  
 [<span data-ttu-id="66f84-111">入门</span><span class="sxs-lookup"><span data-stu-id="66f84-111">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)