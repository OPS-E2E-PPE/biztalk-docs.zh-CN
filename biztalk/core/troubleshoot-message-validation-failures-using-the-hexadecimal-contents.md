---
title: 通过查看挂起的消息的十六进制内容来解决消息验证失败 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf14cd9-2d4b-43a3-9738-52bfd879e1e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 562caf377691e8bfcea5d05bba307e28859d7999
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243119"
---
# <a name="troubleshooting-message-validation-failures-by-viewing-the-hexadecimal-contents-of-suspended-messages"></a><span data-ttu-id="f3428-102">通过查看挂起的消息的十六进制内容来解决消息验证失败</span><span class="sxs-lookup"><span data-stu-id="f3428-102">Troubleshooting Message Validation Failures by Viewing the Hexadecimal Contents of Suspended Messages</span></span>
<span data-ttu-id="f3428-103">如果消息由于验证失败而挂起，可能会有助于查看来确定验证失败的原因的消息部分的十六进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="f3428-103">If a message is suspended due to validation failures, it may be helpful to view the hexadecimal representation of the message parts to determine the cause of the validation failure.</span></span> <span data-ttu-id="f3428-104">本主题列出了可后接若要查看的十六进制表示形式的挂起的消息部分的步骤。</span><span class="sxs-lookup"><span data-stu-id="f3428-104">This topic lists steps that can be followed to view the hexadecimal representation of the parts of a suspended message.</span></span>  
  
## <a name="use-the-message-details-dialog-box-to-view-message-parts"></a><span data-ttu-id="f3428-105">使用消息详细信息对话框中查看消息部分</span><span class="sxs-lookup"><span data-stu-id="f3428-105">Use the Message Details dialog box to view message parts</span></span>  
 <span data-ttu-id="f3428-106">请按照下列步骤查看消息部分的十六进制表示形式：</span><span class="sxs-lookup"><span data-stu-id="f3428-106">Follow these steps to view the hexadecimal representation of message parts:</span></span>  
  
1.  <span data-ttu-id="f3428-107">使用**查询**在 BizTalk 管理控制台中返回的结果集与一个或多个挂起的消息的选项卡。</span><span class="sxs-lookup"><span data-stu-id="f3428-107">Use the **Query** tab in the BizTalk Administration Console to return a result set with one or more suspended messages.</span></span> <span data-ttu-id="f3428-108">请参阅[如何搜索消息](../core/how-to-search-for-messages.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="f3428-108">See [How to Search for Messages](../core/how-to-search-for-messages.md) for more information.</span></span>  
  
2.  <span data-ttu-id="f3428-109">双击你想要进行调查以显示对挂起的消息**消息的详细信息**消息对话框。</span><span class="sxs-lookup"><span data-stu-id="f3428-109">Double-click the suspended message that you want to investigate to display the **Message Details** dialog box for the message.</span></span>  
  
3.  <span data-ttu-id="f3428-110">单击左侧窗格中的消息部分**消息的详细信息**对话框以显示消息部分。</span><span class="sxs-lookup"><span data-stu-id="f3428-110">Click a message part in the left hand pane of the **Message Details** dialog box to display the message part.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f3428-111">消息可能具有 0、 1 或多个消息部分。</span><span class="sxs-lookup"><span data-stu-id="f3428-111">Messages may have 0, 1 or many message parts.</span></span> <span data-ttu-id="f3428-112">大部分消息通常只有一个消息部分，称作"正文"。</span><span class="sxs-lookup"><span data-stu-id="f3428-112">Most often messages have single message part that is called "body".</span></span>  
  
4.  <span data-ttu-id="f3428-113">单击**二进制**的右窗格中的选项卡**消息的详细信息**对话框以显示消息部分的十六进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="f3428-113">Click the **Binary** tab in the right hand pane of the **Message Details** dialog box to display the hexadecimal representation of the message part.</span></span>  
  
5.  <span data-ttu-id="f3428-114">检查以下的消息部分中的字符的十六进制表示形式：</span><span class="sxs-lookup"><span data-stu-id="f3428-114">Check the hexadecimal representation of characters in message parts for the following:</span></span>  
  
    -   <span data-ttu-id="f3428-115">缺失或无效字节顺序标记。</span><span class="sxs-lookup"><span data-stu-id="f3428-115">Missing or invalid byte order mark.</span></span> <span data-ttu-id="f3428-116">有关字节顺序标记请参阅[ http://go.microsoft.com/fwlink/?LinkId=196380 ](http://go.microsoft.com/fwlink/?LinkId=196380)。</span><span class="sxs-lookup"><span data-stu-id="f3428-116">For more information about byte order marks see [http://go.microsoft.com/fwlink/?LinkId=196380](http://go.microsoft.com/fwlink/?LinkId=196380).</span></span>  
  
    -   <span data-ttu-id="f3428-117">Unix 和 Windows 中的换行符编码之间的差异。</span><span class="sxs-lookup"><span data-stu-id="f3428-117">Differences between the encoding of linebreaks in Unix and Windows.</span></span> <span data-ttu-id="f3428-118">Unix 使用十六进制换行符 (0A) 指示换行，Windows 使用十六进制回车符 (0d) 和换行符 (0A) 指示换行。</span><span class="sxs-lookup"><span data-stu-id="f3428-118">Unix uses hex linefeed (0A) to indicate a line break where Windows uses both hex carriage return (0D) and linefeed (0A) to indicate a line break.</span></span>  
  
    -   <span data-ttu-id="f3428-119">消息部分中有无效控制字符。</span><span class="sxs-lookup"><span data-stu-id="f3428-119">Invalid control character(s) in message parts.</span></span> <span data-ttu-id="f3428-120">不显示在文本视图中的消息部分中的控制字符可能会看到在二进制视图中。</span><span class="sxs-lookup"><span data-stu-id="f3428-120">Control characters in message parts that do not show up in the text view may be visible in the binary view.</span></span>  
  
    -   <span data-ttu-id="f3428-121">无效空字符消息部分可能会导致消息部分被截断。</span><span class="sxs-lookup"><span data-stu-id="f3428-121">Invalid nul character(s) in the middle of a message part can cause the message part to be truncated.</span></span> <span data-ttu-id="f3428-122">空字符表示为十六进制值 (00)。</span><span class="sxs-lookup"><span data-stu-id="f3428-122">The nul character is represented as hex (00).</span></span>  
  
    -   <span data-ttu-id="f3428-123">无效的字符偏移量位置平面文件中。</span><span class="sxs-lookup"><span data-stu-id="f3428-123">Invalid character offset in positional flat files.</span></span> <span data-ttu-id="f3428-124">显示消息部分，若要查看位置平面文件中的数据的偏移量的十六进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="f3428-124">Display the hexadecimal representation of a message part to view the offset of data in a positional flat file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3428-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3428-125">See Also</span></span>  
 [<span data-ttu-id="f3428-126">调查业务流程、端口和消息失败</span><span class="sxs-lookup"><span data-stu-id="f3428-126">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)