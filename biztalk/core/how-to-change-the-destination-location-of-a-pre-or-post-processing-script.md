---
title: 如何更改预处理或后处理脚本的目标位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, file locations
- scripts, modifying
- managing [scripts], modifying
- managing [scripts], file locations
ms.assetid: 4a4fdaef-099f-4c29-9815-12404c7a2212
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f6d1a7ec9f661a86ff028b1ec364bbd656cbb2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005286"
---
# <a name="how-to-change-the-destination-location-of-a-pre--or-post-processing-script"></a><span data-ttu-id="07bae-102">如何更改预处理或后处理脚本的目标位置</span><span class="sxs-lookup"><span data-stu-id="07bae-102">How to Change the Destination Location of a Pre- or Post-processing Script</span></span>
<span data-ttu-id="07bae-103">本主题介绍如何使用 BizTalk Server 管理控制台来更改预处理或后处理脚本的目标位置。</span><span class="sxs-lookup"><span data-stu-id="07bae-103">This topic describes how to use the BizTalk Server Administration console to change the destination location of a pre- or post-processing script.</span></span> <span data-ttu-id="07bae-104">这是该脚本复制到其中安装应用程序的位置。</span><span class="sxs-lookup"><span data-stu-id="07bae-104">This is the location to which the script is copied when the application is installed.</span></span> <span data-ttu-id="07bae-105">您可能想要部署到不同环境的应用程序时更改的目标位置。</span><span class="sxs-lookup"><span data-stu-id="07bae-105">You might want to change the destination location when deploying an application into a different environment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="07bae-106">请务必提供卸载应用程序时将运行的脚本的目标位置。</span><span class="sxs-lookup"><span data-stu-id="07bae-106">Be sure to provide a destination location for a script that will run when the application is uninstalled.</span></span> <span data-ttu-id="07bae-107">如果不这样做，脚本将不会复制到本地文件系统中，并因此将不在卸载期间运行。</span><span class="sxs-lookup"><span data-stu-id="07bae-107">If you do not, the script will not be copied to the local file system, and therefore will not run during uninstallation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="07bae-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="07bae-108">Prerequisites</span></span>  
 <span data-ttu-id="07bae-109">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="07bae-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="07bae-110">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="07bae-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-modify-the-deployment-properties-of-a-pre--or-post-processing-script"></a><span data-ttu-id="07bae-111">若要修改预处理或后处理脚本的部署属性</span><span class="sxs-lookup"><span data-stu-id="07bae-111">To modify the deployment properties of a pre- or post-processing script</span></span>  
  
1. <span data-ttu-id="07bae-112">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="07bae-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="07bae-113">在控制台树中，展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开包含要修改的脚本的 BizTalk 组，接着展开包含该脚本的应用程序。</span><span class="sxs-lookup"><span data-stu-id="07bae-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the script to modify, and then expand the application containing the script.</span></span>  
  
3. <span data-ttu-id="07bae-114">单击**资源**文件夹中，右键单击脚本，然后依次**修改**。</span><span class="sxs-lookup"><span data-stu-id="07bae-114">Click the **Resources** folder, right-click the script, and then click **Modify**.</span></span>  
  
4. <span data-ttu-id="07bae-115">在中**目标位置**，键入目标位置，包括文件名称的完整路径，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="07bae-115">In **Destination location**, type the full path of the destination location, including the file name, and then click **OK**.</span></span> <span data-ttu-id="07bae-116">（您可以使用环境变量 %btad_installdir%在路径中指定应用程序安装文件夹。）</span><span class="sxs-lookup"><span data-stu-id="07bae-116">(You can use the environment variable %BTAD_InstallDir% in the path to specify the application installation folder.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07bae-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="07bae-117">See Also</span></span>  
 [<span data-ttu-id="07bae-118">管理预处理脚本和后期处理脚本</span><span class="sxs-lookup"><span data-stu-id="07bae-118">Managing Pre- and Post-processing Scripts</span></span>](../core/managing-pre-and-post-processing-scripts.md)