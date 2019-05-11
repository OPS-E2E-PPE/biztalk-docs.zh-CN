---
title: 如何更改默认应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, default
- applications, modifying
- modifying, applications
ms.assetid: cfa5e88f-0bbb-4edd-a840-722dcdcce266
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28c39f56d125044d234e2a073e6c27f52ad0afdf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342430"
---
# <a name="how-to-change-the-default-application"></a><span data-ttu-id="d25c4-102">如何更改默认应用程序</span><span class="sxs-lookup"><span data-stu-id="d25c4-102">How to Change the Default Application</span></span>
<span data-ttu-id="d25c4-103">本主题介绍如何通过编辑 BizTalk Server 管理控制台中的应用程序的属性来更改默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="d25c4-103">This topic describes how to change the default application by editing the properties of an application in the BizTalk Server Administration console.</span></span> <span data-ttu-id="d25c4-104">您还可以更改默认应用程序通过创建新的应用程序并指定为默认应用程序，如中所述[如何创建应用程序](../core/how-to-create-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d25c4-104">You can also change the default application by creating a new application and specifying it as the default application, as described in [How to Create an Application](../core/how-to-create-an-application.md).</span></span>  
  
 <span data-ttu-id="d25c4-105">在安装 BizTalk Server 时，名为 BizTalk 应用程序 1 的默认应用程序在 BizTalk 管理数据库中创建，并显示在 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="d25c4-105">When you install BizTalk Server, a default application named BizTalk Application 1 is created in the BizTalk Management database and appears in the BizTalk Server Administration console.</span></span> <span data-ttu-id="d25c4-106">在从 BizTalk Server 的早期版本升级，你的项目会自动放在此应用程序。</span><span class="sxs-lookup"><span data-stu-id="d25c4-106">When you upgrade from an earlier version of BizTalk Server, your artifacts are automatically placed in this application.</span></span> <span data-ttu-id="d25c4-107">此外，而无需指定应用程序中使用 BTSTask 导入 Windows Installer (.msi) 文件，当.msi 文件中的项目是导入到默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="d25c4-107">In addition, when you import a Windows Installer (.msi) file by using BTSTask without specifying an application, the artifacts in the .msi file are imported into the default application.</span></span>  
  
 <span data-ttu-id="d25c4-108">无法删除默认的应用程序;但是，可以更改哪些应用程序是默认值。</span><span class="sxs-lookup"><span data-stu-id="d25c4-108">You cannot delete the default application; however, you can change which application is the default.</span></span> <span data-ttu-id="d25c4-109">如果更改默认应用程序，然后可以删除以前是默认情况下，如果你想要的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d25c4-109">If you change the default application, you can then delete the application that was previously the default, if you want.</span></span> <span data-ttu-id="d25c4-110">有关说明，请参阅[如何从 BizTalk 组中删除 BizTalk 应用程序](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)。</span><span class="sxs-lookup"><span data-stu-id="d25c4-110">For instructions, see [How to Delete a BizTalk Application from the BizTalk Group](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).</span></span>  
  
 <span data-ttu-id="d25c4-111">更改默认应用程序时，所有项目都保持最初是默认的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="d25c4-111">When you change the default application, all of the artifacts remain in the application that was originally the default.</span></span> <span data-ttu-id="d25c4-112">如果你想，您可以显式移动从应用程序，项目。</span><span class="sxs-lookup"><span data-stu-id="d25c4-112">You can explicitly move the artifacts out of the application, if you want.</span></span> <span data-ttu-id="d25c4-113">有关说明，请参阅[如何将项目移到不同的应用程序](../core/how-to-move-an-artifact-to-a-different-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d25c4-113">For instructions, see [How to Move an Artifact to a Different Application](../core/how-to-move-an-artifact-to-a-different-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d25c4-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="d25c4-114">Prerequisites</span></span>  
 <span data-ttu-id="d25c4-115">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d25c4-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d25c4-116">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d25c4-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-change-the-default-application"></a><span data-ttu-id="d25c4-117">若要更改默认应用程序</span><span class="sxs-lookup"><span data-stu-id="d25c4-117">To change the default application</span></span>  
  
1. <span data-ttu-id="d25c4-118">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d25c4-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d25c4-119">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，右键单击你想要设置为默认设置，然后单击应用程序**属性**。</span><span class="sxs-lookup"><span data-stu-id="d25c4-119">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, right-click the application that you want to make the default, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="d25c4-120">选择**将此默认应用程序**复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d25c4-120">Select the **Make this the default application** check box, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d25c4-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="d25c4-121">See Also</span></span>  
 [<span data-ttu-id="d25c4-122">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="d25c4-122">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)