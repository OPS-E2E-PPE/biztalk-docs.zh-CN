---
title: 连接超时值设置为 ASPX 页面 |Microsoft 文档
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
ms.openlocfilehash: 83e083b9f2f0262095e58b4ed9842627888773dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207189"
---
# <a name="setting-the-connection-time-out-for-an-aspx-page"></a><span data-ttu-id="09213-102">ASPX 页设置连接超时</span><span class="sxs-lookup"><span data-stu-id="09213-102">Setting the Connection Time-Out for an ASPX Page</span></span>
<span data-ttu-id="09213-103">将 ASPX 页用于同步消息时，必须增加 ASPX 页的连接超时值，以便 ASPX 页可以等待所需的消息。</span><span class="sxs-lookup"><span data-stu-id="09213-103">When you use an ASPX page for synchronous messages, you must increase the connection time-out for the ASPX page so that it can wait for the expected message.</span></span>  
  
 <span data-ttu-id="09213-104">增加 ASPX 页的连接超时值可能会引起意外后果。</span><span class="sxs-lookup"><span data-stu-id="09213-104">Increasing the connection time-out for the ASPX page can have unintended consequences.</span></span> <span data-ttu-id="09213-105">第一，这样做增加了遭受拒绝服务攻击和耗尽线程池的风险。</span><span class="sxs-lookup"><span data-stu-id="09213-105">First, it increases the risk of a denial-of-service attack and the threat of exhausting the thread pool.</span></span> <span data-ttu-id="09213-106">第二，如果 ASPX 页上有太多的同步连接，系统可能会锁定。</span><span class="sxs-lookup"><span data-stu-id="09213-106">Second, if there are too many synchronous connections on the ASPX page, the system can lock up.</span></span> <span data-ttu-id="09213-107">因此，当您必须增加连接超时值时，请注意不要增加的太多。</span><span class="sxs-lookup"><span data-stu-id="09213-107">Therefore, while you must increase the connection time-out, be careful not to increase it too much.</span></span>  
  
 <span data-ttu-id="09213-108">将连接超时值设置为 RosettaNet 组织所允许的最小值。</span><span class="sxs-lookup"><span data-stu-id="09213-108">Set the connection time-out to the minimum allowed by the RosettaNet organization.</span></span> <span data-ttu-id="09213-109">有关详细信息的计时参数为合作伙伴接口过程 (PIP)，请参阅表 4-3: RosettaNet PIP 规范中的消息交换控件。</span><span class="sxs-lookup"><span data-stu-id="09213-109">For more information about the timing parameters for a Partner Interface Process (PIP), see Table 4-3: Message Exchange Controls, in the RosettaNet PIP Specification.</span></span>  
  
### <a name="to-set-the-connection-time-out-for-the-aspx-page"></a><span data-ttu-id="09213-110">设置 ASPX 页的连接超时</span><span class="sxs-lookup"><span data-stu-id="09213-110">To set the connection time-out for the ASPX page</span></span>  
  
1.  <span data-ttu-id="09213-111">单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="09213-111">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="09213-112">在 IIS 管理器中，展开本地计算机，节点，然后展开**网站**。</span><span class="sxs-lookup"><span data-stu-id="09213-112">In IIS Manager, expand the node for the local computer, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="09213-113">右键单击 **“默认的 Web 站点”**，然后单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="09213-113">Right-click **Default Web Site**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="09213-114">在默认 Web 站点属性对话框中，在**网站**选项卡上，在**连接超时**框中，键入适当的值，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="09213-114">In the Default Web Site Properties dialog box, on the **Web Site** tab, in the **Connection Timeout** box, type an appropriate value, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09213-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09213-115">See Also</span></span>  
 [<span data-ttu-id="09213-116">编程指南</span><span class="sxs-lookup"><span data-stu-id="09213-116">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)