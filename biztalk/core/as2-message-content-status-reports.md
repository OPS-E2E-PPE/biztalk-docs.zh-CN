---
title: "AS2 消息内容的状态报告 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6244aa59-a80d-450b-ab95-9a5e14c0c40e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b2dadb3231136255dcf532e5054c1a6228880f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="as2-message-content-status-reports"></a><span data-ttu-id="518aa-102">AS2 消息内容状态报告</span><span class="sxs-lookup"><span data-stu-id="518aa-102">AS2 Message Content Status Reports</span></span>

## <a name="overview"></a><span data-ttu-id="518aa-103">概述</span><span class="sxs-lookup"><span data-stu-id="518aa-103">Overview</span></span>
<span data-ttu-id="518aa-104">这些状态报告显示 AS2 消息或 MDN 的上下文属性、标头和负载。</span><span class="sxs-lookup"><span data-stu-id="518aa-104">These status reports display the context properties, headers and payload of an AS2 message or an MDN.</span></span> <span data-ttu-id="518aa-105">总共有三个 AS2 消息内容状态报告：</span><span class="sxs-lookup"><span data-stu-id="518aa-105">There are three AS2 message content status reports:</span></span>  
  
-   <span data-ttu-id="518aa-106">消息连网格式报表</span><span class="sxs-lookup"><span data-stu-id="518aa-106">Message Wire Format report</span></span>  
  
-   <span data-ttu-id="518aa-107">消息解码格式报表</span><span class="sxs-lookup"><span data-stu-id="518aa-107">Message Decoded Format report</span></span>  
  
-   <span data-ttu-id="518aa-108">Mdn 消息报告</span><span class="sxs-lookup"><span data-stu-id="518aa-108">Mdn Message report</span></span>  
  
 <span data-ttu-id="518aa-109">通过右键单击 AS2/MDN 状态报表中，在 AS2 消息，然后单击显示两个报表**视图消息连网格式**，**视图消息解码格式**，或**视图 Mdn消息**。</span><span class="sxs-lookup"><span data-stu-id="518aa-109">You display one of these reports by right-clicking an AS2 message within the AS2/MDN status report, and then clicking **View Message Wire Format**, **View Message Decoded Format**, or **View Mdn Message**.</span></span> <span data-ttu-id="518aa-110">MDN 命令将显示与 AS2 消息相关联的 MDN。</span><span class="sxs-lookup"><span data-stu-id="518aa-110">The MDN command will display the MDN that is correlated to the AS2 message.</span></span>  
  
 <span data-ttu-id="518aa-111">每个这些报表是你选择了相应的"不可否认性数据库中的应用商店消息"属性中方为 AS2 消息发送方页或方为 AS2 属性对话框中的 AS2 消息接收方页面相关当事方时才可用。</span><span class="sxs-lookup"><span data-stu-id="518aa-111">Each of these reports is available only if you have selected the corresponding "Store messages in non-repudiation database" properties in the Party as AS2 Message Sender page or Party as AS2 Message Receiver page of the AS2 Properties dialog box for the related party.</span></span> <span data-ttu-id="518aa-112">此命令以传输格式或解码格式将 AS2 消息或 MDN 存储在 BizTalkDTADb 数据库中。</span><span class="sxs-lookup"><span data-stu-id="518aa-112">The commands store AS2 messages or MDNs in wire format or decoded format in the BizTalkDTADb database.</span></span>  
  
 <span data-ttu-id="518aa-113">此报表使用**消息详细信息属性对话框中**(请参阅 UI 详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) 与分到多个页的信息一起显示消息数据：</span><span class="sxs-lookup"><span data-stu-id="518aa-113">This report uses the **Message Details Properties Dialog Box** (see the UI details [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) to display message data, with information separated into pages:</span></span>  
  
|<span data-ttu-id="518aa-114">第</span><span class="sxs-lookup"><span data-stu-id="518aa-114">Page</span></span>|<span data-ttu-id="518aa-115">显示的数据</span><span class="sxs-lookup"><span data-stu-id="518aa-115">Data Displayed</span></span>|  
|----------|--------------------|  
|<span data-ttu-id="518aa-116">**常规**</span><span class="sxs-lookup"><span data-stu-id="518aa-116">**General**</span></span>|<span data-ttu-id="518aa-117">有关消息的概述信息</span><span class="sxs-lookup"><span data-stu-id="518aa-117">Overview information about the message</span></span>|  
|<span data-ttu-id="518aa-118">**上下文**</span><span class="sxs-lookup"><span data-stu-id="518aa-118">**Context**</span></span>|<span data-ttu-id="518aa-119">与此消息关联的上下文属性</span><span class="sxs-lookup"><span data-stu-id="518aa-119">Context properties associated with this message</span></span>|  
|<span data-ttu-id="518aa-120">**消息部分**</span><span class="sxs-lookup"><span data-stu-id="518aa-120">**Message Parts**</span></span>|<span data-ttu-id="518aa-121">此消息中包含的单独文档负载。</span><span class="sxs-lookup"><span data-stu-id="518aa-121">Individual document payload contained within this message.</span></span> <span data-ttu-id="518aa-122">每个文档都可被视为文本或二进制文件：</span><span class="sxs-lookup"><span data-stu-id="518aa-122">Each document can be viewed as either text or binary:</span></span><br /><br /> <span data-ttu-id="518aa-123">文本格式视图显示用户可读的窗体，如下所示的 EDI 文本文件中的 AS2 消息或 MDN 的内容。</span><span class="sxs-lookup"><span data-stu-id="518aa-123">-   Text Format view shows the contents of the AS2 message or MDN in human-readable form, as in an EDI text file.</span></span> <span data-ttu-id="518aa-124">此视图显示 AS2 标头、EDI 尾部和 EDI 负载，每个分段都位于单独的行中。</span><span class="sxs-lookup"><span data-stu-id="518aa-124">This view shows the AS2 headers, EDI trailers, and EDI payload, with each segment on a separate line.</span></span><br /><span data-ttu-id="518aa-125">-二进制格式视图显示非分隔的文本格式和为 MDN 的 AS2 消息中每个 ASCII 字符的十六进制表示的表中的 AS2 消息或 MDN 的内容。</span><span class="sxs-lookup"><span data-stu-id="518aa-125">-   Binary Format view shows the contents of the AS2 message or MDN in non-delimited text format and a table of the hexadecimal representations for each ASCII character in the AS2 message or MDN.</span></span>|