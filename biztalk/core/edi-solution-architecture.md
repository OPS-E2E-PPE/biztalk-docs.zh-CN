---
title: "EDI 解决方案体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55709a89-7706-4c64-ada3-16951951c943
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42afbb604a8cef1387418e175a39150f0182c607
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-solution-architecture"></a><span data-ttu-id="2327c-102">EDI 解决方案体系结构</span><span class="sxs-lookup"><span data-stu-id="2327c-102">EDI Solution Architecture</span></span>
<span data-ttu-id="2327c-103">电子数据交换 (EDI) 是业务实体以电子方式交换数据的最常见方式之一。</span><span class="sxs-lookup"><span data-stu-id="2327c-103">Electronic Data Interchange (EDI) is one of the most prevalent means by which business entities exchange data electronically.</span></span> <span data-ttu-id="2327c-104">使用 EDI 必须了解消息语法和标准（包括 ANSI X12 和 UN/EDIFACT）、消息传送协议以及传输。</span><span class="sxs-lookup"><span data-stu-id="2327c-104">EDI usage entails message syntax and standards (including ANSI X12 and UN/EDIFACT), messaging protocol, and transports.</span></span> <span data-ttu-id="2327c-105">以下是 EDI 消息传送的一些特性：</span><span class="sxs-lookup"><span data-stu-id="2327c-105">The following are characteristics of EDI messaging:</span></span>  
  
-   <span data-ttu-id="2327c-106">EDI 消息传送协议可确保数据始终如期到达，并自动检测和报告损坏的数据或不正确的数据。</span><span class="sxs-lookup"><span data-stu-id="2327c-106">EDI messaging protocols ensure that data always arrives as expected, and corrupted or incorrect data is automatically detected and reported.</span></span>  
  
-   <span data-ttu-id="2327c-107">EDI 机制通常指定数据聚合方案（批处理）。</span><span class="sxs-lookup"><span data-stu-id="2327c-107">EDI mechanisms usually specify data aggregation schemes (batching).</span></span>  
  
-   <span data-ttu-id="2327c-108">用户常常通过实现部分 EDI 准则或特定 EDI 准则来自定义 EDI 文档定义。</span><span class="sxs-lookup"><span data-stu-id="2327c-108">Users often customize EDI document definitions by implementing subset or specific implementation of an EDI guideline.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2327c-109"> 使用特定于 EDI 的接收和发送管道处理 EDI 消息，这些管道可以对 EDI 消息进行分析和序列化。</span><span class="sxs-lookup"><span data-stu-id="2327c-109"> processes EDI messages using receive and send pipelines specific to EDI that can parse and serialize EDI messages.</span></span> <span data-ttu-id="2327c-110">本节介绍 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 EDI 解决方案的体系结构，包括接收端和发送端处理、消息验证和状态报告的细节。</span><span class="sxs-lookup"><span data-stu-id="2327c-110">This section describes the architecture of EDI solutions on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], including specifics of receive-side and send-side processing, message validation, and status reporting.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2327c-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="2327c-111">In This Section</span></span>  
  
-   [<span data-ttu-id="2327c-112">EDI 消息传递</span><span class="sxs-lookup"><span data-stu-id="2327c-112">EDI Messaging</span></span>](../core/edi-messaging.md)  
  
-   [<span data-ttu-id="2327c-113">协议在 EDI 处理过程中的角色</span><span class="sxs-lookup"><span data-stu-id="2327c-113">The Role of Agreements in EDI Processing</span></span>](../core/the-role-of-agreements-in-edi-processing.md)  
  
-   [<span data-ttu-id="2327c-114">BizTalk Server 接收 EDI 消息的方式</span><span class="sxs-lookup"><span data-stu-id="2327c-114">How BizTalk Server Receives EDI Messages</span></span>](../core/how-biztalk-server-receives-edi-messages.md)  
  
-   [<span data-ttu-id="2327c-115">BizTalk Server 将 EDI 消息的发送</span><span class="sxs-lookup"><span data-stu-id="2327c-115">How BizTalk Server Sends EDI Messages</span></span>](../core/how-biztalk-server-sends-edi-messages.md)  
  
-   [<span data-ttu-id="2327c-116">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="2327c-116">EDI Message Validation</span></span>](../core/edi-message-validation.md)  
  
-   [<span data-ttu-id="2327c-117">使用 XML 工具扩展</span><span class="sxs-lookup"><span data-stu-id="2327c-117">Using the XML Tool Extensions</span></span>](../core/using-the-xml-tool-extensions.md)