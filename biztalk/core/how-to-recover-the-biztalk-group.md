---
title: 恢复 BizTalk 组 |Microsoft 文档
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
ms.openlocfilehash: 3563956daa4848d4d67c1321c23676b21f9e4735
ms.sourcegitcommit: 78376935362715684b451eb6da9f2b1e8c129c2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
ms.locfileid: "28944093"
---
# <a name="how-to-recover-the-biztalk-group"></a><span data-ttu-id="bd64f-102">如何恢复 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="bd64f-102">How to Recover the BizTalk Group</span></span>
<span data-ttu-id="bd64f-103">必须在系统恢复过程中将 BizTalk Server 重新连接到现有的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="bd64f-103">You must rejoin the BizTalk Server to an existing BizTalk group as part of the system recovery process.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bd64f-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="bd64f-104">Prerequisites</span></span>  
 <span data-ttu-id="bd64f-105">必须以 Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="bd64f-105">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
 <span data-ttu-id="bd64f-106">如果要恢复 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 标准版，必须下载用于帮助恢复该服务器的脚本。</span><span class="sxs-lookup"><span data-stu-id="bd64f-106">If you are recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition, you must download a script that facilitates recovery of the server.</span></span> <span data-ttu-id="bd64f-107">下载[RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462)。</span><span class="sxs-lookup"><span data-stu-id="bd64f-107">Download [RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462).</span></span>  
  
## <a name="recover-the-biztalk-group-standard-edition"></a><span data-ttu-id="bd64f-108">恢复 BizTalk 组 （标准版）</span><span class="sxs-lookup"><span data-stu-id="bd64f-108">Recover the BizTalk group (Standard Edition)</span></span>  
  
1.  <span data-ttu-id="bd64f-109">单击**启动**，类型**cmd**，然后选择**命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="bd64f-109">Click **Start**, type **cmd**, and then select **Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="bd64f-110">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="bd64f-110">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="bd64f-111">**RestoreConfig.vbe**  *\<SavedConfigXML\>*</span><span class="sxs-lookup"><span data-stu-id="bd64f-111">**RestoreConfig.vbe**  *\<SavedConfigXML\>*</span></span>  
  
     <span data-ttu-id="bd64f-112">其中 *\<SavedConfigXML\>* 是完整路径和保存的配置文件的文件名。</span><span class="sxs-lookup"><span data-stu-id="bd64f-112">Where *\<SavedConfigXML\>* is the full path and filename of the saved configuration file.</span></span>  
  
     <span data-ttu-id="bd64f-113">上述操作应该在不显示任何错误的情况下退出。</span><span class="sxs-lookup"><span data-stu-id="bd64f-113">The above should exit without displaying any errors.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bd64f-114">若要恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位计算机上的 Standard Edition，你必须运行**RestoreConfig.vbe**从 32 位命令提示符，以便它能够更新 32 位注册表。</span><span class="sxs-lookup"><span data-stu-id="bd64f-114">To recover [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition on a 64-bit computer, you must run **RestoreConfig.vbe** from the 32-bit command prompt so that it can update the 32-bit registry.</span></span> <span data-ttu-id="bd64f-115">若要打开 32 位命令提示符，请单击 **启动**, ，单击 **运行**, ，类型 **c:\windows\syswow64\cmd.exe**, ，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="bd64f-115">To open the 32-bit command prompt, click **Start**, click **Run**, type **c:\windows\syswow64\cmd.exe**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bd64f-116">失败的计算机名称包含在已保存的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="bd64f-116">The name of the computer that failed is contained in the saved configuration file.</span></span> <span data-ttu-id="bd64f-117">要还原到的计算机的名称必须是相同的名称。</span><span class="sxs-lookup"><span data-stu-id="bd64f-117">The name of the computer that you are restoring onto must have that same name.</span></span> <span data-ttu-id="bd64f-118">您必须在具有该名称的计算机上运行上述脚本。</span><span class="sxs-lookup"><span data-stu-id="bd64f-118">You must run the script above on a computer with that name.</span></span> <span data-ttu-id="bd64f-119">但是，您可以在已保存配置文件中更改失败的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="bd64f-119">You can, however, change the name of the computer that failed in the saved configuration file.</span></span> <span data-ttu-id="bd64f-120">如果进行了此操作，您可以在具有不同名称的计算机上运行上述脚本。</span><span class="sxs-lookup"><span data-stu-id="bd64f-120">If you do so, you can run the script above onto a computer with a different name.</span></span>  
  
## <a name="recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a><span data-ttu-id="bd64f-121">恢复 BizTalk 组 （开发人员版或企业版）</span><span class="sxs-lookup"><span data-stu-id="bd64f-121">Recover the BizTalk group (Developer Edition or Enterprise Edition)</span></span>  
  
1.  <span data-ttu-id="bd64f-122">打开**BizTalk Server 配置**（开始菜单）。</span><span class="sxs-lookup"><span data-stu-id="bd64f-122">Open **BizTalk Server Configuration** (Start menu).</span></span>
  
2.  <span data-ttu-id="bd64f-123">在 BizTalk Server 管理中，选择**组**。</span><span class="sxs-lookup"><span data-stu-id="bd64f-123">In BizTalk Server Administration, select **Group**.</span></span>  
  
3.  <span data-ttu-id="bd64f-124">在详细信息窗格中，选择**加入现有的 BizTalk 组**，然后输入远程 BizTalk 管理 (BizTalkMgmtDb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="bd64f-124">In the details pane, select **Join an existing BizTalk Group**, and then enter the remote BizTalk Management (BizTalkMgmtDb) database.</span></span>  
  
4.  <span data-ttu-id="bd64f-125">选择**应用配置**。</span><span class="sxs-lookup"><span data-stu-id="bd64f-125">Select **Apply Configuration**.</span></span>  
  
5.  <span data-ttu-id="bd64f-126">选择**文件**，然后选择**退出**。</span><span class="sxs-lookup"><span data-stu-id="bd64f-126">Select **File**, and then select **Exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd64f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd64f-127">See Also</span></span>  
 [<span data-ttu-id="bd64f-128">恢复运行 BizTalk Server 的计算机</span><span class="sxs-lookup"><span data-stu-id="bd64f-128">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)
