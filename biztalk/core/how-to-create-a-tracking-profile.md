---
title: 如何创建跟踪配置文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, creating
- creating, tracking profiles
ms.assetid: 676ae7e8-f3eb-45f1-ad2e-807b434c0bf9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34f5d6cbb210cb292cd8ae7d0e2f4ff811984377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248933"
---
# <a name="how-to-create-a-tracking-profile"></a><span data-ttu-id="e12c8-102">如何创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="e12c8-102">How to Create a Tracking Profile</span></span>
<span data-ttu-id="e12c8-103">创建跟踪配置文件可将 BAM 活动定义链接到部署的程序集和 BizTalk Server 消息传送属性。</span><span class="sxs-lookup"><span data-stu-id="e12c8-103">You create tracking profiles to link BAM activity definitions to deployed assemblies and BizTalk Server messaging properties.</span></span> <span data-ttu-id="e12c8-104">跟踪配置文件编辑器打开时，你可以通过单击导入活动链接或导入菜单项来创建新的跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="e12c8-104">When you open the Tracking Profile Editor, you can create a new tracking profile by either clicking the import activity link or the import menu item.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e12c8-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="e12c8-105">Prerequisites</span></span>  
 <span data-ttu-id="e12c8-106">以下为执行本主题中的过程的前提条件：</span><span class="sxs-lookup"><span data-stu-id="e12c8-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="e12c8-107">您有权访问现有的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="e12c8-107">An existing BizTalk Management database to which you have permissions.</span></span>  
  
-   <span data-ttu-id="e12c8-108">TPE 配置为使用 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="e12c8-108">The TPE configured to use the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="e12c8-109">BAM 主导入数据库中已有 BAM 活动定义。</span><span class="sxs-lookup"><span data-stu-id="e12c8-109">An existing BAM activity definition in the BAM Primary Import database.</span></span>  
  
### <a name="to-create-a-tracking-profile"></a><span data-ttu-id="e12c8-110">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="e12c8-110">To create a tracking profile</span></span>  
  
1.  <span data-ttu-id="e12c8-111">在计算机或已标识为源系统的计算机中，打开**跟踪配置文件编辑器**。</span><span class="sxs-lookup"><span data-stu-id="e12c8-111">On the computer or computers that you have identified as the source system, open the **Tracking Profile Editor**.</span></span> <span data-ttu-id="e12c8-112">若要执行此操作，请单击**启动**，单击**运行**，类型**BTSTrkEditor.exe**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e12c8-112">To do this, click **Start**, click **Run**, type **BTSTrkEditor.exe**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e12c8-113">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="e12c8-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="e12c8-114">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="e12c8-114">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="e12c8-115">中间键入的左窗格中，单击**单击此处以导入 BAM 活动定义**链接。</span><span class="sxs-lookup"><span data-stu-id="e12c8-115">In the middle of the left pane of the TPE, click **Click here to import a BAM Activity Definition** link.</span></span> <span data-ttu-id="e12c8-116">这将打开**导入 BAM 活动定义**对话框。</span><span class="sxs-lookup"><span data-stu-id="e12c8-116">This opens the **Import BAM Activity Definition** dialog box.</span></span>  
  
3.  <span data-ttu-id="e12c8-117">从**BAM 活动定义名称**列表框中选择要作为跟踪依据的活动。</span><span class="sxs-lookup"><span data-stu-id="e12c8-117">From the **BAM Activity Definition Name** list box select the activity on which to base the tracking.</span></span> <span data-ttu-id="e12c8-118">如果你的列表包含许多已部署的活动，你可以键入部分中的活动名称**中字符串**文本框中，然后单击**搜索**按钮。</span><span class="sxs-lookup"><span data-stu-id="e12c8-118">If your list contains many deployed activities, you can type part of the activity name in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="e12c8-119">这将使活动列表仅显示名称中包含您输入的部分名称的活动。</span><span class="sxs-lookup"><span data-stu-id="e12c8-119">This limits the list of activities displayed to those whose names contain the partial name entered.</span></span>  
  
4.  <span data-ttu-id="e12c8-120">在选择活动，单击**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="e12c8-120">Once you have selected the activity, click the **OK** button.</span></span> <span data-ttu-id="e12c8-121">此时将打开基于所选活动的新跟踪配置文件，并在 TPE 的左窗格中显示该配置文件。</span><span class="sxs-lookup"><span data-stu-id="e12c8-121">This opens a new tracking profile based on the activity selected and displays the profile in the left pane of the TPE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e12c8-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e12c8-122">See Also</span></span>  
 [<span data-ttu-id="e12c8-123">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="e12c8-123">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)