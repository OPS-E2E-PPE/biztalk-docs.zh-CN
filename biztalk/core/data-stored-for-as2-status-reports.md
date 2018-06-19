---
title: AS2 状态报告为存储的数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6aa4077-3768-436b-99b9-d203a86a7e69
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2341004abe65864b2fceb90985871ecad0cf1e5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238509"
---
# <a name="data-stored-for-as2-status-reports"></a><span data-ttu-id="4d409-102">为 AS2 状态报告存储的数据</span><span class="sxs-lookup"><span data-stu-id="4d409-102">Data Stored for AS2 Status Reports</span></span>
<span data-ttu-id="4d409-103">AS2 状态报告中提供了两个级别的报告： 首先如果**打开 ON Reporting**了协议选择属性 (从**常规属性**页**常规**选项卡中**协议属性**对话框中)，第二个如果不可否认性数据库存储属性选择了协议。</span><span class="sxs-lookup"><span data-stu-id="4d409-103">Two levels of reporting are available in AS2 status reporting: the first if the **Turn ON Reporting** property is selected for an agreement (from the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box), and the second if a non-repudiation database storage property is selected for an agreement.</span></span>  
  
## <a name="data-stored-if-as2-reporting-is-activated"></a><span data-ttu-id="4d409-104">激活 AS2 报告时存储的数据</span><span class="sxs-lookup"><span data-stu-id="4d409-104">Data Stored If AS2 Reporting Is Activated</span></span>  
 <span data-ttu-id="4d409-105">如果**打开 ON Reporting**为一个协议，选中属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将保留的记录的所有发送或接收 AS2 消息和 Mdn。</span><span class="sxs-lookup"><span data-stu-id="4d409-105">If the **Turn ON Reporting** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will keep a record of all sent or received AS2 messages and MDNs.</span></span>  
  
 <span data-ttu-id="4d409-106">对于接收的 AS2 消息，BizTalk Server 将存储以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d409-106">For a received AS2 message, BizTalk Server will store the following information:</span></span>  
  
-   <span data-ttu-id="4d409-107">AS2 消息的记录。</span><span class="sxs-lookup"><span data-stu-id="4d409-107">A record of the AS2 message.</span></span>  
  
 <span data-ttu-id="4d409-108">对于接收或发送的 MDN（同步或异步），BizTalk Server 将存储以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d409-108">For a received or sent MDN (synchronous or asynchronous), BizTalk Server will store the following information:</span></span>  
  
-   <span data-ttu-id="4d409-109">MDN 的记录。</span><span class="sxs-lookup"><span data-stu-id="4d409-109">A record of the MDN.</span></span>  
  
 <span data-ttu-id="4d409-110">通过状态报告 UI，您可以将 AS2 消息记录和相应的 MDN 记录关联起来。</span><span class="sxs-lookup"><span data-stu-id="4d409-110">The status reporting UI enables correlation of the AS2 message record to the appropriate MDN record.</span></span>  
  
## <a name="data-stored-if-resend-as2-message-if-mdn-not-received-is-enabled"></a><span data-ttu-id="4d409-111">启用了“MDN 未收到时重新发送 AS2 消息”时存储的数据</span><span class="sxs-lookup"><span data-stu-id="4d409-111">Data Stored If Resend AS2 Message If MDN Not Received Is Enabled</span></span>  
 <span data-ttu-id="4d409-112">如果**重新发送 AS2 消息如果未收到 MDN**为一个协议，选中属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将记录以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d409-112">If the **Resend AS2 message if MDN not received** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will record the following information:</span></span>  
  
-   <span data-ttu-id="4d409-113">每次重新发送尝试的时间</span><span class="sxs-lookup"><span data-stu-id="4d409-113">Time of each resend attempt</span></span>  
  
-   <span data-ttu-id="4d409-114">每次重新发送尝试的状态</span><span class="sxs-lookup"><span data-stu-id="4d409-114">Status of each resend attempt</span></span>  
  
-   <span data-ttu-id="4d409-115">每次重新发送尝试的索引</span><span class="sxs-lookup"><span data-stu-id="4d409-115">Index of each resend attempt</span></span>  
  
## <a name="data-stored-if-non-repudiation-database-storage-is-enabled"></a><span data-ttu-id="4d409-116">启用不可否认数据库存储时存储的数据</span><span class="sxs-lookup"><span data-stu-id="4d409-116">Data Stored If Non-Repudiation Database Storage Is Enabled</span></span>  
 <span data-ttu-id="4d409-117">选择下列协议属性可以启用不可否认数据库存储：</span><span class="sxs-lookup"><span data-stu-id="4d409-117">Non-repudiation database storage is enabled by the following agreement properties is selected:</span></span>  
  
-   <span data-ttu-id="4d409-118">已为编码后的出站 AS2 消息启用 NRR</span><span class="sxs-lookup"><span data-stu-id="4d409-118">NRR enabled for outbound encoded AS2 messages</span></span>  
  
-   <span data-ttu-id="4d409-119">已为解码后的出站 AS2 消息启用 NRR</span><span class="sxs-lookup"><span data-stu-id="4d409-119">NRR enabled for outbound decoded AS2 messages</span></span>  
  
-   <span data-ttu-id="4d409-120">已为入站 MDN 启用 NRR</span><span class="sxs-lookup"><span data-stu-id="4d409-120">NRR enabled for inbound MDN</span></span>  
  
-   <span data-ttu-id="4d409-121">已为编码后的入站 AS2 消息启用 NRR</span><span class="sxs-lookup"><span data-stu-id="4d409-121">NRR enabled for inbound encoded AS2 messages</span></span>  
  
-   <span data-ttu-id="4d409-122">已为解码后的入站 AS2 消息启用 NRR</span><span class="sxs-lookup"><span data-stu-id="4d409-122">NRR enabled for inbound decoded AS2 messages</span></span>  
  
-   <span data-ttu-id="4d409-123">已为出站 MDN 启用 NRR</span><span class="sxs-lookup"><span data-stu-id="4d409-123">NRR enabled for outbound MDN</span></span>  
  
 <span data-ttu-id="4d409-124">如果选择上面的一个或多个属性，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将存储以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d409-124">If one or more of the above properties is selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store the following information:</span></span>  
  
-   <span data-ttu-id="4d409-125">任何 AS2 消息的内容和任何 MDN（带有或不带有 AS2 标头）的内容。</span><span class="sxs-lookup"><span data-stu-id="4d409-125">The content of any AS2 message and the content of any MDN (with or without AS2 headers).</span></span>  
  
## <a name="data-stored-for-edi-over-as2"></a><span data-ttu-id="4d409-126">通过 AS2 为 EDI 存储的数据</span><span class="sxs-lookup"><span data-stu-id="4d409-126">Data Stored For EDI Over AS2</span></span>  
 <span data-ttu-id="4d409-127">如果**打开 ON Reporting**同时 EDI 协议以及 AS2 协议，选择属性，然后您可以将 AS2 消息的记录 （包含 EDI 负载） 与 EDI 消息记录相关联。</span><span class="sxs-lookup"><span data-stu-id="4d409-127">If the **Turn ON Reporting** property is selected both for an EDI agreement as well as an AS2 agreement, then you can correlate an AS2 message record (containing EDI payload) with an EDI message record.</span></span>  
  
 <span data-ttu-id="4d409-128">如果启用事务集存储，则可以在状态报告 UI 中显示事务集的详细信息和 AS2 消息内容的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d409-128">If transaction set storage is enabled, you can display transaction set details and AS2 message content details in the status reporting UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d409-129">必须使用 AS2EdiReceive 或 AS2EdiSend 管道访问这些报告。</span><span class="sxs-lookup"><span data-stu-id="4d409-129">You must use the AS2EdiReceive or AS2EdiSend pipeline to have access to these reports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d409-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d409-130">See Also</span></span>  
 <span data-ttu-id="4d409-131">[对于 EDI 和 AS2 状态报表存储的数据](../core/data-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="4d409-131">[Data Stored for EDI and AS2 Status Reports](../core/data-stored-for-edi-and-as2-status-reports.md) </span></span>  
 <span data-ttu-id="4d409-132">[对于 EDI 状态报表存储的数据](../core/data-stored-for-edi-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="4d409-132">[Data Stored for EDI Status Reports](../core/data-stored-for-edi-status-reports.md) </span></span>  
 [<span data-ttu-id="4d409-133">为批处理状态报表存储的数据</span><span class="sxs-lookup"><span data-stu-id="4d409-133">Data Stored for Batching Status Reports</span></span>](../core/data-stored-for-batching-status-reports.md)