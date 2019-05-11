---
title: ListApps 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a5eb0af-e153-4639-a6c0-56c951827c7c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 253f3cb365a89a6753be559b42de3c80dde5479c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380655"
---
# <a name="listapps-command"></a><span data-ttu-id="6c5be-102">ListApps Command</span><span class="sxs-lookup"><span data-stu-id="6c5be-102">ListApps Command</span></span>
<span data-ttu-id="6c5be-103">名称和说明的所有指定的 BizTalk 管理数据库中的 BizTalk 应用程序将打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="6c5be-103">Prints to the console the name and description of all of the BizTalk applications in the specified BizTalk Management database.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="6c5be-104">用法</span><span class="sxs-lookup"><span data-stu-id="6c5be-104">Usage</span></span>  
 <span data-ttu-id="6c5be-105">**BTSTask ListApps** [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="6c5be-105">**BTSTask ListApps** [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="6c5be-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="6c5be-106">Parameters</span></span>  
  
|<span data-ttu-id="6c5be-107">参数</span><span class="sxs-lookup"><span data-stu-id="6c5be-107">Parameter</span></span>|<span data-ttu-id="6c5be-108">Required</span><span class="sxs-lookup"><span data-stu-id="6c5be-108">Required</span></span>|<span data-ttu-id="6c5be-109">Description</span><span class="sxs-lookup"><span data-stu-id="6c5be-109">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="6c5be-110">**/ 服务器**(或 **/S**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="6c5be-110">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="6c5be-111">否</span><span class="sxs-lookup"><span data-stu-id="6c5be-111">No</span></span>|<span data-ttu-id="6c5be-112">承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="6c5be-112">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="6c5be-113">实例名称仅是所需的实例名称不同于服务器名称时。</span><span class="sxs-lookup"><span data-stu-id="6c5be-113">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="6c5be-114">端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。</span><span class="sxs-lookup"><span data-stu-id="6c5be-114">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="6c5be-115">示例：</span><span class="sxs-lookup"><span data-stu-id="6c5be-115">Examples:</span></span><br /><br /> <span data-ttu-id="6c5be-116">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="6c5be-116">Server=MyServer</span></span><br /><br /> <span data-ttu-id="6c5be-117">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="6c5be-117">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="6c5be-118">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="6c5be-118">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="6c5be-119">**/ 数据库**(或 **/D**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="6c5be-119">**/Database** (or **/D**, see Remarks)</span></span>|<span data-ttu-id="6c5be-120">否</span><span class="sxs-lookup"><span data-stu-id="6c5be-120">No</span></span>|<span data-ttu-id="6c5be-121">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="6c5be-121">Name of the BizTalk Management database.</span></span> <span data-ttu-id="6c5be-122">如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="6c5be-122">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="6c5be-123">示例</span><span class="sxs-lookup"><span data-stu-id="6c5be-123">Sample</span></span>  
 <span data-ttu-id="6c5be-124">**BTSTask ListApps**</span><span class="sxs-lookup"><span data-stu-id="6c5be-124">**BTSTask ListApps**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c5be-125">备注</span><span class="sxs-lookup"><span data-stu-id="6c5be-125">Remarks</span></span>  
 <span data-ttu-id="6c5be-126">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="6c5be-126">Parameters are not case-sensitive.</span></span> <span data-ttu-id="6c5be-127">不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。</span><span class="sxs-lookup"><span data-stu-id="6c5be-127">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c5be-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c5be-128">See Also</span></span>  
 [<span data-ttu-id="6c5be-129">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="6c5be-129">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)