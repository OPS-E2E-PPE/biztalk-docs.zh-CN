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
ms.openlocfilehash: 89504de79279a42d14061606a31985bed0563635
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358918"
---
# <a name="as2-message-content-status-reports"></a><span data-ttu-id="69926-102">AS2 消息内容状态报告</span><span class="sxs-lookup"><span data-stu-id="69926-102">AS2 Message Content Status Reports</span></span>

## <a name="overview"></a><span data-ttu-id="69926-103">概述</span><span class="sxs-lookup"><span data-stu-id="69926-103">Overview</span></span>
<span data-ttu-id="69926-104">这些状态报告显示标头和负载的 AS2 消息或 MDN 的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="69926-104">These status reports display the context properties, headers and payload of an AS2 message or an MDN.</span></span> <span data-ttu-id="69926-105">有三个 AS2 消息内容状态报告：</span><span class="sxs-lookup"><span data-stu-id="69926-105">There are three AS2 message content status reports:</span></span>  
  
- <span data-ttu-id="69926-106">消息传输格式报告</span><span class="sxs-lookup"><span data-stu-id="69926-106">Message Wire Format report</span></span>  
  
- <span data-ttu-id="69926-107">报告消息解码格式</span><span class="sxs-lookup"><span data-stu-id="69926-107">Message Decoded Format report</span></span>  
  
- <span data-ttu-id="69926-108">Mdn 消息报告</span><span class="sxs-lookup"><span data-stu-id="69926-108">Mdn Message report</span></span>  
  
  <span data-ttu-id="69926-109">通过右键单击 AS2/MDN 状态报表中的 AS2 消息，然后单击显示这些报表之一**查看消息传输格式**，**查看消息解码格式**，或**视图 Mdn消息**。</span><span class="sxs-lookup"><span data-stu-id="69926-109">You display one of these reports by right-clicking an AS2 message within the AS2/MDN status report, and then clicking **View Message Wire Format**, **View Message Decoded Format**, or **View Mdn Message**.</span></span> <span data-ttu-id="69926-110">MDN 命令将显示关联的 MDN 的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="69926-110">The MDN command will display the MDN that is correlated to the AS2 message.</span></span>  
  
  <span data-ttu-id="69926-111">仅当已选择相应的"在不可否认数据库中的存储区消息"属性的参与方中作为 AS2 消息发送方页或参与方作为 AS2 消息接收方的 AS2 属性对话框的页的相关参与方提供的每个这些报表。</span><span class="sxs-lookup"><span data-stu-id="69926-111">Each of these reports is available only if you have selected the corresponding "Store messages in non-repudiation database" properties in the Party as AS2 Message Sender page or Party as AS2 Message Receiver page of the AS2 Properties dialog box for the related party.</span></span> <span data-ttu-id="69926-112">命令以传输格式或 BizTalkDTADb 数据库中的解码的格式存储 AS2 消息或 Mdn。</span><span class="sxs-lookup"><span data-stu-id="69926-112">The commands store AS2 messages or MDNs in wire format or decoded format in the BizTalkDTADb database.</span></span>  
  
  <span data-ttu-id="69926-113">此报表使用**消息详细信息属性对话框**(请参阅 UI 详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) 以显示消息数据，且将信息分到页面：</span><span class="sxs-lookup"><span data-stu-id="69926-113">This report uses the **Message Details Properties Dialog Box** (see the UI details [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) to display message data, with information separated into pages:</span></span>  
  
|<span data-ttu-id="69926-114">第</span><span class="sxs-lookup"><span data-stu-id="69926-114">Page</span></span>|<span data-ttu-id="69926-115">显示数据</span><span class="sxs-lookup"><span data-stu-id="69926-115">Data Displayed</span></span>|  
|----------|--------------------|  
|<span data-ttu-id="69926-116">**常规**</span><span class="sxs-lookup"><span data-stu-id="69926-116">**General**</span></span>|<span data-ttu-id="69926-117">有关消息的概述信息</span><span class="sxs-lookup"><span data-stu-id="69926-117">Overview information about the message</span></span>|  
|<span data-ttu-id="69926-118">**上下文**</span><span class="sxs-lookup"><span data-stu-id="69926-118">**Context**</span></span>|<span data-ttu-id="69926-119">与此消息相关联的上下文属性</span><span class="sxs-lookup"><span data-stu-id="69926-119">Context properties associated with this message</span></span>|  
|<span data-ttu-id="69926-120">**消息部件**</span><span class="sxs-lookup"><span data-stu-id="69926-120">**Message Parts**</span></span>|<span data-ttu-id="69926-121">此消息中包含的各个文档负载。</span><span class="sxs-lookup"><span data-stu-id="69926-121">Individual document payload contained within this message.</span></span> <span data-ttu-id="69926-122">为文本或二进制文件，可以查看每个文档：</span><span class="sxs-lookup"><span data-stu-id="69926-122">Each document can be viewed as either text or binary:</span></span><br /><br /> <span data-ttu-id="69926-123">文本格式视图显示 AS2 消息或 MDN 的内容中的可读的窗体，如 EDI 文本文件中所示。</span><span class="sxs-lookup"><span data-stu-id="69926-123">-   Text Format view shows the contents of the AS2 message or MDN in human-readable form, as in an EDI text file.</span></span> <span data-ttu-id="69926-124">此视图显示 AS2 标头、 EDI 尾部和 EDI 负载，使用单独的行上的每个段。</span><span class="sxs-lookup"><span data-stu-id="69926-124">This view shows the AS2 headers, EDI trailers, and EDI payload, with each segment on a separate line.</span></span><br /><span data-ttu-id="69926-125">的视图二进制格式显示 AS2 消息或 MDN 的内容以非分隔文本格式和 AS2 消息或 MDN 中的每个 ASCII 字符的十六进制表示形式的表。</span><span class="sxs-lookup"><span data-stu-id="69926-125">-   Binary Format view shows the contents of the AS2 message or MDN in non-delimited text format and a table of the hexadecimal representations for each ASCII character in the AS2 message or MDN.</span></span>|