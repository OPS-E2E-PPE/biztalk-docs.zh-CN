---
title: 卸载 BizTalk Server 上的 BizTalk RosettaNet 加速器 (BTARN) |Microsoft Docs"
description: 取消部署项目，并取消配置 btarn，让其从 BizTalk Server 中删除快捷键
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
ms.author: mandia
ms.openlocfilehash: a8e26119039910f398620efe478d07eeebca6f08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299964"
---
# <a name="uninstall-the-rosettanet-accelerator"></a><span data-ttu-id="f8451-103">卸载 RosettaNet 加速器</span><span class="sxs-lookup"><span data-stu-id="f8451-103">Uninstall the RosettaNet accelerator</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f8451-104">开始之前</span><span class="sxs-lookup"><span data-stu-id="f8451-104">Before you begin</span></span>
  
* <span data-ttu-id="f8451-105">如果只运行**Setup.exe**，卸载过程不会删除业务活动监视 (BAM) 项目、 BizTalk 项目、 Internet 信息服务 (IIS) 虚拟目录和应用程序池。</span><span class="sxs-lookup"><span data-stu-id="f8451-105">If you only run **Setup.exe**, the uninstall process does not remove the Business Activity Monitoring (BAM) artifacts, the BizTalk artifacts, Internet Information Services (IIS) virtual directories, and application pools.</span></span>  
  
* <span data-ttu-id="f8451-106">如果您使用了**Loopback**实用工具创建镜像协议对于单台计算机部署，然后运行该工具与 **/禁用 <** **本组织** **>** 选项在中删除合作伙伴之前**BTARN 管理控制台**。</span><span class="sxs-lookup"><span data-stu-id="f8451-106">If you used the **Loopback** utility to create mirror agreements for a single-computer deployment, then run the tool with the **/disable <** **home organization** **>** option before deleting the partners in the **BTARN Administration Console**.</span></span>  
  
* <span data-ttu-id="f8451-107">如果此服务器是多计算机部署的一部分，不能运行**BtarnClean**实用程序或手动取消部署 BTARN 程序集。</span><span class="sxs-lookup"><span data-stu-id="f8451-107">If this server is part of a multi-computer deployment, do not run the **BtarnClean** utility or manually undeploy the BTARN assemblies.</span></span> <span data-ttu-id="f8451-108">删除一台计算机上的项目会中断其他计算机的功能。</span><span class="sxs-lookup"><span data-stu-id="f8451-108">Removing the artifacts on one computer breaks the functionality of the other computers.</span></span>  <span data-ttu-id="f8451-109">如果你想要从所有服务器上卸载 BTARN，然后运行**BtarnClean**实用程序。</span><span class="sxs-lookup"><span data-stu-id="f8451-109">If you want to uninstall BTARN from all the servers, then run the **BtarnClean** utility.</span></span> 

  
## <a name="undeploy-the-artifacts"></a><span data-ttu-id="f8451-110">取消部署的项目</span><span class="sxs-lookup"><span data-stu-id="f8451-110">Undeploy the artifacts</span></span>  

<span data-ttu-id="f8451-111">我们建议在取消部署之前备份 BAM 项目。</span><span class="sxs-lookup"><span data-stu-id="f8451-111">We recommend backing up your BAM artifacts before undeploying.</span></span> 

1. <span data-ttu-id="f8451-112">取消部署已部署的所有 BAM 项目：</span><span class="sxs-lookup"><span data-stu-id="f8451-112">Undeploy all the BAM artifacts that you deployed:</span></span>  
  
    1.  <span data-ttu-id="f8451-113">在命令提示符处，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f8451-113">At the command prompt, run the following command:</span></span>  
  
         ```cd %ProgramFiles%\\<BizTalk Server installation directory\>\Tracking```
  
    2.  <span data-ttu-id="f8451-114">在已安装跟踪 UI 命令提示符处，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f8451-114">At the command prompt where the tracking UI was installed, run the following command:</span></span>  
  
         ```bm remove-all DefinitionFile:"%ProgramFiles%\\<installation directory\>\BAMTracking\tracking.xml"```
  
        > [!NOTE]
        >  <span data-ttu-id="f8451-115">有关 BAM 的详细信息，请参阅[管理业务活动监视](../../core/managing-bam.md)</span><span class="sxs-lookup"><span data-stu-id="f8451-115">For more information about BAM, see [Managing Business Activity Monitoring](../../core/managing-bam.md)</span></span> 
  
2.  <span data-ttu-id="f8451-116">备份和从 BTARN 管理控制台中删除所有协议、 合作伙伴和本组织。</span><span class="sxs-lookup"><span data-stu-id="f8451-116">Backup and delete all the agreements, partners, and home organizations from the BTARN Management Console.</span></span> <span data-ttu-id="f8451-117">请参阅有关使用信息 （在 BTARN 帮助的操作节点中） 的"管理 BTARN 配置"主题**BtarnConfig**实用工具备份协议和合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="f8451-117">See the "Administering the BTARN Configuration" topic (in the Operations node of BTARN Help) for information about using the **BtarnConfig** utility to back up the agreements and partners.</span></span>  
  
    > [!NOTE]
    >  * <span data-ttu-id="f8451-118">停止并取消部署 BTARN 使用创建的 BizTalk 项目[BtarnClean](btarnclean.md)实用程序。</span><span class="sxs-lookup"><span data-stu-id="f8451-118">Stop and undeploy the BizTalk artifacts created by BTARN by using the [BtarnClean](btarnclean.md) utility.</span></span>
    >  * <span data-ttu-id="f8451-119">删除任何已部署的其他项目。</span><span class="sxs-lookup"><span data-stu-id="f8451-119">Remove any additional artifacts that you deployed.</span></span> <span data-ttu-id="f8451-120">请参阅[正在取消部署 BizTalk 应用程序](../../core/undeploying-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="f8451-120">See [Undeploying BizTalk Applications](../../core/undeploying-biztalk-applications.md) .</span></span>
  
3.  <span data-ttu-id="f8451-121">从 BTARN 安装程序，找到 MSI\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f8451-121">From the BTARN Setup, locate the MSI\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK folder.</span></span> <span data-ttu-id="f8451-122">在 SDK 文件夹中，双击**BTARNClean.exe**，然后选择**Y**若要继续，或**N**取消运行该实用程序。</span><span class="sxs-lookup"><span data-stu-id="f8451-122">In the SDK folder, double-click **BTARNClean.exe**, and then select **Y** to continue, or **N** to cancel running the utility.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8451-123">如果你的服务器是多计算机部署方案的一部分，则可以跳过步骤 3。</span><span class="sxs-lookup"><span data-stu-id="f8451-123">If your server is part of a multi-computer deployment scenario, you can skip step 3.</span></span> <span data-ttu-id="f8451-124">取消部署任何共享的资源会削弱部署中的其他服务器上的功能。</span><span class="sxs-lookup"><span data-stu-id="f8451-124">Undeploying any shared resources breaks the functionality on the other servers in the deployment.</span></span>  
  
4.  <span data-ttu-id="f8451-125">取消部署任何自定义程序集创建和部署。</span><span class="sxs-lookup"><span data-stu-id="f8451-125">Undeploy any custom assemblies that you created and deployed.</span></span>  
  
5.  <span data-ttu-id="f8451-126">在命令提示符处，转到 files\microsoft BizTalk Server <your version>\Tracking。</span><span class="sxs-lookup"><span data-stu-id="f8451-126">At the command prompt, go to \Program Files\Microsoft BizTalk Server <your version>\Tracking.</span></span> <span data-ttu-id="f8451-127">运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="f8451-127">Run the following command:</span></span> 

    ```BM UNDEPLOY ALL <drive\>:\Program Files\\<installation directory\>\BAMTracking\tracking.xml```
  
## <a name="unconfigure-btarn"></a><span data-ttu-id="f8451-128">取消配置 BTARN</span><span class="sxs-lookup"><span data-stu-id="f8451-128">Unconfigure BTARN</span></span>
  
1.  <span data-ttu-id="f8451-129">找到并运行以下命令，取消配置 BTARN:</span><span class="sxs-lookup"><span data-stu-id="f8451-129">Locate and run the following to unconfigure BTARN:</span></span>  
  
     <span data-ttu-id="f8451-130">***<drive\>***  **:\Program Files\\<installation directory\>\Configuration.exe /u**</span><span class="sxs-lookup"><span data-stu-id="f8451-130">***<drive\>***  **:\Program Files\\<installation directory\>\Configuration.exe /u**</span></span>  
  
2.  <span data-ttu-id="f8451-131">在控制面板中，双击**添加或删除程序**。</span><span class="sxs-lookup"><span data-stu-id="f8451-131">In Control Panel, double-click **Add or Remove Programs**.</span></span>  
  
3.  <span data-ttu-id="f8451-132">在中**当前安装的程序**列表中，单击**Microsoft BizTalk Accelerator for RosettaNet**，然后单击**更改/删除**。</span><span class="sxs-lookup"><span data-stu-id="f8451-132">In the **Currently installed programs** list, click **Microsoft BizTalk Accelerator for RosettaNet**, and then click **Change/Remove**.</span></span>  
  
4.  <span data-ttu-id="f8451-133">在中**程序维护**对话框中，选择**删除**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f8451-133">In the **Program Maintenance** dialog box, select **Remove**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="f8451-134">在中**摘要**对话框中，单击**卸载**。</span><span class="sxs-lookup"><span data-stu-id="f8451-134">In the **Summary** dialog box, click **Uninstall**.</span></span>  
  
6.  <span data-ttu-id="f8451-135">在中**卸载已完成**对话框中，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="f8451-135">In the **Uninstall Completed** dialog box, click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8451-136">卸载过程不会删除在 BTARN 数据库 （BTARNARCHIVE、 BTARNCONFIG 和 BTARNDATA）。</span><span class="sxs-lookup"><span data-stu-id="f8451-136">The uninstallation process does not remove the BTARN databases (BTARNARCHIVE, BTARNCONFIG, and BTARNDATA).</span></span> <span data-ttu-id="f8451-137">您必须手动删除它们。</span><span class="sxs-lookup"><span data-stu-id="f8451-137">You must manually remove them.</span></span>  
  
7.  <span data-ttu-id="f8451-138">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="f8451-138">Open **SQL Server Management Studio**.</span></span>  
  
8.  <span data-ttu-id="f8451-139">在中**连接到服务器**对话框中，单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="f8451-139">In the **Connect to Server** dialog box, click **Connect**.</span></span>  
  
9. <span data-ttu-id="f8451-140">展开**数据库**的左窗格中的节点。</span><span class="sxs-lookup"><span data-stu-id="f8451-140">Expand the **Databases** node in the left pane.</span></span> <span data-ttu-id="f8451-141">右键单击 BTARN 数据库之一，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="f8451-141">Right-click one of the BTARN databases, and then click **Delete**.</span></span>  
  
10. <span data-ttu-id="f8451-142">在中**删除对象**对话框中，选择**关闭现有连接**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f8451-142">In the **Delete Object** dialog box, select **Close Existing Connections**, and then click **OK**.</span></span>  
  
