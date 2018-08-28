---
title: 如何恢复企业单一登录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 845e6ff7-88a8-4ab4-b307-f9275d44600e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d56953fcab29b53f23ba3097296a74aeb67a17c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973118"
---
# <a name="how-to-recover-enterprise-single-sign-on"></a><span data-ttu-id="1476e-102">如何恢复企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1476e-102">How to Recover Enterprise Single Sign-On</span></span>
<span data-ttu-id="1476e-103">必须先恢复企业单一登录 (SSO)，然后才能恢复 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="1476e-103">Before you can recover BizTalk Server, you must first recover Enterprise Single Sign-On (SSO).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1476e-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="1476e-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="1476e-105">若要执行此项任务，您必须以 Single Sign-On Administrators 组成员和 Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="1476e-105">You must be logged on as a member of the Single Sign-On Administrators group and a member of the Administrators group to perform this task.</span></span>  
  
-   <span data-ttu-id="1476e-106">您必须拥有配置 SSO 时所使用的密码。</span><span class="sxs-lookup"><span data-stu-id="1476e-106">You must have the password used during SSO configuration.</span></span>  
  
-   <span data-ttu-id="1476e-107">远程服务器上所有数据库都保持不变。</span><span class="sxs-lookup"><span data-stu-id="1476e-107">All databases are intact on the remote server.</span></span>  
  
-   <span data-ttu-id="1476e-108">备份主密钥文件保持不变，且保存到一个安全的地方。</span><span class="sxs-lookup"><span data-stu-id="1476e-108">The backup master secret file is intact and stored in a safe place.</span></span>  
  
### <a name="to-recover-enterprise-single-sign-on"></a><span data-ttu-id="1476e-109">恢复企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1476e-109">To recover Enterprise Single Sign-On</span></span>  
  
1. <span data-ttu-id="1476e-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**。</span><span class="sxs-lookup"><span data-stu-id="1476e-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2. <span data-ttu-id="1476e-111">在 Microsoft BizTalk Server 配置，在控制台树中，单击**企业 SSO**。</span><span class="sxs-lookup"><span data-stu-id="1476e-111">In Microsoft BizTalk Server Configuration, in the console tree, click **Enterprise SSO**.</span></span>  
  
3. <span data-ttu-id="1476e-112">在细节窗格中，选择**启用企业单一登录此计算机上**，然后单击**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="1476e-112">In the details pane, select **Enable Enterprise Single Sign-On on this computer**, and then click **Join an existing SSO system**.</span></span>  
  
4. <span data-ttu-id="1476e-113">在中**数据存储区**，输入托管 SSO 数据库和 SSO 数据库的名称的 SQL server 的名称。</span><span class="sxs-lookup"><span data-stu-id="1476e-113">In **Data stores**, enter the name of the SQL server hosting the SSO database and the name of the SSO database.</span></span>  
  
5. <span data-ttu-id="1476e-114">在中**Windows 服务**，最初安装和配置 BizTalk Server 时使用的 SSO 服务帐户输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="1476e-114">In **Windows service**, enter the user name and password for the SSO service account that you used when you originally installed and configured BizTalk Server.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="1476e-115">您也可使用其他帐户，但必须是 Single Sign-On Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="1476e-115">You can use a different account, but it must be a member of the Single Sign-On Administrators group.</span></span>  
  
6. <span data-ttu-id="1476e-116">单击“应用配置”。</span><span class="sxs-lookup"><span data-stu-id="1476e-116">Click **Apply Configuration**.</span></span>  
  
    <span data-ttu-id="1476e-117">此时将显示未检索到主密钥的警告。</span><span class="sxs-lookup"><span data-stu-id="1476e-117">A warning that no master secrets were retrieved is displayed.</span></span> <span data-ttu-id="1476e-118">您可使用事件查看器来验证企业单一登录服务是否已经启动，并正在该计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="1476e-118">You can use Event Viewer to verify that the Enterprise Single Sign-On service is now started and running on the computer.</span></span>  
  
7. <span data-ttu-id="1476e-119">单击**文件**，然后单击**退出**。</span><span class="sxs-lookup"><span data-stu-id="1476e-119">Click **File**, and then click **Exit**.</span></span>  
  
8. <span data-ttu-id="1476e-120">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1476e-120">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="1476e-121">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="1476e-121">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="1476e-122">**cd Program Files\Common Files\Enterprise Single Sign-on**</span><span class="sxs-lookup"><span data-stu-id="1476e-122">**cd Program Files\Common Files\Enterprise Single Sign-On**</span></span>  
  
10. <span data-ttu-id="1476e-123">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="1476e-123">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="1476e-124">**ssoconfig-restoreSecret***\<backupfile  \>*</span><span class="sxs-lookup"><span data-stu-id="1476e-124">**ssoconfig -restoreSecret**  *\<backupfile\>*</span></span>  
  
     <span data-ttu-id="1476e-125">其中*\<backupfile\>* 是您备份主密钥文件的名称。</span><span class="sxs-lookup"><span data-stu-id="1476e-125">where *\<backupfile\>* is the name of the master secret file that you backed up.</span></span>  
  
     <span data-ttu-id="1476e-126">当**ssoconfig**提示您输入备份文件的密码，输入配置 SSO 时指定的密码。</span><span class="sxs-lookup"><span data-stu-id="1476e-126">When **ssoconfig** prompts you for the backup file password, enter the password that was specified during SSO configuration.</span></span> <span data-ttu-id="1476e-127">如果密码正确无误， **ssoconfig**会显示以下消息：</span><span class="sxs-lookup"><span data-stu-id="1476e-127">If the password is correct, **ssoconfig** displays the following message:</span></span>  
  
     <span data-ttu-id="1476e-128">**操作已成功完成**</span><span class="sxs-lookup"><span data-stu-id="1476e-128">**The operation completed successfully**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1476e-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="1476e-129">See Also</span></span>  
 <span data-ttu-id="1476e-130">[恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="1476e-130">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="1476e-131">配置企业 SSO 使用 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="1476e-131">Configuring Enterprise SSO Using the BizTalk Server Configuration</span></span>](http://msdn.microsoft.com/library/f63d1aec-a8c7-4e76-a67f-19af69e252f0)