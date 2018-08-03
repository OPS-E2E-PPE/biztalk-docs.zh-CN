---
title: RNIFReceive |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf1253b0-ceca-4e7a-91ed-3837bd904472
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d54b66c42fae286ec748ef560c461a22124165b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991766"
---
# <a name="rnifreceive"></a><span data-ttu-id="ca6ca-102">RNIFReceive</span><span class="sxs-lookup"><span data-stu-id="ca6ca-102">RNIFReceive</span></span>
<span data-ttu-id="ca6ca-103">此示例提供了一个有效的 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx 文件接收 RNIF 消息，并使其准备好以供处理[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]公用流程。</span><span class="sxs-lookup"><span data-stu-id="ca6ca-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx file that receives an RNIF message, and prepares it for processing by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] public process.</span></span> <span data-ttu-id="ca6ca-104">你可以通过自定义 ASPX 页来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ca6ca-104">You can customize the ASPX page to do the following:</span></span>  
  
- <span data-ttu-id="ca6ca-105">添加或删除性能计数器</span><span class="sxs-lookup"><span data-stu-id="ca6ca-105">Add or remove performance counters</span></span>  
  
- <span data-ttu-id="ca6ca-106">向该页添加功能，例如，将数据写入数据库或自定义跟踪功能</span><span class="sxs-lookup"><span data-stu-id="ca6ca-106">Add functionality to the page, such as writing data to a database or customizing tracking functionality</span></span>  
  
- <span data-ttu-id="ca6ca-107">向该页添加验证功能</span><span class="sxs-lookup"><span data-stu-id="ca6ca-107">Add validation to the page</span></span>  
  
  <span data-ttu-id="ca6ca-108">此示例位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\WebApplication\RNIFReceiver。</span><span class="sxs-lookup"><span data-stu-id="ca6ca-108">This sample is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\WebApplication\RNIFReceiver.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ca6ca-109">演示</span><span class="sxs-lookup"><span data-stu-id="ca6ca-109">Demonstrates</span></span>  
 <span data-ttu-id="ca6ca-110">此示例演示如何为公用流程准备传入消息，演示内容包括以下几个操作：</span><span class="sxs-lookup"><span data-stu-id="ca6ca-110">This sample demonstrates how to prepare incoming messages for the public process, including the following:</span></span>  
  
-   <span data-ttu-id="ca6ca-111">从合作伙伴的 RNIFSend.aspx 接收消息</span><span class="sxs-lookup"><span data-stu-id="ca6ca-111">Receiving the message from the partner's RNIFSend.aspx</span></span>  
  
-   <span data-ttu-id="ca6ca-112">验证 MIME 头</span><span class="sxs-lookup"><span data-stu-id="ca6ca-112">Validating the MIME header</span></span>  
  
-   <span data-ttu-id="ca6ca-113">从消息中删除 MIME 头和边界</span><span class="sxs-lookup"><span data-stu-id="ca6ca-113">Removing the MIME header and boundaries from the message</span></span>  
  
-   <span data-ttu-id="ca6ca-114">将消息路由到合作伙伴的 RNIFReceive.aspx</span><span class="sxs-lookup"><span data-stu-id="ca6ca-114">Routing the message to the partner's RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="ca6ca-115">返回信号消息</span><span class="sxs-lookup"><span data-stu-id="ca6ca-115">Returning a signal message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca6ca-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca6ca-116">See Also</span></span>  
 <span data-ttu-id="ca6ca-117">[发送和接收 ASPX 页](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span><span class="sxs-lookup"><span data-stu-id="ca6ca-117">[Send and Receive ASPX Pages](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span></span>  
 [<span data-ttu-id="ca6ca-118">Web 应用程序示例</span><span class="sxs-lookup"><span data-stu-id="ca6ca-118">Web Application Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)