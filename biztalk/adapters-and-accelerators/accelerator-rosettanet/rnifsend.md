---
title: "RNIFSend |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 780f7446-56c5-40bf-95e2-25d0cff12f12
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1762c30d6524a777a862492701ff0b8a8731a68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="rnifsend"></a><span data-ttu-id="ca7be-102">RNIFSend</span><span class="sxs-lookup"><span data-stu-id="ca7be-102">RNIFSend</span></span>
<span data-ttu-id="ca7be-103">此示例提供可实际应用的 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx 文件，该文件准备供 RNIF 处理的消息，并将该消息发送到响应方的 RNIFReceive.aspx 页。</span><span class="sxs-lookup"><span data-stu-id="ca7be-103">This sample provides a working [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx file that prepares a message for RNIF processing, and sends the message to the RNIFReceive.aspx page at the responder.</span></span> <span data-ttu-id="ca7be-104">你可以通过自定义 ASPX 页来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ca7be-104">You can customize the ASPX page to do the following:</span></span>  
  
-   <span data-ttu-id="ca7be-105">添加或删除性能计数器</span><span class="sxs-lookup"><span data-stu-id="ca7be-105">Add or remove performance counters</span></span>  
  
-   <span data-ttu-id="ca7be-106">向该页添加功能，例如，将数据写入数据库或自定义跟踪功能</span><span class="sxs-lookup"><span data-stu-id="ca7be-106">Add functionality to the page, such as writing data to a database or customizing tracking functionality</span></span>  
  
-   <span data-ttu-id="ca7be-107">向该页添加验证功能</span><span class="sxs-lookup"><span data-stu-id="ca7be-107">Add validation to the page</span></span>  
  
 <span data-ttu-id="ca7be-108">此示例位于*\<驱动器 >*: files\microsoft BizTalk\<版本 > RosettaNet\SDK\WebApplication\RNIFSender 快捷键。</span><span class="sxs-lookup"><span data-stu-id="ca7be-108">This sample is located in *\<drive>*:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\WebApplication\RNIFSender.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ca7be-109">演示</span><span class="sxs-lookup"><span data-stu-id="ca7be-109">Demonstrates</span></span>  
 <span data-ttu-id="ca7be-110">此示例演示如何准备供 RNIF 处理的传出消息，包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="ca7be-110">This sample demonstrates how to prepare outgoing messages for RNIF processing, including the following:</span></span>  
  
-   <span data-ttu-id="ca7be-111">验证 MIME 头的数据</span><span class="sxs-lookup"><span data-stu-id="ca7be-111">Validating the data for the MIME header</span></span>  
  
-   <span data-ttu-id="ca7be-112">向消息中添加 MIME 头和 MIME 边界</span><span class="sxs-lookup"><span data-stu-id="ca7be-112">Adding a MIME header and MIME boundaries to the message</span></span>  
  
-   <span data-ttu-id="ca7be-113">将消息发送到合作伙伴的 RNIFReceive.aspx</span><span class="sxs-lookup"><span data-stu-id="ca7be-113">Sending the message to the partner's RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="ca7be-114">处理返回的信号消息</span><span class="sxs-lookup"><span data-stu-id="ca7be-114">Processing a returned signal message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca7be-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca7be-115">See Also</span></span>  
 <span data-ttu-id="ca7be-116">[发送和接收 ASPX 页](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span><span class="sxs-lookup"><span data-stu-id="ca7be-116">[Send and Receive ASPX Pages](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span></span>  
 [<span data-ttu-id="ca7be-117">Web 应用程序示例</span><span class="sxs-lookup"><span data-stu-id="ca7be-117">Web Application Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)