---
title: "ExportSettings 命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa34dab1-c854-473e-a693-43ba45624e16
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab8c39ef6903affbd2a1446bbde18a56e1a7778c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="exportsettings-command"></a><span data-ttu-id="2a2f3-102">ExportSettings 命令</span><span class="sxs-lookup"><span data-stu-id="2a2f3-102">ExportSettings Command</span></span>
<span data-ttu-id="2a2f3-103">使用 ExportSettings 命令可以将 BizTalk Server 配置数据库中的 BizTalk Server 设置导出到 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="2a2f3-103">The ExportSettings command nables you to export the BizTalk Server settings from a BizTalk Server configuration database to an XML file.</span></span> <span data-ttu-id="2a2f3-104">你可以然后导入这些设置另一个环境中所述[如何导入 BizTalk 设置使用设置仪表板](../core/how-to-import-biztalk-settings-using-settings-dashboard.md)或[如何导入 BizTalk 设置使用 BTSTask](../core/how-to-import-biztalk-settings-using-btstask.md)。</span><span class="sxs-lookup"><span data-stu-id="2a2f3-104">You can then import these settings in another environment as described in [How to Import BizTalk Settings Using Settings Dashboard](../core/how-to-import-biztalk-settings-using-settings-dashboard.md) or [How to Import BizTalk Settings Using BTSTask](../core/how-to-import-biztalk-settings-using-btstask.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2a2f3-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="2a2f3-105">Prerequisites</span></span>  
 <span data-ttu-id="2a2f3-106">若要执行此操作，则必须以 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="2a2f3-106">To perform this operation, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="2a2f3-107">用法</span><span class="sxs-lookup"><span data-stu-id="2a2f3-107">Usage</span></span>  
 `ExportSettings –Destination:value[-Server:value] [-Database:value]`  
  
## <a name="parameters"></a><span data-ttu-id="2a2f3-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="2a2f3-108">Parameters</span></span>  
  
|<span data-ttu-id="2a2f3-109">**参数**</span><span class="sxs-lookup"><span data-stu-id="2a2f3-109">**Parameter**</span></span>|<span data-ttu-id="2a2f3-110">必需</span><span class="sxs-lookup"><span data-stu-id="2a2f3-110">Required</span></span>|<span data-ttu-id="2a2f3-111">值</span><span class="sxs-lookup"><span data-stu-id="2a2f3-111">Value</span></span>|  
|-------------------|--------------|-----------|  
|<span data-ttu-id="2a2f3-112">**-目标**</span><span class="sxs-lookup"><span data-stu-id="2a2f3-112">**-Destination**</span></span>|<span data-ttu-id="2a2f3-113">是</span><span class="sxs-lookup"><span data-stu-id="2a2f3-113">Yes</span></span>|<span data-ttu-id="2a2f3-114">要写入的 XML 文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="2a2f3-114">Path and file name of the XML file to write.</span></span>|  
|<span data-ttu-id="2a2f3-115">**服务器**</span><span class="sxs-lookup"><span data-stu-id="2a2f3-115">**-Server**</span></span>|<span data-ttu-id="2a2f3-116">可选</span><span class="sxs-lookup"><span data-stu-id="2a2f3-116">Optional</span></span>|<span data-ttu-id="2a2f3-117">承载 BizTalk 配置数据库的 SQL Server 的名称。</span><span class="sxs-lookup"><span data-stu-id="2a2f3-117">The name of SQL Server hosting the BizTalk configuration database.</span></span>|  
|<span data-ttu-id="2a2f3-118">**数据库**</span><span class="sxs-lookup"><span data-stu-id="2a2f3-118">**-Database**</span></span>|<span data-ttu-id="2a2f3-119">可选</span><span class="sxs-lookup"><span data-stu-id="2a2f3-119">Optional</span></span>|<span data-ttu-id="2a2f3-120">BizTalk 配置数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="2a2f3-120">The name of the BizTalk configuration database.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="2a2f3-121">示例</span><span class="sxs-lookup"><span data-stu-id="2a2f3-121">Sample</span></span>  
 `BTSTask ExportSettings /Destination:MyFile.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a><span data-ttu-id="2a2f3-122">注释</span><span class="sxs-lookup"><span data-stu-id="2a2f3-122">Remarks</span></span>  
 <span data-ttu-id="2a2f3-123">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="2a2f3-123">Parameters are not case-sensitive.</span></span> <span data-ttu-id="2a2f3-124">指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。</span><span class="sxs-lookup"><span data-stu-id="2a2f3-124">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a2f3-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a2f3-125">See Also</span></span>  
 [<span data-ttu-id="2a2f3-126">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="2a2f3-126">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)