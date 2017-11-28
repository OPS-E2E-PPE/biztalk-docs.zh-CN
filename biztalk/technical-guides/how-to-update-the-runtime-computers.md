---
title: "如何更新运行时计算机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 576a7065-04b6-436c-acf9-28c8d6e40107
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0fc6423a8918237362636f26322b145a0cbcf26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-runtime-computers"></a><span data-ttu-id="5cd3c-102">如何更新运行时计算机</span><span class="sxs-lookup"><span data-stu-id="5cd3c-102">How to Update the Runtime Computers</span></span>
<span data-ttu-id="5cd3c-103">目标系统[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用配置运行时计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置向导在生产环境中运行的生产 BizTalk 组的一部分。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-103">The destination system [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers are configured with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Wizard as part of the production BizTalk group running in the production environment.</span></span> <span data-ttu-id="5cd3c-104">在灾难恢复环境中还原生产 BizTalk 组时，必须在每个更新设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机，因此它指向灾难恢复[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例时它尝试连接到已还原生产 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-104">When the production BizTalk group is restored in the disaster recovery environment, settings must be updated on each [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computer so that it points to the disaster recovery [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s) when it attempts to connect to the restored production BizTalk group.</span></span> <span data-ttu-id="5cd3c-105">在目标系统中还原的 BizTalk 组后，使用以下过程更新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-105">After the BizTalk group is restored in the destination system, use the following procedure to update the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers.</span></span>  
  
### <a name="to-update-the-biztalk-server-runtime-computers"></a><span data-ttu-id="5cd3c-106">若要更新 BizTalk Server 运行时计算机</span><span class="sxs-lookup"><span data-stu-id="5cd3c-106">To update the BizTalk Server runtime computers</span></span>  
  
1.  <span data-ttu-id="5cd3c-107">将编辑的 SampleUpdateInfo.xml 文件复制到 files\microsoft [!INCLUDE[prague](../includes/prague-md.md)]\Schema\Restore 目录在每个 32 位 BizTalk 服务器上或者为 \Program Files (x86) \Microsoft[!INCLUDE[prague](../includes/prague-md.md)]上每个 64 位的 \Bins32\Schema\Restore 目录在目标系统中的 BizTalk server。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-107">Copy the edited SampleUpdateInfo.xml file to the \Program Files\Microsoft [!INCLUDE[prague](../includes/prague-md.md)]\Schema\Restore directory on every 32 bit BizTalk server or to the \Program Files (x86)\Microsoft [!INCLUDE[prague](../includes/prague-md.md)]\Bins32\Schema\Restore directory on every 64 bit BizTalk server in the destination system.</span></span>  
  
2.  <span data-ttu-id="5cd3c-108">在每个 BizTalk 服务器上，打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-108">On each BizTalk server, open a command prompt.</span></span> <span data-ttu-id="5cd3c-109">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-109">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5cd3c-110">在 64 位计算机上必须打开 64 位命令提示符。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-110">On 64-bit computers, you must open a 64-bit command prompt.</span></span>  
  
3.  <span data-ttu-id="5cd3c-111">在命令提示符处，导航到 files\microsoft [!INCLUDE[prague](../includes/prague-md.md)]（在 32 位计算机） 上的 \Schema\Restore 或 \Program Files (x86) \Microsoft [!INCLUDE[prague](../includes/prague-md.md)]\Bins32\Schema\Restore （在 64 位计算机） 上的，键入此命令：</span><span class="sxs-lookup"><span data-stu-id="5cd3c-111">At the command-prompt, navigate to \Program Files\Microsoft [!INCLUDE[prague](../includes/prague-md.md)]\Schema\Restore (on 32 bit computers) or to \Program Files (x86)\Microsoft [!INCLUDE[prague](../includes/prague-md.md)]\Bins32\Schema\Restore (on 64 bit computers) and type this command:</span></span>  
  
    ```  
    cscript UpdateRegistry.vbs SampleUpdateInfo.xml  
    ```  
  
4.  <span data-ttu-id="5cd3c-112">启用并在目标系统中重新启动所有 BizTalk 主机实例和 BizTalk 服务器上的所有其他 BizTalk 服务。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-112">Enable and restart all BizTalk Host instances and all other BizTalk Services on the BizTalk servers in the destination system.</span></span>  
  
5.  <span data-ttu-id="5cd3c-113">在目标系统中每个 BizTalk 服务器上重新启动 WMI。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-113">Restart WMI on each BizTalk server in the destination system.</span></span> <span data-ttu-id="5cd3c-114">单击**启动**，单击**运行**，类型**services.msc**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-114">Click **Start**, click **Run**, type **services.msc**, and then click **OK**.</span></span> <span data-ttu-id="5cd3c-115">在**服务**MMC 管理单元中，右键单击**Windows Management Instrumentation**和选择**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-115">In the **Services** MMC snap-in, right-click **Windows Management Instrumentation** and select **Restart**.</span></span>  
  
6.  <span data-ttu-id="5cd3c-116">每个 BizTalk 服务器上，打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**BizTalk 组**，然后选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-116">On each BizTalk server, open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **BizTalk Group**, and then select **Remove**.</span></span>  
  
7.  <span data-ttu-id="5cd3c-117">右键单击**BizTalk Server 2010 管理**，选择**连接到现有组**、 选择的 SQL Server 数据库实例和数据库对应的 BizTalk 管理数据库的名称BizTalk 组，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-117">Right-click **BizTalk Server 2010 Administration**, select **Connect to Existing Group**, select the SQL Server database instance and database name that corresponds to the BizTalk Management database for the BizTalk group, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5cd3c-118">在更新后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机，你可能还需要更新**SSO 服务器名称**中所示**组属性**对话框中提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-118">After updating the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers, you may also need to update the **SSO Server name** as displayed in the **Group Properties** dialog box available in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="5cd3c-119">若要更新**SSO 服务器名称**，启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，单击以展开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理，右键单击**BizTalk 组**节点，然后选择**属性**以显示**常规**选项卡[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-119">To update the **SSO Server name**, launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click to expand [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration, right-click the **BizTalk Group** node and select **Properties** to display the **General** tab of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="5cd3c-120">然后，在**SSO 服务器名称**文本框中，输入将使用此计算机来访问适配器的配置信息，然后单击企业单一登录服务器名称**确定**。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-120">Then, in the **SSO Server name** textbox, enter the name of the Enterprise Single Sign-On server that this computer will use to access the configuration information for the adapters and click **OK**.</span></span> <span data-ttu-id="5cd3c-121">这是用于连接到 SSO 数据库的 SSO 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5cd3c-121">This is the name of the SSO server used to connect to the SSO database.</span></span>  
  
8.  <span data-ttu-id="5cd3c-122">重新启动每个 BizTalk 运行时服务器上的以下 Windows 服务：</span><span class="sxs-lookup"><span data-stu-id="5cd3c-122">Restart the following Windows services on each BizTalk runtime server:</span></span>  
  
    -   <span data-ttu-id="5cd3c-123">企业 SSO 服务</span><span class="sxs-lookup"><span data-stu-id="5cd3c-123">Enterprise SSO Service</span></span>  
  
    -   <span data-ttu-id="5cd3c-124">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="5cd3c-124">Rule Engine Update Service</span></span>  
  
    -   <span data-ttu-id="5cd3c-125">BizTalk 主机实例</span><span class="sxs-lookup"><span data-stu-id="5cd3c-125">BizTalk Host Instances</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd3c-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5cd3c-126">See Also</span></span>  
 [<span data-ttu-id="5cd3c-127">恢复运行时计算机</span><span class="sxs-lookup"><span data-stu-id="5cd3c-127">Recovering the Runtime Computers</span></span>](../technical-guides/recovering-the-runtime-computers.md)