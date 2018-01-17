---
title: "实现 FRR 否认处理程序示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80fa5fb7-6864-4923-b641-e76d2b95d923
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a91c0303c9abdf6b1d8c434869445f3c84348935
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="implementing-the-frr-nak-handler-sample"></a><span data-ttu-id="0deb0-102">实现 FRR 否认处理程序示例</span><span class="sxs-lookup"><span data-stu-id="0deb0-102">Implementing the FRR NAK Handler Sample</span></span>
<span data-ttu-id="0deb0-103">若要实现示例 FRR 否认自定义处理程序，将示例项目添加到你的解决方案、 生成和部署项目、 绑定和启动业务流程，然后停止并重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0deb0-103">To implement the sample FRR NAK custom handler, add the sample project to your solution, build and deploy the project, bind and start the orchestration, and then stop and restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
### <a name="to-implement-the-frr-nak-custom-handler"></a><span data-ttu-id="0deb0-104">若要实现 FRR 否认自定义处理程序</span><span class="sxs-lookup"><span data-stu-id="0deb0-104">To implement the FRR NAK Custom Handler</span></span>  
  
1.  <span data-ttu-id="0deb0-105">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，打开你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="0deb0-105">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], open your solution.</span></span> <span data-ttu-id="0deb0-106">在解决方案资源管理器，右键单击该解决方案，指向**添加**，然后单击**现有项目**。</span><span class="sxs-lookup"><span data-stu-id="0deb0-106">In Solution Explorer, right-click the solution, point to **Add**, and then click **Existing Project**.</span></span>  
  
2.  <span data-ttu-id="0deb0-107">在**添加现有项目**对话框中，移动到*\<驱动器\>*: files\microsoft BizTalk Accelerator for SWIFT\SDK\Samples\FrrHandler。</span><span class="sxs-lookup"><span data-stu-id="0deb0-107">In the **Add Existing Project** dialog box, move to *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Samples\FrrHandler.</span></span> <span data-ttu-id="0deb0-108">选择**RepairSWIFTRejectedMessage.btproj**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="0deb0-108">Select **RepairSWIFTRejectedMessage.btproj**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="0deb0-109">生成密钥并将密钥分配到项目。</span><span class="sxs-lookup"><span data-stu-id="0deb0-109">Generate a key and assign the key to the project.</span></span>  
  
4.  <span data-ttu-id="0deb0-110">生成和部署 RepairSWIFTRejectedMessage.btproj 项目。</span><span class="sxs-lookup"><span data-stu-id="0deb0-110">Build and deploy the RepairSWIFTRejectedMessage.btproj project.</span></span>  
  
5.  <span data-ttu-id="0deb0-111">在 BizTalk 资源管理器中，展开**BizTalk 配置数据库**，  **\<*服务器名称*\>，BizTalkMgmtDb.dbo**，和**业务流程**，右键单击**RepairSWIFTRejectedMessage.Orchestration_1**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="0deb0-111">In BizTalk Explorer, expand **BizTalk Configuration Databases**, **\<*server name*\>,BizTalkMgmtDb.dbo**, and **Orchestrations**, right-click **RepairSWIFTRejectedMessage.Orchestration_1**, and then click **Bind**.</span></span>  
  
6.  <span data-ttu-id="0deb0-112">在**端口绑定属性**对话框中，选择你的主机，如 BizTalkServerApplication，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0deb0-112">In the **Port Binding Properties** dialog box, select your host, such as BizTalkServerApplication, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="0deb0-113">在 BizTalk 资源管理器中，右键单击**RepairSWIFTRejectedMessage.Orchestration_1**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="0deb0-113">In BizTalk Explorer, right-click **RepairSWIFTRejectedMessage.Orchestration_1**, and then click **Start**.</span></span>  
  
8.  <span data-ttu-id="0deb0-114">在**Express 启动**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0deb0-114">In the **Express Start** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="0deb0-115">单击 **“启动”**，再单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="0deb0-115">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="0deb0-116">输入**services.msc**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0deb0-116">Enter **services.msc**, and then click **OK**.</span></span> <span data-ttu-id="0deb0-117">右键单击**BizTalk 服务**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="0deb0-117">Right-click **BizTalk Service**, and then click **Restart**.</span></span>