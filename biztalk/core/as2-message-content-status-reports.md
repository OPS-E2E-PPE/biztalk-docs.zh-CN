---
title: AS2 消息内容状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6244aa59-a80d-450b-ab95-9a5e14c0c40e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f8461e2433f9d7cfb14dd0d4961704ec624db8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996880"
---
# <a name="as2-message-content-status-reports"></a><span data-ttu-id="bd376-102">AS2 消息内容状态报告</span><span class="sxs-lookup"><span data-stu-id="bd376-102">AS2 Message Content Status Reports</span></span>

## <a name="overview"></a><span data-ttu-id="bd376-103">概述</span><span class="sxs-lookup"><span data-stu-id="bd376-103">Overview</span></span>
<span data-ttu-id="bd376-104">这些状态报告显示 AS2 消息或 MDN 的上下文属性、标头和负载。</span><span class="sxs-lookup"><span data-stu-id="bd376-104">These status reports display the context properties, headers and payload of an AS2 message or an MDN.</span></span> <span data-ttu-id="bd376-105">总共有三个 AS2 消息内容状态报告：</span><span class="sxs-lookup"><span data-stu-id="bd376-105">There are three AS2 message content status reports:</span></span>  
  
- <span data-ttu-id="bd376-106">消息传输格式报告</span><span class="sxs-lookup"><span data-stu-id="bd376-106">Message Wire Format report</span></span>  
  
- <span data-ttu-id="bd376-107">报告消息解码格式</span><span class="sxs-lookup"><span data-stu-id="bd376-107">Message Decoded Format report</span></span>  
  
- <span data-ttu-id="bd376-108">Mdn 消息报告</span><span class="sxs-lookup"><span data-stu-id="bd376-108">Mdn Message report</span></span>  
  
  <span data-ttu-id="bd376-109">通过右键单击 AS2/MDN 状态报表中的 AS2 消息，然后单击显示这些报表之一**查看消息传输格式**，**查看消息解码格式**，或**视图 Mdn消息**。</span><span class="sxs-lookup"><span data-stu-id="bd376-109">You display one of these reports by right-clicking an AS2 message within the AS2/MDN status report, and then clicking **View Message Wire Format**, **View Message Decoded Format**, or **View Mdn Message**.</span></span> <span data-ttu-id="bd376-110">MDN 命令将显示与 AS2 消息相关联的 MDN。</span><span class="sxs-lookup"><span data-stu-id="bd376-110">The MDN command will display the MDN that is correlated to the AS2 message.</span></span>  
  
  <span data-ttu-id="bd376-111">仅当已选择相应的"在不可否认数据库中的存储区消息"属性的参与方中作为 AS2 消息发送方页或参与方作为 AS2 消息接收方的 AS2 属性对话框的页的相关参与方提供的每个这些报表。</span><span class="sxs-lookup"><span data-stu-id="bd376-111">Each of these reports is available only if you have selected the corresponding "Store messages in non-repudiation database" properties in the Party as AS2 Message Sender page or Party as AS2 Message Receiver page of the AS2 Properties dialog box for the related party.</span></span> <span data-ttu-id="bd376-112">此命令以传输格式或解码格式将 AS2 消息或 MDN 存储在 BizTalkDTADb 数据库中。</span><span class="sxs-lookup"><span data-stu-id="bd376-112">The commands store AS2 messages or MDNs in wire format or decoded format in the BizTalkDTADb database.</span></span>  
  
  <span data-ttu-id="bd376-113">此报表使用**消息详细信息属性对话框**(请参阅 UI 详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) 以显示消息数据，且将信息分到页面：</span><span class="sxs-lookup"><span data-stu-id="bd376-113">This report uses the **Message Details Properties Dialog Box** (see the UI details [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) to display message data, with information separated into pages:</span></span>  
  
|<span data-ttu-id="bd376-114">第</span><span class="sxs-lookup"><span data-stu-id="bd376-114">Page</span></span>|<span data-ttu-id="bd376-115">显示的数据</span><span class="sxs-lookup"><span data-stu-id="bd376-115">Data Displayed</span></span>|  
|----------|--------------------|  
|<span data-ttu-id="bd376-116">**常规**</span><span class="sxs-lookup"><span data-stu-id="bd376-116">**General**</span></span>|<span data-ttu-id="bd376-117">有关消息的概述信息</span><span class="sxs-lookup"><span data-stu-id="bd376-117">Overview information about the message</span></span>|  
|<span data-ttu-id="bd376-118">**上下文**</span><span class="sxs-lookup"><span data-stu-id="bd376-118">**Context**</span></span>|<span data-ttu-id="bd376-119">与此消息相关联的上下文属性</span><span class="sxs-lookup"><span data-stu-id="bd376-119">Context properties associated with this message</span></span>|  
|<span data-ttu-id="bd376-120">**消息部件**</span><span class="sxs-lookup"><span data-stu-id="bd376-120">**Message Parts**</span></span>|<span data-ttu-id="bd376-121">此消息中包含的各个文档负载。</span><span class="sxs-lookup"><span data-stu-id="bd376-121">Individual document payload contained within this message.</span></span> <span data-ttu-id="bd376-122">每个文档都可被视为文本或二进制文件：</span><span class="sxs-lookup"><span data-stu-id="bd376-122">Each document can be viewed as either text or binary:</span></span><br /><br /> <span data-ttu-id="bd376-123">文本格式视图显示 AS2 消息或 MDN 的内容中的可读的窗体，如 EDI 文本文件中所示。</span><span class="sxs-lookup"><span data-stu-id="bd376-123">-   Text Format view shows the contents of the AS2 message or MDN in human-readable form, as in an EDI text file.</span></span> <span data-ttu-id="bd376-124">此视图显示 AS2 标头、EDI 尾部和 EDI 负载，每个分段都位于单独的行中。</span><span class="sxs-lookup"><span data-stu-id="bd376-124">This view shows the AS2 headers, EDI trailers, and EDI payload, with each segment on a separate line.</span></span><br /><span data-ttu-id="bd376-125">的视图二进制格式显示 AS2 消息或 MDN 的内容以非分隔文本格式和 AS2 消息或 MDN 中的每个 ASCII 字符的十六进制表示形式的表。</span><span class="sxs-lookup"><span data-stu-id="bd376-125">-   Binary Format view shows the contents of the AS2 message or MDN in non-delimited text format and a table of the hexadecimal representations for each ASCII character in the AS2 message or MDN.</span></span>|