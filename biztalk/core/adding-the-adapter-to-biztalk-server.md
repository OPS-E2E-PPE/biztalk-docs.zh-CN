---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: e464a792ab13d1b05b9c4d2ee9cc46ed15b1a55b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360831"
---
# <a name="adding-the-adapter-to-biztalk-server"></a><span data-ttu-id="ed1ee-101">将适配器添加到 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ed1ee-101">Adding the Adapter to BizTalk Server</span></span>
<span data-ttu-id="ed1ee-102">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器包含接收处理程序和发送处理程序文件夹。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-102">Microsoft BizTalk Adapter for JD Edwards OneWorld contains both the Receive Handler and Send Handler folders.</span></span> <span data-ttu-id="ed1ee-103">发送处理程序文件夹包含 BizTalkServerApplication。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-103">The Send Handler folder contains BizTalkServerApplication.</span></span> <span data-ttu-id="ed1ee-104">用于 JD Edwards OneWorld 的 BizTalk 适配器是可创建对象;在进程中运行它与 BizTalk Server 运行，而不在独立的主机进程中。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-104">BizTalk Adapter for JD Edwards OneWorld is creatable; it runs in-process with BizTalk Server and does not run in an isolated host process.</span></span>  
  
 <span data-ttu-id="ed1ee-105">使用以下过程将适配器添加到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-105">Use the following procedure to add the adapter to BizTalk Server.</span></span>  
  
### <a name="to-add-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="ed1ee-106">若要添加用于 JD Edwards OneWorld 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="ed1ee-106">To add BizTalk Adapter for JD Edwards OneWorld</span></span>  
  
1. <span data-ttu-id="ed1ee-107">上**启动**菜单，依次指向**Program Files**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-107">On the **Start** menu, point to **Program Files**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration** to start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
2. <span data-ttu-id="ed1ee-108">展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**平台设置**。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-108">Expand **BizTalk Server Administration**, expand **BizTalk Group**, and then expand **Platform Settings**.</span></span>  
  
3. <span data-ttu-id="ed1ee-109">右键单击**适配器**，依次指向**新建**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-109">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
4. <span data-ttu-id="ed1ee-110">在中**适配器属性**对话框中，键入适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-110">In the **Adapter Properties** dialog box, type a name for the adapter.</span></span> <span data-ttu-id="ed1ee-111">例如，JDEdwards。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-111">For example, JDEdwards.</span></span>  
  
5. <span data-ttu-id="ed1ee-112">选择**JDEOneWorld**从**适配器**列表，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-112">Select **JDEOneWorld** from the **Adapter** list, and then click **OK**.</span></span>  
  
## <a name="verifying-the-adapter"></a><span data-ttu-id="ed1ee-113">验证适配器</span><span class="sxs-lookup"><span data-stu-id="ed1ee-113">Verifying the Adapter</span></span>  
 <span data-ttu-id="ed1ee-114">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你可以验证适配器工作正常，通过查看**逻辑系统**窗口。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-114">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, you can verify that the adapter is functioning correctly by looking at the **Logical System** window.</span></span> <span data-ttu-id="ed1ee-115">在初始安装时，此窗口为空，因为尚未建立与服务器系统的连接也没有建立任何逻辑系统。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-115">On initial installation, this window is empty because you have not yet established a connection to the server system, nor have you created any logical systems.</span></span>  
  
#### <a name="to-verify-that-the-adapter-is-running-correctly"></a><span data-ttu-id="ed1ee-116">若要验证适配器正常运行</span><span class="sxs-lookup"><span data-stu-id="ed1ee-116">To verify that the adapter is running correctly</span></span>  
  
1. <span data-ttu-id="ed1ee-117">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开**平台设置**，展开**适配器**，然后选择**JDEOneWorld**。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-117">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand **Platform Settings**, expand **Adapters**, and then select **JDEOneWorld**.</span></span>  
  
2. <span data-ttu-id="ed1ee-118">在细节窗格中，右键单击**BizTalkServerApplication**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-118">In the details pane, right-click **BizTalkServerApplication**, and select **Properties**.</span></span>  
  
3. <span data-ttu-id="ed1ee-119">单击 **“属性”** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-119">Click the **Properties** tab.</span></span>  
  
4. <span data-ttu-id="ed1ee-120">设置 SQL 连接参数。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-120">Set the SQL Connection parameters.</span></span>  
  
   -   <span data-ttu-id="ed1ee-121">**定义 SQL 数据库参数-** SQL Server 名称和数据库都是在安装时设置。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-121">**Define SQL Database Parameters -** The SQL Server Name and Database are those you set at installation.</span></span> <span data-ttu-id="ed1ee-122">这是您可以重新定义的服务器和数据库的此适配器的文本区域。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-122">This is the text area that you can redefine the server and database for this adapter.</span></span>  
  
5. <span data-ttu-id="ed1ee-123">单击**关闭**退出**逻辑系统**窗口。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-123">Click **Close** to exit the **Logical System** window.</span></span>  
  
    <span data-ttu-id="ed1ee-124">下一步是添加逻辑系统使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ed1ee-124">Your next step is to add a logical system using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed1ee-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed1ee-125">See Also</span></span>  
 <span data-ttu-id="ed1ee-126">[规划和体系结构](../core/planning-and-architecture17.md) </span><span class="sxs-lookup"><span data-stu-id="ed1ee-126">[Planning and Architecture](../core/planning-and-architecture17.md) </span></span>  
 <span data-ttu-id="ed1ee-127">[用于 JD Edwards OneWorld 的 BizTalk 适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="ed1ee-127">[Security in BizTalk Adapter for JD Edwards OneWorld](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="ed1ee-128">添加用于 JD Edwards OneWorld 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="ed1ee-128">Adding BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)