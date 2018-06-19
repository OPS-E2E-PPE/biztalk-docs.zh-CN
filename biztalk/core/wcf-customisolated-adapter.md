---
title: WCF CustomIsolated 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-CustomIsolated adapters
ms.assetid: 0b529992-65e4-4543-951f-61644f8315a0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 734986a7ea87ff3b5a4b4a46a307d44665246b22
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288493"
---
# <a name="wcf-customisolated-adapter"></a><span data-ttu-id="3bd62-102">WCF CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="3bd62-102">WCF-CustomIsolated Adapter</span></span>
<span data-ttu-id="3bd62-103">WCF CustomIsolated 适配器是一个独立的适配器，来允许配置的绑定和行为设置为 Windows Communication Foundation (WCF) 适用于通过 HTTP 传输接收位置[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3bd62-103">The WCF-CustomIsolated adapter is an isolated adapter to allow configuring receive locations over the HTTP transport with any binding and behavior settings for Windows Communication Foundation (WCF) that are applicable to [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3bd62-104">您可在标准 WCF 适配器不支持的情况下使用 WCF-CustomIsolated 适配器。</span><span class="sxs-lookup"><span data-stu-id="3bd62-104">You can use the WCF-CustomIsolated adapter for scenarios that the standard WCF adapters do not support.</span></span> <span data-ttu-id="3bd62-105">WCF CustomIsolated 适配器还可以使用中的 WCF 扩展性点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3bd62-105">The WCF-CustomIsolated adapter also enables you to use the WCF extensibility points in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3bd62-106">WCF-CustomIsolated 适配器用于在独立主机中运行的接收位置。</span><span class="sxs-lookup"><span data-stu-id="3bd62-106">The WCF-CustomIsolated adapter is used for the receive location running in an isolated host.</span></span> <span data-ttu-id="3bd62-107">若要使用 WCF-CustomIsolated 适配器，必须使用 BizTalk WCF 服务发布向导在 Microsoft Internet 信息服务 (IIS) 中创建与此接收位置对应的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="3bd62-107">To use the WCF-CustomIsolated adapter, you must use the BizTalk WCF Service Publishing Wizard to create in Microsoft Internet Information Services (IIS) the virtual directory corresponding to this receive location.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3bd62-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="3bd62-108">In This Section</span></span>  
  
-   [<span data-ttu-id="3bd62-109">什么是 WCF CustomIsolated 适配器？</span><span class="sxs-lookup"><span data-stu-id="3bd62-109">What Is the WCF-CustomIsolated Adapter?</span></span>](../core/what-is-the-wcf-customisolated-adapter.md)  
  
-   [<span data-ttu-id="3bd62-110">配置 WCF CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="3bd62-110">Configuring the WCF-CustomIsolated Adapter</span></span>](../core/configuring-the-wcf-customisolated-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="3bd62-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bd62-111">See Also</span></span>  
 [<span data-ttu-id="3bd62-112">扩展性介绍</span><span class="sxs-lookup"><span data-stu-id="3bd62-112">Introduction to Extensibility</span></span>](http://go.microsoft.com/fwlink/?LinkId=82590)