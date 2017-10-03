---
title: "将适配器添加到 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters [JD Edwards OneWorld adapters], installing
- installing, JD Edwards OneWorld adapters
- JD Edwards OneWorld adapters, installing
ms.assetid: e2018856-1943-48e9-b43f-7d527880e4bd
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63de8824112c9891c6d67eee424a84dd4968976c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-the-adapter-to-biztalk-server"></a><span data-ttu-id="381f9-102">将适配器添加到 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="381f9-102">Adding the Adapter to BizTalk Server</span></span>
<span data-ttu-id="381f9-103">适用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器包含“接收处理程序”文件夹和“发送处理程序”文件夹。</span><span class="sxs-lookup"><span data-stu-id="381f9-103">Microsoft BizTalk Adapter for JD Edwards OneWorld contains both the Receive Handler and Send Handler folders.</span></span> <span data-ttu-id="381f9-104">“发送处理程序”文件夹包含 BizTalkServerApplication。</span><span class="sxs-lookup"><span data-stu-id="381f9-104">The Send Handler folder contains BizTalkServerApplication.</span></span> <span data-ttu-id="381f9-105">适用于 JD Edwards OneWorld 的 BizTalk 适配器是可以创建的，它在与 BizTalk 服务器相关的进程中运行，而不在隔离的主机进程中运行。</span><span class="sxs-lookup"><span data-stu-id="381f9-105">BizTalk Adapter for JD Edwards OneWorld is creatable; it runs in-process with BizTalk Server and does not run in an isolated host process.</span></span>  
  
 <span data-ttu-id="381f9-106">您可以使用以下过程将适配器添加到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="381f9-106">Use the following procedure to add the adapter to BizTalk Server.</span></span>  
  
### <a name="to-add-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="381f9-107">要添加适用于 JD Edwards OneWorld 的 BizTalk 适配器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="381f9-107">To add BizTalk Adapter for JD Edwards OneWorld</span></span>  
  
1.  <span data-ttu-id="381f9-108">上**启动**菜单上，指向**Program Files**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="381f9-108">On the **Start** menu, point to **Program Files**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration** to start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
2.  <span data-ttu-id="381f9-109">展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**平台设置**。</span><span class="sxs-lookup"><span data-stu-id="381f9-109">Expand **BizTalk Server Administration**, expand **BizTalk Group**, and then expand **Platform Settings**.</span></span>  
  
3.  <span data-ttu-id="381f9-110">右键单击**适配器**，指向**新建**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="381f9-110">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
4.  <span data-ttu-id="381f9-111">在**适配器属性**对话框中，键入的适配器名称。</span><span class="sxs-lookup"><span data-stu-id="381f9-111">In the **Adapter Properties** dialog box, type a name for the adapter.</span></span> <span data-ttu-id="381f9-112">例如，JDEdwards。</span><span class="sxs-lookup"><span data-stu-id="381f9-112">For example, JDEdwards.</span></span>  
  
5.  <span data-ttu-id="381f9-113">选择**JDEOneWorld**从**适配器**列表，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="381f9-113">Select **JDEOneWorld** from the **Adapter** list, and then click **OK**.</span></span>  
  
## <a name="verifying-the-adapter"></a><span data-ttu-id="381f9-114">验证适配器</span><span class="sxs-lookup"><span data-stu-id="381f9-114">Verifying the Adapter</span></span>  
 <span data-ttu-id="381f9-115">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你可以验证适配器是否正确运作，可以通过查看**逻辑系统**窗口。</span><span class="sxs-lookup"><span data-stu-id="381f9-115">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, you can verify that the adapter is functioning correctly by looking at the **Logical System** window.</span></span> <span data-ttu-id="381f9-116">在初始安装时，该窗口为空，因为您还没有建立到服务器系统的连接，也没有建立任何逻辑系统。</span><span class="sxs-lookup"><span data-stu-id="381f9-116">On initial installation, this window is empty because you have not yet established a connection to the server system, nor have you created any logical systems.</span></span>  
  
#### <a name="to-verify-that-the-adapter-is-running-correctly"></a><span data-ttu-id="381f9-117">若要验证该适配器正确运行，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="381f9-117">To verify that the adapter is running correctly</span></span>  
  
1.  <span data-ttu-id="381f9-118">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开**平台设置**，展开**适配器**，然后选择**JDEOneWorld**。</span><span class="sxs-lookup"><span data-stu-id="381f9-118">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand **Platform Settings**, expand **Adapters**, and then select **JDEOneWorld**.</span></span>  
  
2.  <span data-ttu-id="381f9-119">在细节窗格中，右键单击**BizTalkServerApplication**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="381f9-119">In the details pane, right-click **BizTalkServerApplication**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="381f9-120">单击 **“属性”** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="381f9-120">Click the **Properties** tab.</span></span>  
  
4.  <span data-ttu-id="381f9-121">设置 SQL 连接参数。</span><span class="sxs-lookup"><span data-stu-id="381f9-121">Set the SQL Connection parameters.</span></span>  
  
    -   <span data-ttu-id="381f9-122">**定义 SQL 数据库参数-**的 SQL Server 名称和数据库是那些在安装设置。</span><span class="sxs-lookup"><span data-stu-id="381f9-122">**Define SQL Database Parameters -** The SQL Server Name and Database are those you set at installation.</span></span> <span data-ttu-id="381f9-123">在这个文本区域，您可以重新定义适用于该适配器的服务器和数据库。</span><span class="sxs-lookup"><span data-stu-id="381f9-123">This is the text area that you can redefine the server and database for this adapter.</span></span>  
  
5.  <span data-ttu-id="381f9-124">单击**关闭**退出**逻辑系统**窗口。</span><span class="sxs-lookup"><span data-stu-id="381f9-124">Click **Close** to exit the **Logical System** window.</span></span>  
  
     <span data-ttu-id="381f9-125">下一步是使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 添加逻辑系统。</span><span class="sxs-lookup"><span data-stu-id="381f9-125">Your next step is to add a logical system using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="381f9-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="381f9-126">See Also</span></span>  
 <span data-ttu-id="381f9-127">[规划和体系结构](../core/planning-and-architecture17.md) </span><span class="sxs-lookup"><span data-stu-id="381f9-127">[Planning and Architecture](../core/planning-and-architecture17.md) </span></span>  
 <span data-ttu-id="381f9-128">[用于博士 Edwards OneWorld 的 BizTalk Adapter 中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="381f9-128">[Security in BizTalk Adapter for JD Edwards OneWorld](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="381f9-129">为博士 Edwards OneWorld 添加 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="381f9-129">Adding BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)