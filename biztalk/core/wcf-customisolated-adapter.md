---
title: Wcf-customisolated 适配器 |Microsoft Docs
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
ms.openlocfilehash: 56bb02f99aaebf4e301239c26cfcf9f6e6c21c4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399409"
---
# <a name="wcf-customisolated-adapter"></a><span data-ttu-id="8b5d6-102">Wcf-customisolated 适配器</span><span class="sxs-lookup"><span data-stu-id="8b5d6-102">WCF-CustomIsolated Adapter</span></span>
<span data-ttu-id="8b5d6-103">Wcf-customisolated 适配器是一个独立的适配器，以允许配置接收位置通过 HTTP 传输的绑定和行为设置为 Windows Communication Foundation (WCF) 适用于[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8b5d6-103">The WCF-CustomIsolated adapter is an isolated adapter to allow configuring receive locations over the HTTP transport with any binding and behavior settings for Windows Communication Foundation (WCF) that are applicable to [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="8b5d6-104">对 WCF CustomIsolated 适配器可用于标准 WCF 适配器不支持的方案。</span><span class="sxs-lookup"><span data-stu-id="8b5d6-104">You can use the WCF-CustomIsolated adapter for scenarios that the standard WCF adapters do not support.</span></span> <span data-ttu-id="8b5d6-105">对 WCF CustomIsolated 适配器还可以使用 WCF 扩展点在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8b5d6-105">The WCF-CustomIsolated adapter also enables you to use the WCF extensibility points in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8b5d6-106">Wcf-customisolated 适配器用于在独立主机中运行的接收位置。</span><span class="sxs-lookup"><span data-stu-id="8b5d6-106">The WCF-CustomIsolated adapter is used for the receive location running in an isolated host.</span></span> <span data-ttu-id="8b5d6-107">若要使用 Wcf-customisolated 适配器，必须使用 BizTalk WCF 服务发布向导来创建在 Microsoft Internet 信息服务 (IIS) 虚拟目录对应于此接收位置。</span><span class="sxs-lookup"><span data-stu-id="8b5d6-107">To use the WCF-CustomIsolated adapter, you must use the BizTalk WCF Service Publishing Wizard to create in Microsoft Internet Information Services (IIS) the virtual directory corresponding to this receive location.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b5d6-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="8b5d6-108">In This Section</span></span>  
  
-   [<span data-ttu-id="8b5d6-109">WCF-CustomIsolated 适配器概述</span><span class="sxs-lookup"><span data-stu-id="8b5d6-109">What Is the WCF-CustomIsolated Adapter?</span></span>](../core/what-is-the-wcf-customisolated-adapter.md)  
  
-   [<span data-ttu-id="8b5d6-110">配置 WCF-CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="8b5d6-110">Configuring the WCF-CustomIsolated Adapter</span></span>](../core/configuring-the-wcf-customisolated-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="8b5d6-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b5d6-111">See Also</span></span>  
 [<span data-ttu-id="8b5d6-112">扩展性介绍</span><span class="sxs-lookup"><span data-stu-id="8b5d6-112">Introduction to Extensibility</span></span>](http://go.microsoft.com/fwlink/?LinkId=82590)