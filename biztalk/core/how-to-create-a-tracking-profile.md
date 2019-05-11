---
title: 如何创建跟踪配置文件 |Microsoft Docs
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
ms.openlocfilehash: bb5951042bc3f3bbc3c2379cc83ab07de0d35c0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385555"
---
# <a name="how-to-create-a-tracking-profile"></a><span data-ttu-id="4c1fa-102">如何创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="4c1fa-102">How to Create a Tracking Profile</span></span>
<span data-ttu-id="4c1fa-103">创建跟踪配置文件可将 BAM 活动定义链接到已部署程序集和 BizTalk Server 消息传送属性。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-103">You create tracking profiles to link BAM activity definitions to deployed assemblies and BizTalk Server messaging properties.</span></span> <span data-ttu-id="4c1fa-104">当您打开跟踪配置文件编辑器时，可以通过单击导入活动链接或导入菜单项来创建新的跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-104">When you open the Tracking Profile Editor, you can create a new tracking profile by either clicking the import activity link or the import menu item.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4c1fa-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="4c1fa-105">Prerequisites</span></span>  
 <span data-ttu-id="4c1fa-106">在本主题中执行该过程的先决条件如下：</span><span class="sxs-lookup"><span data-stu-id="4c1fa-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="4c1fa-107">现有的 BizTalk 管理数据库对其具有权限。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-107">An existing BizTalk Management database to which you have permissions.</span></span>  
  
-   <span data-ttu-id="4c1fa-108">TPE 配置为使用 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-108">The TPE configured to use the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="4c1fa-109">BAM 主导入数据库中的现有 BAM 活动定义。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-109">An existing BAM activity definition in the BAM Primary Import database.</span></span>  
  
### <a name="to-create-a-tracking-profile"></a><span data-ttu-id="4c1fa-110">若要创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="4c1fa-110">To create a tracking profile</span></span>  
  
1.  <span data-ttu-id="4c1fa-111">在计算机或计算机已标识为源系统中，打开**跟踪配置文件编辑器**。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-111">On the computer or computers that you have identified as the source system, open the **Tracking Profile Editor**.</span></span> <span data-ttu-id="4c1fa-112">若要执行此操作，请单击**启动**，单击**运行**，类型**BTSTrkEditor.exe**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-112">To do this, click **Start**, click **Run**, type **BTSTrkEditor.exe**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4c1fa-113">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="4c1fa-114">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-114">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="4c1fa-115">中间 TPE 的左窗格中，单击**单击此处可导入 BAM 活动定义**链接。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-115">In the middle of the left pane of the TPE, click **Click here to import a BAM Activity Definition** link.</span></span> <span data-ttu-id="4c1fa-116">这将打开**导入 BAM 活动定义**对话框。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-116">This opens the **Import BAM Activity Definition** dialog box.</span></span>  
  
3.  <span data-ttu-id="4c1fa-117">从**BAM 活动定义名称**列表框选择要跟踪所基于的活动。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-117">From the **BAM Activity Definition Name** list box select the activity on which to base the tracking.</span></span> <span data-ttu-id="4c1fa-118">如果列表包含许多已部署的活动，则可以键入中的活动名称的一部分**字符串中**文本框中，然后单击**搜索**按钮。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-118">If your list contains many deployed activities, you can type part of the activity name in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="4c1fa-119">这将限制为那些名称中包含输入的部分名称显示的活动列表。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-119">This limits the list of activities displayed to those whose names contain the partial name entered.</span></span>  
  
4.  <span data-ttu-id="4c1fa-120">一旦选择活动后，单击**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-120">Once you have selected the activity, click the **OK** button.</span></span> <span data-ttu-id="4c1fa-121">这将打开基于所选活动的新跟踪配置文件，并在 TPE 的左窗格中显示该配置文件。</span><span class="sxs-lookup"><span data-stu-id="4c1fa-121">This opens a new tracking profile based on the activity selected and displays the profile in the left pane of the TPE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c1fa-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c1fa-122">See Also</span></span>  
 [<span data-ttu-id="4c1fa-123">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="4c1fa-123">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)