---
title: ImportSettings 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 587f7e1f-9cf7-4e7b-90cd-11a266f474dc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 040e0d827fd8039433ed950119e6c7b2d0ee3a9b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332164"
---
# <a name="importsettings-command"></a><span data-ttu-id="cbb45-102">ImportSettings 命令</span><span class="sxs-lookup"><span data-stu-id="cbb45-102">ImportSettings Command</span></span>
<span data-ttu-id="cbb45-103">导入 BizTalk 组、 主机或主机实例设置从源 XML 文件配置数据库。</span><span class="sxs-lookup"><span data-stu-id="cbb45-103">Imports the BizTalk group, host, or host instance settings from a source XML file to the configuration database.</span></span> <span data-ttu-id="cbb45-104">设置映射以及映射 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="cbb45-104">The settings are mapped as they are in the mapping XML file.</span></span> <span data-ttu-id="cbb45-105">这些设置可能已导出中所述[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)或[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。</span><span class="sxs-lookup"><span data-stu-id="cbb45-105">These settings may have been exported as described in [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) or [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cbb45-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="cbb45-106">Prerequisites</span></span>  
 <span data-ttu-id="cbb45-107">若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="cbb45-107">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="cbb45-108">用法</span><span class="sxs-lookup"><span data-stu-id="cbb45-108">Usage</span></span>  
 `ImportSettings –Source:value –Map: value [-Server:value] [-Database:value]`  
  
## <a name="parameters"></a><span data-ttu-id="cbb45-109">Parameters</span><span class="sxs-lookup"><span data-stu-id="cbb45-109">Parameters</span></span>  
  
|<span data-ttu-id="cbb45-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="cbb45-110">**Parameter**</span></span>|<span data-ttu-id="cbb45-111">Required</span><span class="sxs-lookup"><span data-stu-id="cbb45-111">Required</span></span>|<span data-ttu-id="cbb45-112">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="cbb45-112">Value</span></span>|  
|-------------------|--------------|-----------|  
|<span data-ttu-id="cbb45-113">**-Source**</span><span class="sxs-lookup"><span data-stu-id="cbb45-113">**-Source**</span></span>|<span data-ttu-id="cbb45-114">是</span><span class="sxs-lookup"><span data-stu-id="cbb45-114">Yes</span></span>|<span data-ttu-id="cbb45-115">导出的设置 XML 文件的路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="cbb45-115">Path and file name of the exported settings XML file.</span></span>|  
|<span data-ttu-id="cbb45-116">**-Map**</span><span class="sxs-lookup"><span data-stu-id="cbb45-116">**-Map**</span></span>|<span data-ttu-id="cbb45-117">是</span><span class="sxs-lookup"><span data-stu-id="cbb45-117">Yes</span></span>|<span data-ttu-id="cbb45-118">映射 XML 文件的路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="cbb45-118">Path and file name of the mapping XML file.</span></span>|  
|<span data-ttu-id="cbb45-119">**-Server**</span><span class="sxs-lookup"><span data-stu-id="cbb45-119">**-Server**</span></span>|<span data-ttu-id="cbb45-120">可选</span><span class="sxs-lookup"><span data-stu-id="cbb45-120">Optional</span></span>|<span data-ttu-id="cbb45-121">承载 BizTalk 配置数据库的 SQL Server 计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="cbb45-121">The name of SQL Server computer hosting the BizTalk configuration database.</span></span>|  
|<span data-ttu-id="cbb45-122">**-Database**</span><span class="sxs-lookup"><span data-stu-id="cbb45-122">**-Database**</span></span>|<span data-ttu-id="cbb45-123">可选</span><span class="sxs-lookup"><span data-stu-id="cbb45-123">Optional</span></span>|<span data-ttu-id="cbb45-124">BizTalk 配置数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="cbb45-124">The name of the BizTalk configuration database.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="cbb45-125">示例</span><span class="sxs-lookup"><span data-stu-id="cbb45-125">Sample</span></span>  
 `BTSTask ImportSettings /Source:”C:\My Folder>\ExportedSettings.xml” /Map:Mappings.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a><span data-ttu-id="cbb45-126">备注</span><span class="sxs-lookup"><span data-stu-id="cbb45-126">Remarks</span></span>  
 <span data-ttu-id="cbb45-127">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="cbb45-127">Parameters are not case-sensitive.</span></span> <span data-ttu-id="cbb45-128">不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。</span><span class="sxs-lookup"><span data-stu-id="cbb45-128">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbb45-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="cbb45-129">See Also</span></span>  
 [<span data-ttu-id="cbb45-130">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="cbb45-130">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)