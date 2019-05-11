---
title: RNIFSend | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 780f7446-56c5-40bf-95e2-25d0cff12f12
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92ad9b7c0318a028b6b2f98a75eca1484014b305
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282236"
---
# <a name="rnifsend"></a><span data-ttu-id="8d490-102">RNIFSend</span><span class="sxs-lookup"><span data-stu-id="8d490-102">RNIFSend</span></span>
<span data-ttu-id="8d490-103">此示例提供了一个有效的 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx 文件准备供 RNIF 处理的消息并将消息发送到响应方的 RNIFReceive.aspx 页。</span><span class="sxs-lookup"><span data-stu-id="8d490-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx file that prepares a message for RNIF processing, and sends the message to the RNIFReceive.aspx page at the responder.</span></span> <span data-ttu-id="8d490-104">可以自定义 ASPX 页后，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8d490-104">You can customize the ASPX page to do the following:</span></span>  
  
- <span data-ttu-id="8d490-105">添加或删除性能计数器</span><span class="sxs-lookup"><span data-stu-id="8d490-105">Add or remove performance counters</span></span>  
  
- <span data-ttu-id="8d490-106">将功能添加到页上，如向数据库写入数据或自定义跟踪功能</span><span class="sxs-lookup"><span data-stu-id="8d490-106">Add functionality to the page, such as writing data to a database or customizing tracking functionality</span></span>  
  
- <span data-ttu-id="8d490-107">向页面添加验证</span><span class="sxs-lookup"><span data-stu-id="8d490-107">Add validation to the page</span></span>  
  
  <span data-ttu-id="8d490-108">此示例位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\WebApplication\RNIFSender。</span><span class="sxs-lookup"><span data-stu-id="8d490-108">This sample is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\WebApplication\RNIFSender.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="8d490-109">演示</span><span class="sxs-lookup"><span data-stu-id="8d490-109">Demonstrates</span></span>  
 <span data-ttu-id="8d490-110">此示例演示如何准备供 RNIF 处理，包括以下传出消息：</span><span class="sxs-lookup"><span data-stu-id="8d490-110">This sample demonstrates how to prepare outgoing messages for RNIF processing, including the following:</span></span>  
  
-   <span data-ttu-id="8d490-111">验证 MIME 标头的数据</span><span class="sxs-lookup"><span data-stu-id="8d490-111">Validating the data for the MIME header</span></span>  
  
-   <span data-ttu-id="8d490-112">将 MIME 头和 MIME 边界添加到消息</span><span class="sxs-lookup"><span data-stu-id="8d490-112">Adding a MIME header and MIME boundaries to the message</span></span>  
  
-   <span data-ttu-id="8d490-113">将消息发送到合作伙伴的 RNIFReceive.aspx</span><span class="sxs-lookup"><span data-stu-id="8d490-113">Sending the message to the partner's RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="8d490-114">处理返回的信号消息</span><span class="sxs-lookup"><span data-stu-id="8d490-114">Processing a returned signal message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d490-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d490-115">See Also</span></span>  
 <span data-ttu-id="8d490-116">[发送和接收 ASPX 页](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span><span class="sxs-lookup"><span data-stu-id="8d490-116">[Send and Receive ASPX Pages](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span></span>  
 [<span data-ttu-id="8d490-117">Web 应用程序示例</span><span class="sxs-lookup"><span data-stu-id="8d490-117">Web Application Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)