---
title: 更新、 修复或卸载 BizTalk Accelerator for HL7 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2fc84d2-1262-4a6e-ae9c-488a00ab4099
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a63f015541c93f1fb2000eed064aaa50df0fca86
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977310"
---
# <a name="update-repair-or-uninstall-biztalk-accelerator-for-hl7"></a><span data-ttu-id="ea964-102">更新、 修复或卸载 BizTalk Accelerator for HL7</span><span class="sxs-lookup"><span data-stu-id="ea964-102">Update, repair, or uninstall BizTalk Accelerator for HL7</span></span>

<span data-ttu-id="ea964-103">更改、 修复或卸载[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ea964-103">Change, repair or uninstall the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ea964-104">请务必卸载[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]然后再卸载[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ea964-104">Be sure to uninstall [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] before uninstalling [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]<span data-ttu-id="ea964-105"> 如果无法卸载[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]不再安装。</span><span class="sxs-lookup"><span data-stu-id="ea964-105"> cannot be uninstalled if [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is no longer installed.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="ea964-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="ea964-106">Prerequisites</span></span>
* <span data-ttu-id="ea964-107">使用的成员帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="ea964-107">Sign in using an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  

* <span data-ttu-id="ea964-108">此用户帐户还必须是 Administrators 组的成员上[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]存储 BizTalk Accelerator for HL7 数据。</span><span class="sxs-lookup"><span data-stu-id="ea964-108">This user account must also be a member of the Administrators group on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] that stores the BizTalk Accelerator for HL7 data.</span></span>  
    
## <a name="update-an-existing-installation"></a><span data-ttu-id="ea964-109">更新现有安装</span><span class="sxs-lookup"><span data-stu-id="ea964-109">Update an existing installation</span></span>

> [!NOTE]
>  <span data-ttu-id="ea964-110">当修改您的安装的[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]，端到端教程不会自动运行。</span><span class="sxs-lookup"><span data-stu-id="ea964-110">When you modify your installation of [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)], the End-to-End Tutorial does not automatically run.</span></span> 
> 
> <span data-ttu-id="ea964-111">若要运行本教程并验证是否已修改的安装是否正确执行，运行手动从教程***\<驱动器\>*** **\Program Files\Microsoft BizTalk \<版本\>HL7\SDK\End 端到端教程中的加速器**文件夹。</span><span class="sxs-lookup"><span data-stu-id="ea964-111">To run the tutorial and verify that the modified installation executed correctly, run the tutorial manually from the ***\<drive\>*** **\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial** folder.</span></span>
  
1. <span data-ttu-id="ea964-112">运行[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe**以管理员身份</span><span class="sxs-lookup"><span data-stu-id="ea964-112">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe** as an administrator</span></span> 
  
2. <span data-ttu-id="ea964-113">在欢迎页上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ea964-113">On the welcome page, select **Next**.</span></span>  
  
3. <span data-ttu-id="ea964-114">在中**程序维护**，选择**修改**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ea964-114">In **Program Maintenance**, select **Modify**, and then select **Next**.</span></span>  
  
4. <span data-ttu-id="ea964-115">在中**自定义安装**，选择你想要安装的功能，清除功能也不想，并选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ea964-115">In **Custom Setup**, select the features that you want to install, clear the features you don't want, and then select **Next**.</span></span>  
  
5. <span data-ttu-id="ea964-116">在摘要中，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ea964-116">In the summary, select **Next**.</span></span>  
  
6. <span data-ttu-id="ea964-117">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="ea964-117">Select **Install**.</span></span>  
  
7. <span data-ttu-id="ea964-118">完成时，选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="ea964-118">When complete, select **Finish**.</span></span>  

## <a name="repair-an-existing-installation"></a><span data-ttu-id="ea964-119">修复现有安装</span><span class="sxs-lookup"><span data-stu-id="ea964-119">Repair an existing installation</span></span>
<span data-ttu-id="ea964-120">[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]向导通过修复丢失或损坏的文件、 快捷方式或注册表项来修复安装。</span><span class="sxs-lookup"><span data-stu-id="ea964-120">The [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] Wizard repairs an installation by fixing missing or corrupt files, shortcuts, or registry entries.</span></span>  
  
1. <span data-ttu-id="ea964-121">运行[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="ea964-121">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe** as administrator.</span></span>  
  
2. <span data-ttu-id="ea964-122">在欢迎页上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ea964-122">On the welcome page, select **Next**.</span></span>  
  
3. <span data-ttu-id="ea964-123">在中**程序维护**，选择**修复**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ea964-123">In **Program Maintenance**, select **Repair**, and then select **Next**.</span></span>  
  
4. <span data-ttu-id="ea964-124">在中**日志记录服务帐户**，重新输入该用户帐户，并选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="ea964-124">In **Logging Service Account**, re-enter the user account, and then select **OK**.</span></span>  
  
5. <span data-ttu-id="ea964-125">如果系统提示**帐户名已被授予登录，为服务正确**，然后选择**确定**以继续。</span><span class="sxs-lookup"><span data-stu-id="ea964-125">If prompted **The account name has been granted logon as a service right**, then select **OK** to continue.</span></span>  
  
6. <span data-ttu-id="ea964-126">准备好修复后，选择**安装**。</span><span class="sxs-lookup"><span data-stu-id="ea964-126">When ready to repair, select **Install**.</span></span>  
  
7. <span data-ttu-id="ea964-127">完成后，选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="ea964-127">When completed, select **Finish**.</span></span> 

  
## <a name="uninstall-btahl7"></a><span data-ttu-id="ea964-128">卸载 BTAHL7</span><span class="sxs-lookup"><span data-stu-id="ea964-128">Uninstall BTAHL7</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="ea964-129">如果接收位置或发送端口使用 MLLP 传输类型，BTAHL7 安装程序不会在卸载 BTAHL7 的过程删除 MLLP 适配器。</span><span class="sxs-lookup"><span data-stu-id="ea964-129">If there is a receive location or send port using the MLLP transport type, the BTAHL7 setup does not remove the MLLP adapter during the uninstall of BTAHL7.</span></span> <span data-ttu-id="ea964-130">在卸载之前，删除所有接收位置或发送端口使用 MLLP 传输。</span><span class="sxs-lookup"><span data-stu-id="ea964-130">Before you uninstall, remove all receive locations or send ports using the MLLP transport.</span></span> <span data-ttu-id="ea964-131">或者，从 MLLP 的传输类型更改为另一种类型。</span><span class="sxs-lookup"><span data-stu-id="ea964-131">Or, change the transport type from MLLP to another type.</span></span> <span data-ttu-id="ea964-132">然后，卸载会删除 MLLP 适配器。</span><span class="sxs-lookup"><span data-stu-id="ea964-132">Then, the uninstall will remove the MLLP adapter.</span></span>  
      
1. <span data-ttu-id="ea964-133">打开“程序和功能”。</span><span class="sxs-lookup"><span data-stu-id="ea964-133">Open **Programs and Features**.</span></span>  
  
2. <span data-ttu-id="ea964-134">选择[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]，然后选择**卸载**。</span><span class="sxs-lookup"><span data-stu-id="ea964-134">Select [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], and then select **Uninstall**.</span></span>  
  
3. <span data-ttu-id="ea964-135">选择**是**如果系统要求确认。</span><span class="sxs-lookup"><span data-stu-id="ea964-135">Select **Yes** if asked to confirm.</span></span> 
  
4. <span data-ttu-id="ea964-136">完成后，选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="ea964-136">When completed, select **Finish**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ea964-137">BTAHL7 不会自动卸载[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目和程序集。</span><span class="sxs-lookup"><span data-stu-id="ea964-137">BTAHL7 does not automatically uninstall [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] artifacts and assemblies.</span></span>  
  

  
## <a name="troubleshooting-installation-issues"></a><span data-ttu-id="ea964-138">安装问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="ea964-138">Troubleshooting Installation Issues</span></span>  
 <span data-ttu-id="ea964-139">如果服务器将无法验证用户是否是[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员，卸载 BTAHL7 将返回以下错误：</span><span class="sxs-lookup"><span data-stu-id="ea964-139">If the server is unable to validate whether the user is a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrator, uninstalling BTAHL7 returns the following error:</span></span> 
 
 `Fatal error during uninstallation`  
  
<span data-ttu-id="ea964-140">若要继续卸载，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ea964-140">To continue with uninstallation, do the following:</span></span>  
  
1. <span data-ttu-id="ea964-141">以本地管理员身份登录到服务器。</span><span class="sxs-lookup"><span data-stu-id="ea964-141">Sign in to the server as a local administrator.</span></span>  
  
2. <span data-ttu-id="ea964-142">卸载 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ea964-142">Uninstall [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
3. <span data-ttu-id="ea964-143">卸载 [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ea964-143">Uninstall [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea964-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea964-144">See Also</span></span>  
[<span data-ttu-id="ea964-145">安装或升级 Microsoft BizTalk Accelerator for HL7</span><span class="sxs-lookup"><span data-stu-id="ea964-145">Install or upgrade Microsoft BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)