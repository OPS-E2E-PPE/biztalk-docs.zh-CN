---
title: RNIFReceive | Microsoft Docs
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
ms.openlocfilehash: b2c949f87f74881da64475c74c6e26099359f925
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282250"
---
# <a name="rnifreceive"></a><span data-ttu-id="9af98-102">RNIFReceive</span><span class="sxs-lookup"><span data-stu-id="9af98-102">RNIFReceive</span></span>
<span data-ttu-id="9af98-103">此示例提供了一个有效的 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx 文件接收 RNIF 消息，并使其准备好以供处理[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]公用流程。</span><span class="sxs-lookup"><span data-stu-id="9af98-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx file that receives an RNIF message, and prepares it for processing by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] public process.</span></span> <span data-ttu-id="9af98-104">可以自定义 ASPX 页后，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9af98-104">You can customize the ASPX page to do the following:</span></span>  
  
- <span data-ttu-id="9af98-105">添加或删除性能计数器</span><span class="sxs-lookup"><span data-stu-id="9af98-105">Add or remove performance counters</span></span>  
  
- <span data-ttu-id="9af98-106">将功能添加到页上，如向数据库写入数据或自定义跟踪功能</span><span class="sxs-lookup"><span data-stu-id="9af98-106">Add functionality to the page, such as writing data to a database or customizing tracking functionality</span></span>  
  
- <span data-ttu-id="9af98-107">向页面添加验证</span><span class="sxs-lookup"><span data-stu-id="9af98-107">Add validation to the page</span></span>  
  
  <span data-ttu-id="9af98-108">此示例位于 *\<驱动器\>* : \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\WebApplication\RNIFReceiver。</span><span class="sxs-lookup"><span data-stu-id="9af98-108">This sample is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\WebApplication\RNIFReceiver.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="9af98-109">演示</span><span class="sxs-lookup"><span data-stu-id="9af98-109">Demonstrates</span></span>  
 <span data-ttu-id="9af98-110">此示例演示如何准备传入消息的公用流程，其中包括：</span><span class="sxs-lookup"><span data-stu-id="9af98-110">This sample demonstrates how to prepare incoming messages for the public process, including the following:</span></span>  
  
-   <span data-ttu-id="9af98-111">从合作伙伴的 RNIFSend.aspx 接收消息</span><span class="sxs-lookup"><span data-stu-id="9af98-111">Receiving the message from the partner's RNIFSend.aspx</span></span>  
  
-   <span data-ttu-id="9af98-112">验证 MIME 头</span><span class="sxs-lookup"><span data-stu-id="9af98-112">Validating the MIME header</span></span>  
  
-   <span data-ttu-id="9af98-113">从消息中删除 MIME 头和边界</span><span class="sxs-lookup"><span data-stu-id="9af98-113">Removing the MIME header and boundaries from the message</span></span>  
  
-   <span data-ttu-id="9af98-114">将消息路由到合作伙伴的 RNIFReceive.aspx</span><span class="sxs-lookup"><span data-stu-id="9af98-114">Routing the message to the partner's RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="9af98-115">返回信号消息</span><span class="sxs-lookup"><span data-stu-id="9af98-115">Returning a signal message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9af98-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9af98-116">See Also</span></span>  
 <span data-ttu-id="9af98-117">[发送和接收 ASPX 页](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span><span class="sxs-lookup"><span data-stu-id="9af98-117">[Send and Receive ASPX Pages](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span></span>  
 [<span data-ttu-id="9af98-118">Web 应用程序示例</span><span class="sxs-lookup"><span data-stu-id="9af98-118">Web Application Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)