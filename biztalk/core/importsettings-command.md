---
title: "ImportSettings 命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 587f7e1f-9cf7-4e7b-90cd-11a266f474dc
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c609634422f8c8b5f2c1a96691fe4eda708e5c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importsettings-command"></a><span data-ttu-id="0a8cb-102">ImportSettings 命令</span><span class="sxs-lookup"><span data-stu-id="0a8cb-102">ImportSettings Command</span></span>
<span data-ttu-id="0a8cb-103">将 BizTalk 组、主机或主机实例设置从 XML 源文件导入到配置数据库。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-103">Imports the BizTalk group, host, or host instance settings from a source XML file to the configuration database.</span></span> <span data-ttu-id="0a8cb-104">设置将按照映射 XML 文件中的方式进行映射。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-104">The settings are mapped as they are in the mapping XML file.</span></span> <span data-ttu-id="0a8cb-105">这些设置可能已导出中所述[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)或[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-105">These settings may have been exported as described in [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) or [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0a8cb-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="0a8cb-106">Prerequisites</span></span>  
 <span data-ttu-id="0a8cb-107">若要执行此操作，你必须作为 BizTalk Server Administrators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-107">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="0a8cb-108">用法</span><span class="sxs-lookup"><span data-stu-id="0a8cb-108">Usage</span></span>  
 `ImportSettings –Source:value –Map: value [-Server:value] [-Database:value]`  
  
## <a name="parameters"></a><span data-ttu-id="0a8cb-109">Parameters</span><span class="sxs-lookup"><span data-stu-id="0a8cb-109">Parameters</span></span>  
  
|<span data-ttu-id="0a8cb-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="0a8cb-110">**Parameter**</span></span>|<span data-ttu-id="0a8cb-111">必需</span><span class="sxs-lookup"><span data-stu-id="0a8cb-111">Required</span></span>|<span data-ttu-id="0a8cb-112">值</span><span class="sxs-lookup"><span data-stu-id="0a8cb-112">Value</span></span>|  
|-------------------|--------------|-----------|  
|<span data-ttu-id="0a8cb-113">**源代码**</span><span class="sxs-lookup"><span data-stu-id="0a8cb-113">**-Source**</span></span>|<span data-ttu-id="0a8cb-114">是</span><span class="sxs-lookup"><span data-stu-id="0a8cb-114">Yes</span></span>|<span data-ttu-id="0a8cb-115">导出的设置 XML 文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-115">Path and file name of the exported settings XML file.</span></span>|  
|<span data-ttu-id="0a8cb-116">**映射**</span><span class="sxs-lookup"><span data-stu-id="0a8cb-116">**-Map**</span></span>|<span data-ttu-id="0a8cb-117">是</span><span class="sxs-lookup"><span data-stu-id="0a8cb-117">Yes</span></span>|<span data-ttu-id="0a8cb-118">映射 XML 文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-118">Path and file name of the mapping XML file.</span></span>|  
|<span data-ttu-id="0a8cb-119">**服务器**</span><span class="sxs-lookup"><span data-stu-id="0a8cb-119">**-Server**</span></span>|<span data-ttu-id="0a8cb-120">可选</span><span class="sxs-lookup"><span data-stu-id="0a8cb-120">Optional</span></span>|<span data-ttu-id="0a8cb-121">托管 BizTalk 配置数据库的 SQL 服务器计算机名称。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-121">The name of SQL Server computer hosting the BizTalk configuration database.</span></span>|  
|<span data-ttu-id="0a8cb-122">**数据库**</span><span class="sxs-lookup"><span data-stu-id="0a8cb-122">**-Database**</span></span>|<span data-ttu-id="0a8cb-123">可选</span><span class="sxs-lookup"><span data-stu-id="0a8cb-123">Optional</span></span>|<span data-ttu-id="0a8cb-124">BizTalk 配置数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-124">The name of the BizTalk configuration database.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="0a8cb-125">示例</span><span class="sxs-lookup"><span data-stu-id="0a8cb-125">Sample</span></span>  
 `BTSTask ImportSettings /Source:”C:\My Folder>\ExportedSettings.xml” /Map:Mappings.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a><span data-ttu-id="0a8cb-126">注释</span><span class="sxs-lookup"><span data-stu-id="0a8cb-126">Remarks</span></span>  
 <span data-ttu-id="0a8cb-127">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-127">Parameters are not case-sensitive.</span></span> <span data-ttu-id="0a8cb-128">指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。</span><span class="sxs-lookup"><span data-stu-id="0a8cb-128">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a8cb-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a8cb-129">See Also</span></span>  
 [<span data-ttu-id="0a8cb-130">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="0a8cb-130">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)