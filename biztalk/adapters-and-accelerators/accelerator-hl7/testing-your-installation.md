---
title: 测试安装 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing installation
- installing, testing installation
ms.assetid: db27a75c-db7f-46ff-b8ef-2624ff18dcc8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7fc94930ba5ff0851114e36d728ee7f3ffb73ab
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961059"
---
# <a name="testing-your-installation"></a><span data-ttu-id="3b79c-102">测试安装</span><span class="sxs-lookup"><span data-stu-id="3b79c-102">Testing Your Installation</span></span>
<span data-ttu-id="3b79c-103">你可以将设置你[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]测试通过手动运行完成端到端教程或执行端到端教程程序的安装。</span><span class="sxs-lookup"><span data-stu-id="3b79c-103">You can set up your [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] installation for testing either by manually running through the end-to-end tutorial or by executing the end-to-end tutorial program.</span></span> <span data-ttu-id="3b79c-104">若要执行程序，可单击**启动教程**按钮在安装过程中或在 C:\Program Files\Microsoft BizTalk 中执行 EndToEndTutorial.exe\<版本\>HL7\SDK\ 快捷键端到端教程 （后运行安装和配置） 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3b79c-104">To exercise the program, either click the **Launch Tutorial** button during setup or execute EndToEndTutorial.exe in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder (after running installation and configuration).</span></span> <span data-ttu-id="3b79c-105">这两种自动操作将执行相同的安装步骤通过运行完成教程将会手动执行。</span><span class="sxs-lookup"><span data-stu-id="3b79c-105">Either of these automated actions will perform the same setup steps that you would manually perform by running through the tutorial.</span></span> <span data-ttu-id="3b79c-106">端到端教程程序执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="3b79c-106">The end-to-end tutorial program does the following:</span></span>  
  
-   <span data-ttu-id="3b79c-107">部署 MSH 和 ACK 架构</span><span class="sxs-lookup"><span data-stu-id="3b79c-107">Deploys MSH and ACK schemas</span></span>  
  
-   <span data-ttu-id="3b79c-108">部署版本 2.3.1 通用架构</span><span class="sxs-lookup"><span data-stu-id="3b79c-108">Deploys Version 2.3.1 common schemas</span></span>  
  
-   <span data-ttu-id="3b79c-109">部署 ADT 架构</span><span class="sxs-lookup"><span data-stu-id="3b79c-109">Deploys ADT schemas</span></span>  
  
-   <span data-ttu-id="3b79c-110">创建 Tutorial_1WayReceive 接收端口</span><span class="sxs-lookup"><span data-stu-id="3b79c-110">Creates the Tutorial_1WayReceive receive port</span></span>  
  
-   <span data-ttu-id="3b79c-111">创建 Tutorial_MLLPReceive 接收位置</span><span class="sxs-lookup"><span data-stu-id="3b79c-111">Creates the Tutorial_MLLPReceive receive location</span></span>  
  
-   <span data-ttu-id="3b79c-112">创建 Tutorial_BTAHL7PickUp 接收端口</span><span class="sxs-lookup"><span data-stu-id="3b79c-112">Creates the Tutorial_BTAHL7PickUp receive port</span></span>  
  
-   <span data-ttu-id="3b79c-113">创建 Tutorial_FileReceiveLoc 接收位置</span><span class="sxs-lookup"><span data-stu-id="3b79c-113">Creates the Tutorial_FileReceiveLoc receive location</span></span>  
  
-   <span data-ttu-id="3b79c-114">创建 Tutorial_sendAck_ADT 发送端口</span><span class="sxs-lookup"><span data-stu-id="3b79c-114">Creates the Tutorial_sendAck_ADT send port</span></span>  
  
-   <span data-ttu-id="3b79c-115">创建 Tutorial_sendMsg_RX 发送端口</span><span class="sxs-lookup"><span data-stu-id="3b79c-115">Creates the Tutorial_sendMsg_RX send port</span></span>  
  
-   <span data-ttu-id="3b79c-116">创建 Tutorial_BTAHL7Drop 发送端口</span><span class="sxs-lookup"><span data-stu-id="3b79c-116">Creates the Tutorial_BTAHL7Drop send port</span></span>  
  
-   <span data-ttu-id="3b79c-117">创建 Tutorial_MLLPSend 发送端口</span><span class="sxs-lookup"><span data-stu-id="3b79c-117">Creates the Tutorial_MLLPSend send port</span></span>  
  
-   <span data-ttu-id="3b79c-118">创建 Tutorial_ADTSystem 方</span><span class="sxs-lookup"><span data-stu-id="3b79c-118">Creates the Tutorial_ADTSystem party</span></span>  
  
-   <span data-ttu-id="3b79c-119">创建 Tutorial_RXSystem 方</span><span class="sxs-lookup"><span data-stu-id="3b79c-119">Creates the Tutorial_RXSystem party</span></span>  
  
-   <span data-ttu-id="3b79c-120">创建 Tutorial_HISystem 方</span><span class="sxs-lookup"><span data-stu-id="3b79c-120">Creates the Tutorial_HISystem party</span></span>  
  
-   <span data-ttu-id="3b79c-121">重新启动 BizTalk 服务</span><span class="sxs-lookup"><span data-stu-id="3b79c-121">Restarts the BizTalk Service</span></span>  
  
 <span data-ttu-id="3b79c-122">如果已执行端到端教程程序，则可以为 HL7 预定义的文件夹中删除的测试实例。</span><span class="sxs-lookup"><span data-stu-id="3b79c-122">If you have executed the end-to-end tutorial program, you can drop a test instance for HL7 in a pre-defined folder.</span></span> <span data-ttu-id="3b79c-123">接收管道与该文件夹关联选取该消息并处理它。</span><span class="sxs-lookup"><span data-stu-id="3b79c-123">The receive pipeline associated with the folder picks up the message and processes it.</span></span> <span data-ttu-id="3b79c-124">根据筛选器，发送管道将文档路由到目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="3b79c-124">Based on filters, a send pipeline routes the document to the destination folder.</span></span> <span data-ttu-id="3b79c-125">此简单的"往返"练习的基本构建基块[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 引擎，并确认你的安装。</span><span class="sxs-lookup"><span data-stu-id="3b79c-125">This simple "round-trip" exercises the basic building blocks of the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) engine and confirms your installation.</span></span>  
  
### <a name="to-test-your-installation"></a><span data-ttu-id="3b79c-126">若要测试你的安装</span><span class="sxs-lookup"><span data-stu-id="3b79c-126">To test your installation</span></span>  
  
1.  <span data-ttu-id="3b79c-127">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到\<*驱动器*\>: files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\End 端到端教程文件夹。</span><span class="sxs-lookup"><span data-stu-id="3b79c-127">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder.</span></span>  
  
2.  <span data-ttu-id="3b79c-128">右键单击**TutorialSampleInstance.txt**文件，，然后单击**复制**。</span><span class="sxs-lookup"><span data-stu-id="3b79c-128">Right-click the **TutorialSampleInstance.txt** file, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="3b79c-129">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_ 快捷键BTAHL7PickUp 文件夹。</span><span class="sxs-lookup"><span data-stu-id="3b79c-129">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp folder.</span></span>  
  
4.  <span data-ttu-id="3b79c-130">右键单击文件夹，并依次**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="3b79c-130">Right-click the folder, and then click **Paste**.</span></span>  
  
5.  <span data-ttu-id="3b79c-131">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_ 快捷键BTAHL7Drop 文件夹。</span><span class="sxs-lookup"><span data-stu-id="3b79c-131">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop folder.</span></span>  
  
     <span data-ttu-id="3b79c-132">你可以验证你的安装是否成功，如果已处理的实例出现在**Tutorial_BTAHL7Drop**文件夹作为\< *Guid*\>.txt。</span><span class="sxs-lookup"><span data-stu-id="3b79c-132">You can verify if your installation was successful if the processed instance appears in the **Tutorial_BTAHL7Drop** folder as \<*Guid*\>.txt.</span></span>  
  
 <span data-ttu-id="3b79c-133">继续执行下一步，[准备使用本教程](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)。</span><span class="sxs-lookup"><span data-stu-id="3b79c-133">Proceed to the next step, [Preparing to Use the Tutorial](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md).</span></span>