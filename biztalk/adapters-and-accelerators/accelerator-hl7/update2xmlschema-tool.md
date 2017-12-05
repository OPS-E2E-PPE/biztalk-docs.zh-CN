---
title: "Update2XMLSchema 工具 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.XML schemas, Update2XMLSchema tool
- schemas, Update2XMLSchema tool
- Update2XMLSchema tool
- Update2XMLSchema tool, syntax
ms.assetid: fd861e2f-ebda-427f-bd52-a2f05b7e22da
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0f5a33b8951d1f02cf0504ba833b35adf275834
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="update2xmlschema-tool"></a><span data-ttu-id="0c8bb-102">Update2XMLSchema 工具</span><span class="sxs-lookup"><span data-stu-id="0c8bb-102">Update2XMLSchema Tool</span></span>
<span data-ttu-id="0c8bb-103">Update2XMLSchema 工具，可修改 HL7 2.XML 架构，若要使用 BizTalk 编辑器。</span><span class="sxs-lookup"><span data-stu-id="0c8bb-103">The Update2XMLSchema tool enables you to modify HL7 2.XML schemas to work with BizTalk Editor.</span></span> <span data-ttu-id="0c8bb-104">这是必需的因为某些 HL7 2.XML 架构不正确内工作[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]而不进行修改。</span><span class="sxs-lookup"><span data-stu-id="0c8bb-104">This is necessary because certain HL7 2.XML schemas do not work correctly within [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] without modification.</span></span> <span data-ttu-id="0c8bb-105">修改后的架构，该工具将它们放在架构文件夹其中[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]已安装，例如， *\<驱动器\>*: files\microsoft BizTalk\<版本\>HL7\Templates\Schemas 快捷键。</span><span class="sxs-lookup"><span data-stu-id="0c8bb-105">After modifying the schemas, the tool places them in the Schemas folder where [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] is installed, for instance, *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\Templates\Schemas.</span></span>  
  
 <span data-ttu-id="0c8bb-106">你需要更新手动因运行 Update2XMLSchema 工具的架构的某些字段。</span><span class="sxs-lookup"><span data-stu-id="0c8bb-106">You need to update manually some fields of the schemas that result from running the Update2XMLSchema tool.</span></span> <span data-ttu-id="0c8bb-107">请参阅[所需的手动更新](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)有关这些架构的列表。</span><span class="sxs-lookup"><span data-stu-id="0c8bb-107">See [Required Manual Updates](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) for a list of those schemas.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c8bb-108">语法</span><span class="sxs-lookup"><span data-stu-id="0c8bb-108">Syntax</span></span>  
 <span data-ttu-id="0c8bb-109">此工具位于*\<驱动器\>*: files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\2XML 实用程序。</span><span class="sxs-lookup"><span data-stu-id="0c8bb-109">This tool is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\2XML Utilities.</span></span> <span data-ttu-id="0c8bb-110">在命令提示符处使用以下命令运行此工具：</span><span class="sxs-lookup"><span data-stu-id="0c8bb-110">You run this tool at the command prompt with the following command:</span></span>  
  
```  
Update2XMLSchema /s /v  
```  
  
 <span data-ttu-id="0c8bb-111">下表列出了要使用此命令使用的参数。</span><span class="sxs-lookup"><span data-stu-id="0c8bb-111">The following table lists the parameters to use with this command.</span></span>  
  
|<span data-ttu-id="0c8bb-112">参数</span><span class="sxs-lookup"><span data-stu-id="0c8bb-112">Parameter</span></span>|<span data-ttu-id="0c8bb-113">Name</span><span class="sxs-lookup"><span data-stu-id="0c8bb-113">Name</span></span>|<span data-ttu-id="0c8bb-114">值</span><span class="sxs-lookup"><span data-stu-id="0c8bb-114">Value</span></span>|  
|---------------|----------|-----------|  
|<span data-ttu-id="0c8bb-115">*S*</span><span class="sxs-lookup"><span data-stu-id="0c8bb-115">*S*</span></span>|<span data-ttu-id="0c8bb-116">数据源</span><span class="sxs-lookup"><span data-stu-id="0c8bb-116">Source</span></span>|<span data-ttu-id="0c8bb-117">原始的 HL7 架构的完整路径</span><span class="sxs-lookup"><span data-stu-id="0c8bb-117">Full path of the original HL7 schemas</span></span>|  
|<span data-ttu-id="0c8bb-118">*V*</span><span class="sxs-lookup"><span data-stu-id="0c8bb-118">*V*</span></span>|<span data-ttu-id="0c8bb-119">版本</span><span class="sxs-lookup"><span data-stu-id="0c8bb-119">Version</span></span>|<span data-ttu-id="0c8bb-120">2.XML 架构的版本： 2.3.1、 2.4 或 2.5</span><span class="sxs-lookup"><span data-stu-id="0c8bb-120">The version of the 2.XML schemas:  either 2.3.1, 2.4, or 2.5</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0c8bb-121">示例</span><span class="sxs-lookup"><span data-stu-id="0c8bb-121">Example</span></span>  
  
-   <span data-ttu-id="0c8bb-122">如果你想要修改版本 2.3.1 2.XML 架构位于 c:\231XML\v231\xsd 目录，则可以在命令提示符下键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="0c8bb-122">If you want to modify version 2.3.1 2.XML schemas located in the c:\231XML\v231\xsd directory, you would type the following command at the command prompt:</span></span>  
  
```  
Update2XMLSchema /s c:\231XML\v231\xsd /v 2.3.1  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="0c8bb-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="0c8bb-123">In This Section</span></span>  
  
-   [<span data-ttu-id="0c8bb-124">需要手动更新</span><span class="sxs-lookup"><span data-stu-id="0c8bb-124">Required Manual Updates</span></span>](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)