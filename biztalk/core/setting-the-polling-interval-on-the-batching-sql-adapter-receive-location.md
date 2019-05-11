---
title: 轮询间隔设置上的批处理 SQL 适配器接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- polling interval [receive adapters]
- SQL adapters, polling interval
- receive locations, polling interval
- SQL adapters, receive locations
- receive locations, SQL adapters
ms.assetid: 9053b20d-145a-4445-b414-c0482cf975a0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c71bd431670d7a46721f626765e76f21c3882f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393231"
---
# <a name="setting-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a><span data-ttu-id="b0e78-102">轮询间隔设置上的批处理 SQL 适配器接收位置</span><span class="sxs-lookup"><span data-stu-id="b0e78-102">Setting the Polling Interval on the Batching SQL Adapter Receive Location</span></span>
<span data-ttu-id="b0e78-103">你可以设置轮询间隔对批处理 SQL 适配器接收位置 (**BatchControlMessageRecvLoc**) 开发和生产计算机上以不同的方式。</span><span class="sxs-lookup"><span data-stu-id="b0e78-103">You can set the polling interval on the batching SQL adapter receive location (**BatchControlMessageRecvLoc**) differently on development and production computers.</span></span> <span data-ttu-id="b0e78-104">在开发服务器上，Microsoft 建议您将轮询间隔保留 30 秒，以便快速激活批处理业务流程为协议的默认值。</span><span class="sxs-lookup"><span data-stu-id="b0e78-104">On a development server, Microsoft recommends that you keep the polling interval at the default of 30 seconds, for quick activation of the batching orchestration for an agreement.</span></span> <span data-ttu-id="b0e78-105">但是，在生产服务器上，设置为 30 秒可能会影响性能。</span><span class="sxs-lookup"><span data-stu-id="b0e78-105">However, on a production server, a setting of 30 seconds may affect performance.</span></span> <span data-ttu-id="b0e78-106">后已激活批处理，你可能想要将轮询间隔设置为更高的值，比如五分钟。</span><span class="sxs-lookup"><span data-stu-id="b0e78-106">Once you have activated a batch, you may want to set the polling interval to a higher value, such as five minutes.</span></span>  
  
 <span data-ttu-id="b0e78-107">有关参与方的详细信息，请参阅[管理参与方](../core/managing-parties.md)。</span><span class="sxs-lookup"><span data-stu-id="b0e78-107">For more information about parties, see [Managing Parties](../core/managing-parties.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b0e78-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="b0e78-108">Prerequisites</span></span>  
 <span data-ttu-id="b0e78-109">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="b0e78-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-set-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a><span data-ttu-id="b0e78-110">若要在批处理 SQL 适配器接收位置设置轮询间隔</span><span class="sxs-lookup"><span data-stu-id="b0e78-110">To set the Polling Interval on the Batching SQL Adapter Receive Location</span></span>  
  
1. <span data-ttu-id="b0e78-111">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk EDI 应用程序**，然后单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="b0e78-111">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **BizTalk EDI Application**, and then click **Receive Locations**.</span></span> <span data-ttu-id="b0e78-112">右键单击**BatchControlMessageRecvLoc**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="b0e78-112">Right-click **BatchControlMessageRecvLoc**, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="b0e78-113">在中**接收位置属性**对话框中**传输**部分中，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b0e78-113">In the **Receive Location Properties** dialog box, in the **Transport** section, click **Configure**.</span></span>  
  
3. <span data-ttu-id="b0e78-114">在中**SQL 传输属性**对话框中，将更改为值**轮询间隔**从"30"为所需值的默认值。</span><span class="sxs-lookup"><span data-stu-id="b0e78-114">In the **SQL Transport Properties** dialog box, change the value for **Polling Interval** from the default value of "30" to the desired value.</span></span> <span data-ttu-id="b0e78-115">在生产服务器的建议的值为"5"。</span><span class="sxs-lookup"><span data-stu-id="b0e78-115">The recommended value for a production server is "5".</span></span>  
  
4. <span data-ttu-id="b0e78-116">更改的值**轮询度量单位**默认值为**秒**到**分钟**。</span><span class="sxs-lookup"><span data-stu-id="b0e78-116">Change the value of **Polling Unit of Measure** from the default value of **Seconds** to **Minutes**.</span></span>  
  
5. <span data-ttu-id="b0e78-117">单击**确定**，然后单击**确定**再次</span><span class="sxs-lookup"><span data-stu-id="b0e78-117">Click **OK**, and then click **OK** again</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e78-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0e78-118">See Also</span></span>  
 [<span data-ttu-id="b0e78-119">管理 EDI 和 AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="b0e78-119">Managing EDI and AS2 Solutions</span></span>](../core/managing-edi-and-as2-solutions.md)