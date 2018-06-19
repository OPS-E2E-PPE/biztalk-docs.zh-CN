---
title: BizTalk Server AS2 功能 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c16c017e-b68b-483b-a4af-e47eb229de00
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c72e8acf77f57c18a87a44de365ea1ab611e49c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230997"
---
# <a name="biztalk-server-as2-functionality"></a><span data-ttu-id="cea5e-102">BizTalk Server AS2 功能</span><span class="sxs-lookup"><span data-stu-id="cea5e-102">BizTalk Server AS2 Functionality</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="cea5e-103"> 通过使用核心 BizTalk Server 功能和特定于 AS2 的 BizTalk Server 功能的组合来处理 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="cea5e-103"> processes AS2 messages using a combination of core BizTalk Server features and AS2-specific BizTalk Server features.</span></span> <span data-ttu-id="cea5e-104">这使 BizTalk Server 来执行处理所独有的 AS2 消息传送，同时充分利用其核心消息传送功能。</span><span class="sxs-lookup"><span data-stu-id="cea5e-104">This enables BizTalk Server to perform the processing that is unique to AS2 messaging, while leveraging its core messaging functionality.</span></span> <span data-ttu-id="cea5e-105">如果通过 AS2 传输 EDI 文档，则还会使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中某些特定于 EDI 的功能。</span><span class="sxs-lookup"><span data-stu-id="cea5e-105">If EDI documents are transported over AS2, some of the EDI-specific functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also be used.</span></span>  
  
 <span data-ttu-id="cea5e-106">本部分介绍了基本 AS2 消息以及 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的实现方法。</span><span class="sxs-lookup"><span data-stu-id="cea5e-106">This section describes basic AS2 messaging and how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implements it.</span></span> <span data-ttu-id="cea5e-107">它还描述如何带来的贸易合作伙伴协议定义了 AS2 处理、 接收方 AS2 处理和发送方 AS2 处理。</span><span class="sxs-lookup"><span data-stu-id="cea5e-107">It also describes how a trading partner agreement definition can be leveraged for AS2 processing, receive-side AS2 processing, and send-side AS2 processing.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cea5e-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="cea5e-108">In This Section</span></span>  
  
-   [<span data-ttu-id="cea5e-109">BizTalk Server 中的 AS2 支持</span><span class="sxs-lookup"><span data-stu-id="cea5e-109">AS2 Support in BizTalk Server</span></span>](../core/as2-support-in-biztalk-server.md)  
  
-   [<span data-ttu-id="cea5e-110">在 BizTalk Server 中的 AS2 处理</span><span class="sxs-lookup"><span data-stu-id="cea5e-110">AS2 Processing in BizTalk Server</span></span>](../core/as2-processing-in-biztalk-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="cea5e-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cea5e-111">See Also</span></span>  
 <span data-ttu-id="cea5e-112">[BizTalk Server EDI 功能。](../core/biztalk-server-edi-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="cea5e-112">[BizTalk Server EDI Functionality](../core/biztalk-server-edi-functionality.md) </span></span>  
 [<span data-ttu-id="cea5e-113">AS2 解决方案体系结构</span><span class="sxs-lookup"><span data-stu-id="cea5e-113">AS2 Solution Architecture</span></span>](../core/as2-solution-architecture.md)