---
title: 恢复 BizTalk 组 |Microsoft Docs
ms.custom: ''
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1010e55-7e3d-4565-8604-ea652ea4da8c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e96e647358a0fd0601933dc0b1744537d63ae630
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023587"
---
# <a name="how-to-recover-the-biztalk-group"></a><span data-ttu-id="ec33d-102">如何恢复 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="ec33d-102">How to Recover the BizTalk Group</span></span>
<span data-ttu-id="ec33d-103">必须在系统恢复过程中将 BizTalk Server 重新连接到现有的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="ec33d-103">You must rejoin the BizTalk Server to an existing BizTalk group as part of the system recovery process.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ec33d-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="ec33d-104">Prerequisites</span></span>  
 <span data-ttu-id="ec33d-105">必须以 Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="ec33d-105">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
 <span data-ttu-id="ec33d-106">如果要恢复 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 标准版，必须下载用于帮助恢复该服务器的脚本。</span><span class="sxs-lookup"><span data-stu-id="ec33d-106">If you are recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition, you must download a script that facilitates recovery of the server.</span></span> <span data-ttu-id="ec33d-107">下载[RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462)。</span><span class="sxs-lookup"><span data-stu-id="ec33d-107">Download [RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462).</span></span>  
  
## <a name="recover-the-biztalk-group-standard-edition"></a><span data-ttu-id="ec33d-108">恢复 BizTalk 组 （标准版）</span><span class="sxs-lookup"><span data-stu-id="ec33d-108">Recover the BizTalk group (Standard Edition)</span></span>  
  
1. <span data-ttu-id="ec33d-109">单击**启动**，类型**cmd**，然后选择**命令提示符下**。</span><span class="sxs-lookup"><span data-stu-id="ec33d-109">Click **Start**, type **cmd**, and then select **Command Prompt**.</span></span>  
  
2. <span data-ttu-id="ec33d-110">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="ec33d-110">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="ec33d-111">**RestoreConfig.vbe**  *\<SavedConfigXML\>*</span><span class="sxs-lookup"><span data-stu-id="ec33d-111">**RestoreConfig.vbe**  *\<SavedConfigXML\>*</span></span>  
  
    <span data-ttu-id="ec33d-112">其中*\<SavedConfigXML\>* 是完整路径和保存的配置文件的文件名。</span><span class="sxs-lookup"><span data-stu-id="ec33d-112">Where *\<SavedConfigXML\>* is the full path and filename of the saved configuration file.</span></span>  
  
    <span data-ttu-id="ec33d-113">上述操作应该在不显示任何错误的情况下退出。</span><span class="sxs-lookup"><span data-stu-id="ec33d-113">The above should exit without displaying any errors.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ec33d-114">若要恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位计算机上的 Standard Edition，您必须运行**RestoreConfig.vbe**从 32 位命令提示符，以便它能够更新 32 位注册表。</span><span class="sxs-lookup"><span data-stu-id="ec33d-114">To recover [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition on a 64-bit computer, you must run **RestoreConfig.vbe** from the 32-bit command prompt so that it can update the 32-bit registry.</span></span> <span data-ttu-id="ec33d-115">若要打开 32 位命令提示符下，单击**启动**，单击**运行**，类型**c:\windows\syswow64\cmd.exe**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ec33d-115">To open the 32-bit command prompt, click **Start**, click **Run**, type **c:\windows\syswow64\cmd.exe**, and then click **OK**.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="ec33d-116">失败的计算机名称包含在已保存的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="ec33d-116">The name of the computer that failed is contained in the saved configuration file.</span></span> <span data-ttu-id="ec33d-117">要还原到的计算机的名称必须是相同的名称。</span><span class="sxs-lookup"><span data-stu-id="ec33d-117">The name of the computer that you are restoring onto must have that same name.</span></span> <span data-ttu-id="ec33d-118">您必须在具有该名称的计算机上运行上述脚本。</span><span class="sxs-lookup"><span data-stu-id="ec33d-118">You must run the script above on a computer with that name.</span></span> <span data-ttu-id="ec33d-119">但是，您可以在已保存配置文件中更改失败的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="ec33d-119">You can, however, change the name of the computer that failed in the saved configuration file.</span></span> <span data-ttu-id="ec33d-120">如果进行了此操作，您可以在具有不同名称的计算机上运行上述脚本。</span><span class="sxs-lookup"><span data-stu-id="ec33d-120">If you do so, you can run the script above onto a computer with a different name.</span></span>  
  
## <a name="recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a><span data-ttu-id="ec33d-121">恢复 BizTalk 组 （开发人员版或企业版）</span><span class="sxs-lookup"><span data-stu-id="ec33d-121">Recover the BizTalk group (Developer Edition or Enterprise Edition)</span></span>  
  
1.  <span data-ttu-id="ec33d-122">打开**BizTalk Server 配置**（开始菜单）。</span><span class="sxs-lookup"><span data-stu-id="ec33d-122">Open **BizTalk Server Configuration** (Start menu).</span></span>
  
2.  <span data-ttu-id="ec33d-123">在 BizTalk Server 管理中选择**组**。</span><span class="sxs-lookup"><span data-stu-id="ec33d-123">In BizTalk Server Administration, select **Group**.</span></span>  
  
3.  <span data-ttu-id="ec33d-124">在细节窗格中，选择**加入现有 BizTalk 组**，然后输入远程 BizTalk 管理 (BizTalkMgmtDb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="ec33d-124">In the details pane, select **Join an existing BizTalk Group**, and then enter the remote BizTalk Management (BizTalkMgmtDb) database.</span></span>  
  
4.  <span data-ttu-id="ec33d-125">选择**应用配置**。</span><span class="sxs-lookup"><span data-stu-id="ec33d-125">Select **Apply Configuration**.</span></span>  
  
5.  <span data-ttu-id="ec33d-126">选择**文件**，然后选择**退出**。</span><span class="sxs-lookup"><span data-stu-id="ec33d-126">Select **File**, and then select **Exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec33d-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec33d-127">See Also</span></span>  
 [<span data-ttu-id="ec33d-128">恢复运行 BizTalk Server 的计算机</span><span class="sxs-lookup"><span data-stu-id="ec33d-128">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)
