---
title: 设置 ASPX 页的连接超时 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ASPX pages, connection time-out
- connections, time-out
ms.assetid: 61d9c996-caf4-48bd-bda7-52f2797a941b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d28867e323a3fb7c3b50ab787b31b19c32c36e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281836"
---
# <a name="setting-the-connection-time-out-for-an-aspx-page"></a><span data-ttu-id="3b0e9-102">设置 ASPX 页的连接超时值</span><span class="sxs-lookup"><span data-stu-id="3b0e9-102">Setting the Connection Time-Out for an ASPX Page</span></span>
<span data-ttu-id="3b0e9-103">当您使用用于同步消息的 ASPX 页时，必须增加 ASPX 页的连接超时值，以便它可以等待预期的消息。</span><span class="sxs-lookup"><span data-stu-id="3b0e9-103">When you use an ASPX page for synchronous messages, you must increase the connection time-out for the ASPX page so that it can wait for the expected message.</span></span>  
  
 <span data-ttu-id="3b0e9-104">增加连接超时的 ASPX 页中可以有意外的结果。</span><span class="sxs-lookup"><span data-stu-id="3b0e9-104">Increasing the connection time-out for the ASPX page can have unintended consequences.</span></span> <span data-ttu-id="3b0e9-105">首先，它提高了拒绝服务攻击的风险和耗尽线程池的威胁。</span><span class="sxs-lookup"><span data-stu-id="3b0e9-105">First, it increases the risk of a denial-of-service attack and the threat of exhausting the thread pool.</span></span> <span data-ttu-id="3b0e9-106">其次，如果有太多 ASPX 页上的同步连接，系统可能会锁定。</span><span class="sxs-lookup"><span data-stu-id="3b0e9-106">Second, if there are too many synchronous connections on the ASPX page, the system can lock up.</span></span> <span data-ttu-id="3b0e9-107">因此，您必须增加连接超时值，而是小心以免增加的太多。</span><span class="sxs-lookup"><span data-stu-id="3b0e9-107">Therefore, while you must increase the connection time-out, be careful not to increase it too much.</span></span>  
  
 <span data-ttu-id="3b0e9-108">将连接超时值设置为 RosettaNet 组织所允许的最小。</span><span class="sxs-lookup"><span data-stu-id="3b0e9-108">Set the connection time-out to the minimum allowed by the RosettaNet organization.</span></span> <span data-ttu-id="3b0e9-109">有关详细信息的计时参数的合作伙伴接口流程 (PIP)，请参阅表 4-3:消息交换的控制，RosettaNet PIP 规范中。</span><span class="sxs-lookup"><span data-stu-id="3b0e9-109">For more information about the timing parameters for a Partner Interface Process (PIP), see Table 4-3: Message Exchange Controls, in the RosettaNet PIP Specification.</span></span>  
  
### <a name="to-set-the-connection-time-out-for-the-aspx-page"></a><span data-ttu-id="3b0e9-110">设置 ASPX 页的连接超时值</span><span class="sxs-lookup"><span data-stu-id="3b0e9-110">To set the connection time-out for the ASPX page</span></span>  
  
1.  <span data-ttu-id="3b0e9-111">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="3b0e9-111">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="3b0e9-112">在 IIS 管理器中，展开本地计算机的节点，然后展开**网站**。</span><span class="sxs-lookup"><span data-stu-id="3b0e9-112">In IIS Manager, expand the node for the local computer, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="3b0e9-113">右键单击 **“默认的 Web 站点”**，然后单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="3b0e9-113">Right-click **Default Web Site**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="3b0e9-114">在默认网站属性对话框中上,**网站**选项卡上，在**连接超时**框中键入适当的值，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3b0e9-114">In the Default Web Site Properties dialog box, on the **Web Site** tab, in the **Connection Timeout** box, type an appropriate value, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b0e9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b0e9-115">See Also</span></span>  
 [<span data-ttu-id="3b0e9-116">编程指南</span><span class="sxs-lookup"><span data-stu-id="3b0e9-116">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)