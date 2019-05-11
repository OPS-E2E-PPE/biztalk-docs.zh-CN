---
title: EDI 解决方案体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55709a89-7706-4c64-ada3-16951951c943
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9df4d308af97e0fcccf52d2c6f42660afa7cf079
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350255"
---
# <a name="edi-solution-architecture"></a><span data-ttu-id="14f63-102">EDI 解决方案体系结构</span><span class="sxs-lookup"><span data-stu-id="14f63-102">EDI Solution Architecture</span></span>
<span data-ttu-id="14f63-103">电子数据交换 (EDI) 是通过业务实体数据以电子方式交换的最常见方式之一。</span><span class="sxs-lookup"><span data-stu-id="14f63-103">Electronic Data Interchange (EDI) is one of the most prevalent means by which business entities exchange data electronically.</span></span> <span data-ttu-id="14f63-104">使用 EDI 必须了解消息语法和标准 （包括 ANSI X12 和 UN/EDIFACT），消息传送协议以及传输。</span><span class="sxs-lookup"><span data-stu-id="14f63-104">EDI usage entails message syntax and standards (including ANSI X12 and UN/EDIFACT), messaging protocol, and transports.</span></span> <span data-ttu-id="14f63-105">EDI 消息传送的特征如下：</span><span class="sxs-lookup"><span data-stu-id="14f63-105">The following are characteristics of EDI messaging:</span></span>  
  
- <span data-ttu-id="14f63-106">EDI 消息传送协议可确保数据始终如期到达，并损坏或不正确的数据自动检测和报告。</span><span class="sxs-lookup"><span data-stu-id="14f63-106">EDI messaging protocols ensure that data always arrives as expected, and corrupted or incorrect data is automatically detected and reported.</span></span>  
  
- <span data-ttu-id="14f63-107">EDI 机制通常指定数据聚合方案 （批处理）。</span><span class="sxs-lookup"><span data-stu-id="14f63-107">EDI mechanisms usually specify data aggregation schemes (batching).</span></span>  
  
- <span data-ttu-id="14f63-108">用户通常通过实现子集或特定 EDI 准则来自定义 EDI 文档定义。</span><span class="sxs-lookup"><span data-stu-id="14f63-108">Users often customize EDI document definitions by implementing subset or specific implementation of an EDI guideline.</span></span>  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="14f63-109">处理 EDI 消息使用接收和发送管道特定于 EDI 的可以解析和序列化 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="14f63-109">processes EDI messages using receive and send pipelines specific to EDI that can parse and serialize EDI messages.</span></span> <span data-ttu-id="14f63-110">本部分介绍的 EDI 解决方案体系结构上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，包括接收端和发送端处理、 消息验证和状态报告的细节。</span><span class="sxs-lookup"><span data-stu-id="14f63-110">This section describes the architecture of EDI solutions on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], including specifics of receive-side and send-side processing, message validation, and status reporting.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14f63-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="14f63-111">In This Section</span></span>  
  
-   [<span data-ttu-id="14f63-112">EDI 消息传送</span><span class="sxs-lookup"><span data-stu-id="14f63-112">EDI Messaging</span></span>](../core/edi-messaging.md)  
  
-   [<span data-ttu-id="14f63-113">协议在 EDI 处理中的角色</span><span class="sxs-lookup"><span data-stu-id="14f63-113">The Role of Agreements in EDI Processing</span></span>](../core/the-role-of-agreements-in-edi-processing.md)  
  
-   [<span data-ttu-id="14f63-114">BizTalk Server 如何接收 EDI 消息</span><span class="sxs-lookup"><span data-stu-id="14f63-114">How BizTalk Server Receives EDI Messages</span></span>](../core/how-biztalk-server-receives-edi-messages.md)  
  
-   [<span data-ttu-id="14f63-115">BizTalk Server 如何发送 EDI 消息</span><span class="sxs-lookup"><span data-stu-id="14f63-115">How BizTalk Server Sends EDI Messages</span></span>](../core/how-biztalk-server-sends-edi-messages.md)  
  
-   [<span data-ttu-id="14f63-116">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="14f63-116">EDI Message Validation</span></span>](../core/edi-message-validation.md)  
  
-   [<span data-ttu-id="14f63-117">使用 XML 工具扩展</span><span class="sxs-lookup"><span data-stu-id="14f63-117">Using the XML Tool Extensions</span></span>](../core/using-the-xml-tool-extensions.md)