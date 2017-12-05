---
title: "BtarnConfig |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTARN, exporting configuration data
- BTARN, BtarnConfig utility
- BtarnConfig utility
- BTARN, importing configuration data
ms.assetid: 8c95be2a-7df5-47fb-ae2d-64fa27e2811a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78ab62a86e97bf70e07629052a850b5aea2cee27
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="btarnconfig"></a><span data-ttu-id="abaf1-102">BtarnConfig</span><span class="sxs-lookup"><span data-stu-id="abaf1-102">BtarnConfig</span></span>
<span data-ttu-id="abaf1-103">使用 BtarnConfig 实用工具可以将配置数据导入或导出 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 环境。</span><span class="sxs-lookup"><span data-stu-id="abaf1-103">You use the BtarnConfig utility to import configuration data into, or export configuration data from, a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] environment.</span></span> <span data-ttu-id="abaf1-104">此处的配置数据是指用 BTARN 管理控制台设置的数据，包括流程配置设置、本组织、合作伙伴和协议。</span><span class="sxs-lookup"><span data-stu-id="abaf1-104">This configuration data is the data that you set by using the BTARN Management Console, including process configuration settings, home organizations, partners, and agreements.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="abaf1-105">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="abaf1-105">Location in SDK</span></span>  
 <span data-ttu-id="abaf1-106">\<*驱动器*\>\ Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>RosettaNet\SDK 快捷键</span><span class="sxs-lookup"><span data-stu-id="abaf1-106">\<*drive*\>\ Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for RosettaNet\SDK</span></span>  
  
## <a name="running-btarnconfig"></a><span data-ttu-id="abaf1-107">运行 BtarnConfig</span><span class="sxs-lookup"><span data-stu-id="abaf1-107">Running BtarnConfig</span></span>  
  
#### <a name="to-run-btarnconfig"></a><span data-ttu-id="abaf1-108">若要运行 BtarnConfig</span><span class="sxs-lookup"><span data-stu-id="abaf1-108">To run BtarnConfig</span></span>  
  
1.  <span data-ttu-id="abaf1-109">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="abaf1-109">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="abaf1-110">将移动到\<*驱动器*\>\ Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>Accelerator for RosettaNet\SDK\\。</span><span class="sxs-lookup"><span data-stu-id="abaf1-110">Move to \<*drive*\>\ Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
3.  <span data-ttu-id="abaf1-111">在命令提示符处，键入**BtarnConfig**，键入相应的开关，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="abaf1-111">At the command prompt, type **BtarnConfig**, type the appropriate switches, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="abaf1-112">下面的部分描述这些开关。</span><span class="sxs-lookup"><span data-stu-id="abaf1-112">The following section describes the switches.</span></span>  
  
## <a name="syntax-for-btarnconfig"></a><span data-ttu-id="abaf1-113">BtarnConfig 的语法</span><span class="sxs-lookup"><span data-stu-id="abaf1-113">Syntax for BtarnConfig</span></span>  
 <span data-ttu-id="abaf1-114">下面给出了用于启动此命令行工具的语法：</span><span class="sxs-lookup"><span data-stu-id="abaf1-114">The following shows the syntax that you use to start this command-line tool:</span></span>  
  
### <a name="syntax-for-importing-configuration-data"></a><span data-ttu-id="abaf1-115">导入配置数据的语法</span><span class="sxs-lookup"><span data-stu-id="abaf1-115">Syntax for Importing Configuration Data</span></span>  
  
```  
BTARNCONFIG /IMPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  
  
### <a name="syntax-for-exporting-configuration-data"></a><span data-ttu-id="abaf1-116">导出配置数据的语法</span><span class="sxs-lookup"><span data-stu-id="abaf1-116">Syntax for Exporting Configuration Data</span></span>  
  
```  
BTARNCONFIG /EXPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  
  
### <a name="syntax-description"></a><span data-ttu-id="abaf1-117">语法说明</span><span class="sxs-lookup"><span data-stu-id="abaf1-117">Syntax Description</span></span>  
 <span data-ttu-id="abaf1-118">下表描述了 BtarnConfig 实用工具使用的语法的各个部分。</span><span class="sxs-lookup"><span data-stu-id="abaf1-118">The following table describes each part of the syntax that the BtarnConfig utility uses.</span></span>  
  
|<span data-ttu-id="abaf1-119">语法</span><span class="sxs-lookup"><span data-stu-id="abaf1-119">Syntax</span></span>|<span data-ttu-id="abaf1-120">Description</span><span class="sxs-lookup"><span data-stu-id="abaf1-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="abaf1-121">\<*filename*.xml\></span><span class="sxs-lookup"><span data-stu-id="abaf1-121">\<*filename*.xml\></span></span>|<span data-ttu-id="abaf1-122">要导入或导出的文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="abaf1-122">Full path of the file to import into or export from.</span></span> <span data-ttu-id="abaf1-123">如果你不提供的路径，BTARN 假定该路径\<*驱动器*\>\ Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>RosettaNet 快捷键\SDK。</span><span class="sxs-lookup"><span data-stu-id="abaf1-123">If you do not provide a path, BTARN assumes that the path is \<*drive*\>\ Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for RosettaNet\SDK.</span></span>|  
|<span data-ttu-id="abaf1-124">**/ 导入**</span><span class="sxs-lookup"><span data-stu-id="abaf1-124">**/IMPORT**</span></span>|<span data-ttu-id="abaf1-125">导入 XML 数据从\< *filename*.xml\>到 BTARN 配置。</span><span class="sxs-lookup"><span data-stu-id="abaf1-125">Imports the XML data from \<*filename*.xml\> into the BTARN configuration.</span></span>|  
|<span data-ttu-id="abaf1-126">**/ 导出**</span><span class="sxs-lookup"><span data-stu-id="abaf1-126">**/EXPORT**</span></span>|<span data-ttu-id="abaf1-127">将 BTARN 配置导出到 XML 数据作为\< *filename*.xml\>。</span><span class="sxs-lookup"><span data-stu-id="abaf1-127">Exports the BTARN configuration as XML data into \<*filename*.xml\>.</span></span>|  
|<span data-ttu-id="abaf1-128">**/H**</span><span class="sxs-lookup"><span data-stu-id="abaf1-128">**/H**</span></span>|<span data-ttu-id="abaf1-129">导入或导出本组织配置数据。</span><span class="sxs-lookup"><span data-stu-id="abaf1-129">Imports or exports home-organization configuration data.</span></span>|  
|<span data-ttu-id="abaf1-130">**/ P**</span><span class="sxs-lookup"><span data-stu-id="abaf1-130">**/P**</span></span>|<span data-ttu-id="abaf1-131">导入或导出合作伙伴配置数据。</span><span class="sxs-lookup"><span data-stu-id="abaf1-131">Imports or exports partner configuration data.</span></span>|  
|<span data-ttu-id="abaf1-132">**/R**</span><span class="sxs-lookup"><span data-stu-id="abaf1-132">**/R**</span></span>|<span data-ttu-id="abaf1-133">导入或导出流程配置数据。</span><span class="sxs-lookup"><span data-stu-id="abaf1-133">Imports or exports process configuration data.</span></span>|  
|<span data-ttu-id="abaf1-134">**/ A**</span><span class="sxs-lookup"><span data-stu-id="abaf1-134">**/A**</span></span>|<span data-ttu-id="abaf1-135">导入或导出协议配置数据。</span><span class="sxs-lookup"><span data-stu-id="abaf1-135">Imports or exports agreement configuration data.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abaf1-136">注释</span><span class="sxs-lookup"><span data-stu-id="abaf1-136">Remarks</span></span>  
 <span data-ttu-id="abaf1-137">如果未提供任何一种**/H**， **/P**， **/R**，或**/A**切换的 BtarnConfig 实用程序导入或导出的所有数据。</span><span class="sxs-lookup"><span data-stu-id="abaf1-137">If you do not provide any one of the **/H**, **/P**, **/R**, or **/A** switches, the BtarnConfig utility imports or exports all the data.</span></span> <span data-ttu-id="abaf1-138">导出一个操作中的所有数据时，BtarnConfig 会将数据导出到 XML 文件中按以下顺序： 家庭组织、 合作伙伴、 过程配置和协议。</span><span class="sxs-lookup"><span data-stu-id="abaf1-138">When you export all the data in one operation, BtarnConfig exports the data into the XML file in the following order: home organizations, partners, process configuration, and agreements.</span></span>  
  
 <span data-ttu-id="abaf1-139">如果从中导入的文件存在结构性问题，BTARN 将会在架构验证阶段检测到错误，这样，在导入任何数据前，操作已失败。</span><span class="sxs-lookup"><span data-stu-id="abaf1-139">If there is a structural problem with the file that you are importing from, BTARN will detect the error during the schema validation stage, and the operation will fail before any data is imported.</span></span> <span data-ttu-id="abaf1-140">如果出现其他错误，例如尝试导入重复的项目或 PIP/协议需要 HTTPS，则导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="abaf1-140">If another error occurs, for example, you are trying to import a duplicate artifact or HTTPS is required for the PIP/agreement, then the import operation will fail.</span></span> <span data-ttu-id="abaf1-141">但是，在操作失败时已导入的所有数据将保留在配置中。</span><span class="sxs-lookup"><span data-stu-id="abaf1-141">However, all the data imported up to that point will remain in the configuration.</span></span>  
  
 <span data-ttu-id="abaf1-142">你必须是 BizTalk 管理员才能使用 BtarnConfig 导入或导出配置数据。</span><span class="sxs-lookup"><span data-stu-id="abaf1-142">You must be a BizTalk administrator to import or export configuration data using BtarnConfig.</span></span> <span data-ttu-id="abaf1-143">如果你不是 BizTalk 管理员，则由于访问权限问题某些导入操作可能会失败。</span><span class="sxs-lookup"><span data-stu-id="abaf1-143">If you are not a BizTalk administrator, some import operations may fail because of access issues.</span></span> <span data-ttu-id="abaf1-144">但是，同一 BtarnConfig 命令中的其他导入操作可能会成功。</span><span class="sxs-lookup"><span data-stu-id="abaf1-144">However,  other import operations in the same BtarnConfig command may succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abaf1-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abaf1-145">See Also</span></span>  
 [<span data-ttu-id="abaf1-146">实用工具</span><span class="sxs-lookup"><span data-stu-id="abaf1-146">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)