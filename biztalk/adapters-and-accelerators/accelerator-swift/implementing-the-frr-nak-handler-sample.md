---
title: 实现 FRR NAK 处理程序示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fa5fb7-6864-4923-b641-e76d2b95d923
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42885d6c487c6f088bfab113891ec5425d3fc82e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990278"
---
# <a name="implementing-the-frr-nak-handler-sample"></a><span data-ttu-id="606b1-102">实现 FRR NAK 处理程序示例</span><span class="sxs-lookup"><span data-stu-id="606b1-102">Implementing the FRR NAK Handler Sample</span></span>
<span data-ttu-id="606b1-103">若要实现示例 FRR NAK 自定义处理程序、 将示例项目添加到你的解决方案、 生成和部署项目、 绑定和启动业务流程，然后停止并重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="606b1-103">To implement the sample FRR NAK custom handler, add the sample project to your solution, build and deploy the project, bind and start the orchestration, and then stop and restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  

### <a name="to-implement-the-frr-nak-custom-handler"></a><span data-ttu-id="606b1-104">若要实现 FRR NAK 自定义处理程序</span><span class="sxs-lookup"><span data-stu-id="606b1-104">To implement the FRR NAK Custom Handler</span></span>  

1. <span data-ttu-id="606b1-105">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，打开你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="606b1-105">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], open your solution.</span></span> <span data-ttu-id="606b1-106">在解决方案资源管理器中右键单击解决方案，指向**外**，然后单击**现有项目**。</span><span class="sxs-lookup"><span data-stu-id="606b1-106">In Solution Explorer, right-click the solution, point to **Add**, and then click **Existing Project**.</span></span>  

2. <span data-ttu-id="606b1-107">在中**添加现有项目**对话框中，转到*\<驱动器\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Samples\FrrHandler。</span><span class="sxs-lookup"><span data-stu-id="606b1-107">In the **Add Existing Project** dialog box, move to *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Samples\FrrHandler.</span></span> <span data-ttu-id="606b1-108">选择**RepairSWIFTRejectedMessage.btproj**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="606b1-108">Select **RepairSWIFTRejectedMessage.btproj**, and then click **Open**.</span></span>  

3. <span data-ttu-id="606b1-109">生成密钥并将该密钥分配到项目。</span><span class="sxs-lookup"><span data-stu-id="606b1-109">Generate a key and assign the key to the project.</span></span>  

4. <span data-ttu-id="606b1-110">生成和部署 RepairSWIFTRejectedMessage.btproj 项目。</span><span class="sxs-lookup"><span data-stu-id="606b1-110">Build and deploy the RepairSWIFTRejectedMessage.btproj project.</span></span>  

5. <span data-ttu-id="606b1-111">在 BizTalk 浏览器中，展开**BizTalk 配置数据库**，  **\<*服务器名称*\>，BizTalkMgmtDb.dbo**，和**业务流程**，右键单击**RepairSWIFTRejectedMessage.Orchestration_1**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="606b1-111">In BizTalk Explorer, expand **BizTalk Configuration Databases**, **\<*server name*\>,BizTalkMgmtDb.dbo**, and **Orchestrations**, right-click **RepairSWIFTRejectedMessage.Orchestration_1**, and then click **Bind**.</span></span>  

6. <span data-ttu-id="606b1-112">在中**端口绑定属性**对话框中，选择您的主机，如 BizTalkServerApplication，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="606b1-112">In the **Port Binding Properties** dialog box, select your host, such as BizTalkServerApplication, and then click **OK**.</span></span>  

7. <span data-ttu-id="606b1-113">在 BizTalk 浏览器中右键单击**RepairSWIFTRejectedMessage.Orchestration_1**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="606b1-113">In BizTalk Explorer, right-click **RepairSWIFTRejectedMessage.Orchestration_1**, and then click **Start**.</span></span>  

8. <span data-ttu-id="606b1-114">在中**快速启动**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="606b1-114">In the **Express Start** dialog box, click **OK**.</span></span>  

9. <span data-ttu-id="606b1-115">单击 **“启动”**，再单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="606b1-115">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="606b1-116">输入**services.msc**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="606b1-116">Enter **services.msc**, and then click **OK**.</span></span> <span data-ttu-id="606b1-117">右键单击**BizTalk 服务**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="606b1-117">Right-click **BizTalk Service**, and then click **Restart**.</span></span>
