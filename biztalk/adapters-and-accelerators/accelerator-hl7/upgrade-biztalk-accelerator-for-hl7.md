---
title: 升级 BizTalk Accelerator for HL7 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91b6747f-e560-4cf8-99b5-af0d150599bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 245d59e54a39cb77a71fc546920542619a4aeb3f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977638"
---
# <a name="upgrade-biztalk-accelerator-for-hl7"></a><span data-ttu-id="1dee1-102">升级 BizTalk Accelerator for HL7</span><span class="sxs-lookup"><span data-stu-id="1dee1-102">Upgrade BizTalk Accelerator for HL7</span></span>
<span data-ttu-id="1dee1-103">概述[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]升级过程。</span><span class="sxs-lookup"><span data-stu-id="1dee1-103">Overview of the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] upgrade process.</span></span> 

<a name="BKMK_BeforeUpgrade"></a>   
## <a name="before-you-upgrade"></a><span data-ttu-id="1dee1-104">升级之前需完成的操作</span><span class="sxs-lookup"><span data-stu-id="1dee1-104">Before you upgrade</span></span>  

- <span data-ttu-id="1dee1-105">运行升级的用户必须是 BizTalk Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="1dee1-105">The user running the upgrade must be a member of the BizTalk Administrators group.</span></span>  

- <span data-ttu-id="1dee1-106">当你执行升级时，必须运行 SQL Server (MSSQLSERVER) 服务。</span><span class="sxs-lookup"><span data-stu-id="1dee1-106">The SQL Server (MSSQLSERVER) service must be running when you perform an upgrade.</span></span>  

- <span data-ttu-id="1dee1-107">不要运行无提示安装中升级。</span><span class="sxs-lookup"><span data-stu-id="1dee1-107">Do not run a silent installation to upgrade.</span></span>  

- <span data-ttu-id="1dee1-108">安装程序升级时，迁移现有[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]到较新版本的配置信息。</span><span class="sxs-lookup"><span data-stu-id="1dee1-108">When you upgrade, the setup program migrates the existing [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] configuration information to the newer version.</span></span>  

- <span data-ttu-id="1dee1-109">升级时，注册表项和数据库会自动备份。</span><span class="sxs-lookup"><span data-stu-id="1dee1-109">When you upgrade, the registry keys and databases are automatically backed up.</span></span>  

- <span data-ttu-id="1dee1-110">中的文件*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for HL7 文件夹进行更新。</span><span class="sxs-lookup"><span data-stu-id="1dee1-110">The files in the *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7 folder are updated.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="1dee1-111">升级不会创建为升级后的文件中，新建一个文件夹，也不会更改现有文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="1dee1-111">The upgrade does not create a new folder for the upgraded files, nor does it change the name of the existing folder.</span></span>  

<a name="BKMK_UpgradePaths"></a>   
## <a name="supported-upgrade-paths"></a><span data-ttu-id="1dee1-112">支持的升级路径</span><span class="sxs-lookup"><span data-stu-id="1dee1-112">Supported Upgrade Paths</span></span>  
 <span data-ttu-id="1dee1-113">下表列出了受支持[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以升级的版本。</span><span class="sxs-lookup"><span data-stu-id="1dee1-113">The following table lists the supported [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] versions that can be upgraded.</span></span> <span data-ttu-id="1dee1-114">"是"表示[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]版本可以升级。</span><span class="sxs-lookup"><span data-stu-id="1dee1-114">“Yes” means the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] version can be upgraded.</span></span> <span data-ttu-id="1dee1-115">"否"表示[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]版本无法升级。</span><span class="sxs-lookup"><span data-stu-id="1dee1-115">“No” means the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] version cannot be upgraded.</span></span> <span data-ttu-id="1dee1-116">如果[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]版本未列出，该版本无法升级。</span><span class="sxs-lookup"><span data-stu-id="1dee1-116">If the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] version is not listed, that version cannot be upgraded.</span></span>  


|                                                                                              | [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)] | <span data-ttu-id="1dee1-117">BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dee1-117">BizTalk Server 2013</span></span> |
|----------------------------------------------------------------------------------------------|------------------------------------------------------|-------------------------------------------------------|---------------------|
| [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1dee1-118"> 2013</span><span class="sxs-lookup"><span data-stu-id="1dee1-118"> 2013</span></span> |                         <span data-ttu-id="1dee1-119">是</span><span class="sxs-lookup"><span data-stu-id="1dee1-119">Yes</span></span>                          |                          <span data-ttu-id="1dee1-120">是</span><span class="sxs-lookup"><span data-stu-id="1dee1-120">Yes</span></span>                          |         <span data-ttu-id="1dee1-121">“否”</span><span class="sxs-lookup"><span data-stu-id="1dee1-121">No</span></span>          |
| [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1dee1-122"> 2010</span><span class="sxs-lookup"><span data-stu-id="1dee1-122"> 2010</span></span> |                          <span data-ttu-id="1dee1-123">“否”</span><span class="sxs-lookup"><span data-stu-id="1dee1-123">No</span></span>                          |                          <span data-ttu-id="1dee1-124">是</span><span class="sxs-lookup"><span data-stu-id="1dee1-124">Yes</span></span>                          |         <span data-ttu-id="1dee1-125">是</span><span class="sxs-lookup"><span data-stu-id="1dee1-125">Yes</span></span>         |

<a name="BKMK_UpgradeSteps"></a>   
## <a name="upgrade-steps"></a><span data-ttu-id="1dee1-126">升级步骤</span><span class="sxs-lookup"><span data-stu-id="1dee1-126">Upgrade Steps</span></span>  

1. <span data-ttu-id="1dee1-127">升级[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1dee1-127">Upgrade the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>   

2. <span data-ttu-id="1dee1-128">备份[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]数据库和你 HL7 消息架构。</span><span class="sxs-lookup"><span data-stu-id="1dee1-128">Back up the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] databases and your HL7 message schemas.</span></span>  

3. <span data-ttu-id="1dee1-129">备份下的任何文件 ***\<驱动器\>*:\Program Files\Microsoft BizTalk Accelerator for HL7**已更改的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1dee1-129">Back up any files under the ***\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for HL7** folder that you have changed.</span></span> <span data-ttu-id="1dee1-130">例如，在 SDK 中的文件备份。</span><span class="sxs-lookup"><span data-stu-id="1dee1-130">For example, back up files in the SDK.</span></span>  

4. <span data-ttu-id="1dee1-131">安装你的版本的相应更新[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1dee1-131">Install the appropriate update for your version of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]:</span></span>  

   -   <span data-ttu-id="1dee1-132">如果从 BTAHL7 2010 进行升级，安装**HL72010Patch.msp**。</span><span class="sxs-lookup"><span data-stu-id="1dee1-132">If upgrading from BTAHL7 2010, install **HL72010Patch.msp**.</span></span>  

   -   <span data-ttu-id="1dee1-133">如果从 BTAHL7 2013 升级，安装**HL72013Patch.msp**。</span><span class="sxs-lookup"><span data-stu-id="1dee1-133">If upgrading from BTAHL7 2013, install **HL72013Patch.msp**.</span></span>  


5. <span data-ttu-id="1dee1-134">运行[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="1dee1-134">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] setup.</span></span> <span data-ttu-id="1dee1-135">请参阅[安装 BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。</span><span class="sxs-lookup"><span data-stu-id="1dee1-135">See [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  

6. <span data-ttu-id="1dee1-136">部署新 BTAHL7V2*x*常见的项目。</span><span class="sxs-lookup"><span data-stu-id="1dee1-136">Deploy the new BTAHL7V2*x*Common project.</span></span>  

7. <span data-ttu-id="1dee1-137">重新部署所有其他程序集。</span><span class="sxs-lookup"><span data-stu-id="1dee1-137">Redeploy all other assemblies.</span></span>  

8. <span data-ttu-id="1dee1-138">重建引用一个或多个 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 程序集的任何项目或程序集。</span><span class="sxs-lookup"><span data-stu-id="1dee1-138">Rebuild any projects or assemblies that have a reference to one or more of the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] assemblies.</span></span> <span data-ttu-id="1dee1-139">使用**BTSTask.exe**中\<*驱动器*\>: \Program Files\Microsoft BizTalk Server\<版本\>，请手动重新部署这些项目。</span><span class="sxs-lookup"><span data-stu-id="1dee1-139">Using **BTSTask.exe** in \<*drive*\>:\Program Files\Microsoft BizTalk Server \<version\>, manually redeploy these projects.</span></span>  

9. <span data-ttu-id="1dee1-140">重新启动 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="1dee1-140">Restart the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] service.</span></span>  

<a name="BKMK_UpgradeMulti"></a>   
## <a name="upgrading-in-a-multi-server-environment"></a><span data-ttu-id="1dee1-141">在多服务器环境中升级</span><span class="sxs-lookup"><span data-stu-id="1dee1-141">Upgrading in a Multi-server Environment</span></span>  
 <span data-ttu-id="1dee1-142">在多服务器[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]环境、 升级[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]s，然后再升级[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]所有服务器上。</span><span class="sxs-lookup"><span data-stu-id="1dee1-142">In a multi-server [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] environment, upgrade all [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]s, and then upgrade the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] on all servers.</span></span> <span data-ttu-id="1dee1-143">请按以下顺序迁移服务器：</span><span class="sxs-lookup"><span data-stu-id="1dee1-143">Migrate your servers in the following order:</span></span>  

-   <span data-ttu-id="1dee1-144">承载 BizTalk 组的服务器</span><span class="sxs-lookup"><span data-stu-id="1dee1-144">The server hosting the BizTalk Group</span></span>  

-   <span data-ttu-id="1dee1-145">各个处理节点</span><span class="sxs-lookup"><span data-stu-id="1dee1-145">Each processing node</span></span>  

-   <span data-ttu-id="1dee1-146">BAM 门户服务器</span><span class="sxs-lookup"><span data-stu-id="1dee1-146">The BAM portal server</span></span>  

## <a name="see-also"></a><span data-ttu-id="1dee1-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="1dee1-147">See Also</span></span>  
 [<span data-ttu-id="1dee1-148">安装 BizTalk Accelerator for HL7</span><span class="sxs-lookup"><span data-stu-id="1dee1-148">Install BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)