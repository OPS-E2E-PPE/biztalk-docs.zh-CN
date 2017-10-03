---
title: "通过查看挂起的消息的十六进制内容来解决消息验证失败 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cf14cd9-2d4b-43a3-9738-52bfd879e1e4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f7dc0f24a85f206831e3706bd03f2206aaa2c15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-message-validation-failures-by-viewing-the-hexadecimal-contents-of-suspended-messages"></a><span data-ttu-id="1f45f-102">通过查看挂起的消息的十六进制内容来解决消息验证失败</span><span class="sxs-lookup"><span data-stu-id="1f45f-102">Troubleshooting Message Validation Failures by Viewing the Hexadecimal Contents of Suspended Messages</span></span>
<span data-ttu-id="1f45f-103">如果消息由于验证失败而挂起，通过查看消息部分的十六进制表示形式可以帮助确定导致验证失败的原因。</span><span class="sxs-lookup"><span data-stu-id="1f45f-103">If a message is suspended due to validation failures, it may be helpful to view the hexadecimal representation of the message parts to determine the cause of the validation failure.</span></span> <span data-ttu-id="1f45f-104">本主题列出了查看挂起消息部分的十六进制表示形式时应遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="1f45f-104">This topic lists steps that can be followed to view the hexadecimal representation of the parts of a suspended message.</span></span>  
  
## <a name="use-the-message-details-dialog-box-to-view-message-parts"></a><span data-ttu-id="1f45f-105">使用“消息详细信息”对话框查看消息部分</span><span class="sxs-lookup"><span data-stu-id="1f45f-105">Use the Message Details dialog box to view message parts</span></span>  
 <span data-ttu-id="1f45f-106">请遵循以下这些步骤查看消息部分的十六进制表示形式：</span><span class="sxs-lookup"><span data-stu-id="1f45f-106">Follow these steps to view the hexadecimal representation of message parts:</span></span>  
  
1.  <span data-ttu-id="1f45f-107">使用**查询**在 BizTalk 管理控制台中返回的结果集与一个或多个挂起的消息的选项卡。</span><span class="sxs-lookup"><span data-stu-id="1f45f-107">Use the **Query** tab in the BizTalk Administration Console to return a result set with one or more suspended messages.</span></span> <span data-ttu-id="1f45f-108">请参阅[如何搜索消息](../core/how-to-search-for-messages.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="1f45f-108">See [How to Search for Messages](../core/how-to-search-for-messages.md) for more information.</span></span>  
  
2.  <span data-ttu-id="1f45f-109">双击你想要进行调查以显示该挂起的消息**消息详细信息**消息的对话框。</span><span class="sxs-lookup"><span data-stu-id="1f45f-109">Double-click the suspended message that you want to investigate to display the **Message Details** dialog box for the message.</span></span>  
  
3.  <span data-ttu-id="1f45f-110">单击左侧窗格中的消息部分**消息详细信息**对话框以显示消息部分。</span><span class="sxs-lookup"><span data-stu-id="1f45f-110">Click a message part in the left hand pane of the **Message Details** dialog box to display the message part.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f45f-111">消息可能没有或者有一个或多个消息部分。</span><span class="sxs-lookup"><span data-stu-id="1f45f-111">Messages may have 0, 1 or many message parts.</span></span> <span data-ttu-id="1f45f-112">大部分消息通常只有一个消息部分，称作“正文”。</span><span class="sxs-lookup"><span data-stu-id="1f45f-112">Most often messages have single message part that is called "body".</span></span>  
  
4.  <span data-ttu-id="1f45f-113">单击**二进制**的右窗格中的选项卡**消息详细信息**对话框中显示的十六进制表示形式的消息部分。</span><span class="sxs-lookup"><span data-stu-id="1f45f-113">Click the **Binary** tab in the right hand pane of the **Message Details** dialog box to display the hexadecimal representation of the message part.</span></span>  
  
5.  <span data-ttu-id="1f45f-114">检查消息部分中字符的十六进制表示形式的以下各项：</span><span class="sxs-lookup"><span data-stu-id="1f45f-114">Check the hexadecimal representation of characters in message parts for the following:</span></span>  
  
    -   <span data-ttu-id="1f45f-115">缺少字节顺序标记或字节顺序标记无效。</span><span class="sxs-lookup"><span data-stu-id="1f45f-115">Missing or invalid byte order mark.</span></span> <span data-ttu-id="1f45f-116">有关字节顺序标记请参阅[http://go.microsoft.com/fwlink/?LinkId=196380](http://go.microsoft.com/fwlink/?LinkId=196380)。</span><span class="sxs-lookup"><span data-stu-id="1f45f-116">For more information about byte order marks see [http://go.microsoft.com/fwlink/?LinkId=196380](http://go.microsoft.com/fwlink/?LinkId=196380).</span></span>  
  
    -   <span data-ttu-id="1f45f-117">Unix 和 Windows 中的换行符编码不同。</span><span class="sxs-lookup"><span data-stu-id="1f45f-117">Differences between the encoding of linebreaks in Unix and Windows.</span></span> <span data-ttu-id="1f45f-118">Unix 使用十六进制换行符 (0A) 指示换行，而 Windows 使用十六进制回车符 (0D) 和换行符 (0A) 一起指示换行。</span><span class="sxs-lookup"><span data-stu-id="1f45f-118">Unix uses hex linefeed (0A) to indicate a line break where Windows uses both hex carriage return (0D) and linefeed (0A) to indicate a line break.</span></span>  
  
    -   <span data-ttu-id="1f45f-119">消息部分中有无效控制字符。</span><span class="sxs-lookup"><span data-stu-id="1f45f-119">Invalid control character(s) in message parts.</span></span> <span data-ttu-id="1f45f-120">消息部分中在文本视图下不显示的控制字符在二进制视图中可能可见。</span><span class="sxs-lookup"><span data-stu-id="1f45f-120">Control characters in message parts that do not show up in the text view may be visible in the binary view.</span></span>  
  
    -   <span data-ttu-id="1f45f-121">消息部分中的无效空字符会导致消息部分截断。</span><span class="sxs-lookup"><span data-stu-id="1f45f-121">Invalid nul character(s) in the middle of a message part can cause the message part to be truncated.</span></span> <span data-ttu-id="1f45f-122">空字符表示为十六进制值 (00)。</span><span class="sxs-lookup"><span data-stu-id="1f45f-122">The nul character is represented as hex (00).</span></span>  
  
    -   <span data-ttu-id="1f45f-123">位置平面文件中的无效字符偏移量。</span><span class="sxs-lookup"><span data-stu-id="1f45f-123">Invalid character offset in positional flat files.</span></span> <span data-ttu-id="1f45f-124">显示消息部分的十六进制表示形式，以查看位置平面文件中的数据偏移量。</span><span class="sxs-lookup"><span data-stu-id="1f45f-124">Display the hexadecimal representation of a message part to view the offset of data in a positional flat file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f45f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f45f-125">See Also</span></span>  
 [<span data-ttu-id="1f45f-126">调查业务流程、 端口和消息失败</span><span class="sxs-lookup"><span data-stu-id="1f45f-126">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)