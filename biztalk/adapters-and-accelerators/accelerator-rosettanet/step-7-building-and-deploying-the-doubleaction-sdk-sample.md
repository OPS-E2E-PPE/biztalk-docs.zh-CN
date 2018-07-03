---
title: 步骤 7： 生成和部署 DoubleAction SDK 示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- deploying, solutions
- building solutions
- double action tutorial, deploying solutions
ms.assetid: f67f8aee-1004-48ee-a6fd-881097382888
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c4664210cf4911f180b44b470db01aa2948531f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998670"
---
# <a name="step-7-building-and-deploying-the-doubleaction-sdk-sample"></a><span data-ttu-id="10728-102">步骤 7： 生成和部署 DoubleAction SDK 示例</span><span class="sxs-lookup"><span data-stu-id="10728-102">Step 7: Building and Deploying the DoubleAction SDK Sample</span></span>
<span data-ttu-id="10728-103">DoubleAction.odx 示例显示了如何实现业务流程，以自动为双操作合作伙伴接口流程 (PIP) 0C2、0C4、3A2 和 3A4 生成响应。</span><span class="sxs-lookup"><span data-stu-id="10728-103">The DoubleAction.odx sample shows how to implement an orchestration to generate responses automatically for the double-action Partner Interface Processes (PIPs) 0C2, 0C4, 3A2, and 3A4.</span></span> <span data-ttu-id="10728-104">你可将此示例项目扩展为支持其他双操作 PIP。</span><span class="sxs-lookup"><span data-stu-id="10728-104">You can extend this sample project to support additional double-action PIPs.</span></span>  
  
 <span data-ttu-id="10728-105">只要 Fabrikam 使用这四种 PIP 中的任意一种发出请求，此示例都可自动向 Fabrikam 发送响应。</span><span class="sxs-lookup"><span data-stu-id="10728-105">You use this sample to send a response automatically to Fabrikam whenever Fabrikam makes a request using any one of the four PIPs.</span></span>  
  
### <a name="to-build-and-initialize-the-doubleaction-sample"></a><span data-ttu-id="10728-106">生成和初始化 DoubleAction 示例</span><span class="sxs-lookup"><span data-stu-id="10728-106">To build and initialize the DoubleAction sample</span></span>  
  
1. <span data-ttu-id="10728-107">在 Contoso 计算机的命令提示符窗口中，转到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="10728-107">On the Contoso computer, in a command prompt window, move to the following folder:</span></span>   
   <span data-ttu-id="10728-108">*\<驱动器\>*: \Program Files\\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction\\。</span><span class="sxs-lookup"><span data-stu-id="10728-108">*\<drive\>*:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction\\.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="10728-109">在运行安装程序之前，用记事本打开 DoubleAction.sql 文件（位于上述文件夹中）。</span><span class="sxs-lookup"><span data-stu-id="10728-109">Before running the Setup program, open the DoubleAction.sql file (in the above folder) in Notepad.</span></span> <span data-ttu-id="10728-110">上**文件**菜单上，单击**另存为**。</span><span class="sxs-lookup"><span data-stu-id="10728-110">On the **File** menu, click **Save As**.</span></span> <span data-ttu-id="10728-111">在中**编码**框中，选择**ANSI**从下拉列表中，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="10728-111">In the **Encoding** box, select **ANSI** from the drop-down list, and then click **Save**.</span></span> <span data-ttu-id="10728-112">单击**是**以覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="10728-112">Click **Yes** to overwrite the existing file.</span></span>  
  
2. <span data-ttu-id="10728-113">如果您的 BizTalk Server 安装在 SQL Server 2008 R2/2008 SP1 上运行，请在同一文件夹中运行 setupx64.bat。</span><span class="sxs-lookup"><span data-stu-id="10728-113">If your BizTalk Server installation is running on SQL Server 2008 R2/2008 SP1, run setupx64.bat in the same folder.</span></span> <span data-ttu-id="10728-114">该批处理文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="10728-114">The batch file will perform the following actions:</span></span>  
  
   - <span data-ttu-id="10728-115">在 BTARNDATA 数据库中创建一个 SQL 存储过程 (`PipAutomationGetAction`)，用于从 MessagesToLOB 表中检索操作消息。</span><span class="sxs-lookup"><span data-stu-id="10728-115">Creates a SQL stored procedure (`PipAutomationGetAction`) in the BTARNDATA database to retrieve the action message from the MessagesToLOB table.</span></span>  
  
   - <span data-ttu-id="10728-116">编译 HeaderHelper .NET 项目，并在全局程序集缓存中注册此程序集。</span><span class="sxs-lookup"><span data-stu-id="10728-116">Compiles the HeaderHelper .NET project and registers the assembly in the global assembly cache.</span></span>  
  
   - <span data-ttu-id="10728-117">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SQL 接收端口 (MessagesToLOB_Receive_Port)。</span><span class="sxs-lookup"><span data-stu-id="10728-117">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SQL receive port (MessagesToLOB_Receive_Port).</span></span>  
  
   - <span data-ttu-id="10728-118">启用接收位置 (MessagesToLOB_Receive_Location)。</span><span class="sxs-lookup"><span data-stu-id="10728-118">Enables the receive location (MessagesToLOB_Receive_Location).</span></span>  
  
   - <span data-ttu-id="10728-119">编译并部署双操作 PIPAutomation 业务流程 (DoubleAction.odx)。</span><span class="sxs-lookup"><span data-stu-id="10728-119">Compiles and deploys the double-action PIPAutomation orchestration (DoubleAction.odx).</span></span>  
  
   - <span data-ttu-id="10728-120">绑定并启动 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 业务流程。</span><span class="sxs-lookup"><span data-stu-id="10728-120">Binds and starts the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="10728-121">编译时示例将显示一些警告。</span><span class="sxs-lookup"><span data-stu-id="10728-121">The sample displays some warnings while compiling.</span></span> <span data-ttu-id="10728-122">你可以忽略这些警告。</span><span class="sxs-lookup"><span data-stu-id="10728-122">You can ignore these warnings.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="10728-123">验证 DoubleAction.odx 已绑定到**MessagesToLOB_Receive_Port**，并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="10728-123">Verify that DoubleAction.odx has been bound to **MessagesToLOB_Receive_Port**, and that the orchestration has been started.</span></span>  
  
3. <span data-ttu-id="10728-124">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，**应用程序**，并**BizTalk Application 1**节点。</span><span class="sxs-lookup"><span data-stu-id="10728-124">In BizTalk Server Administration Console, expand the **BizTalk Group**, **Applications**, and **BizTalk Application 1** nodes.</span></span> <span data-ttu-id="10728-125">单击**业务流程**节点。</span><span class="sxs-lookup"><span data-stu-id="10728-125">Click the **Orchestrations** node.</span></span> <span data-ttu-id="10728-126">右键单击**DoubleAction**业务流程，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="10728-126">Right-click the **DoubleAction** orchestration, and then click **Properties**.</span></span> <span data-ttu-id="10728-127">在属性对话框中，单击**绑定**节点，然后设置**主机**到**BizTalkServerApplication**并设置**接收端口**到**MessageToLOB_ReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="10728-127">In the Properties dialog box, click the **Bindings** node, and then set the **Host** to **BizTalkServerApplication** and set the **Receive Port** to **MessageToLOB_ReceivePort**.</span></span> <span data-ttu-id="10728-128">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="10728-128">Click **OK**.</span></span> <span data-ttu-id="10728-129">右键单击**DoubleAction**业务流程，并单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="10728-129">Right-click the **DoubleAction** orchestration, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10728-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="10728-130">See Also</span></span>  
 [<span data-ttu-id="10728-131">创建和配置 Fabrikam 解决方案</span><span class="sxs-lookup"><span data-stu-id="10728-131">Creating and Configuring the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)