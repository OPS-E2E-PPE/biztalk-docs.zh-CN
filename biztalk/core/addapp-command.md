---
title: AddApp 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 445784f1-505b-4259-a3f4-6f0d61578b1c
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb47b817c0f48cb82337afc6c82613fc35df28f6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986574"
---
# <a name="addapp-command"></a><span data-ttu-id="60ac9-102">AddApp 命令</span><span class="sxs-lookup"><span data-stu-id="60ac9-102">AddApp Command</span></span>
<span data-ttu-id="60ac9-103">在 BizTalk 管理数据库中创建新的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="60ac9-103">Creates a new BizTalk application in the BizTalk Management database.</span></span> <span data-ttu-id="60ac9-104">在 BizTalk Server 管理控制台的“应用程序”节点中可查看该应用程序。</span><span class="sxs-lookup"><span data-stu-id="60ac9-104">You can view the application in the Applications node of the BizTalk Server Administration console.</span></span> <span data-ttu-id="60ac9-105">您可以将项目添加到应用程序使用 AddResource 命令，如中所述[AddResource 命令](../core/addresource-command.md)。</span><span class="sxs-lookup"><span data-stu-id="60ac9-105">You can add artifacts to the application by using the AddResource command, as described in [AddResource Command](../core/addresource-command.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="60ac9-106">用法</span><span class="sxs-lookup"><span data-stu-id="60ac9-106">Usage</span></span>  
 <span data-ttu-id="60ac9-107">**BTSTask AddApp /ApplicationName:** *值*[**/Description:**<em>值</em>] [**/默认**] [**/服务器：**<em>值</em>] [**/database:**<em>值</em>]</span><span class="sxs-lookup"><span data-stu-id="60ac9-107">**BTSTask AddApp /ApplicationName:** *value* [**/Description:**<em>value</em>] [**/Default**] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="60ac9-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="60ac9-108">Parameters</span></span>  
  
|<span data-ttu-id="60ac9-109">参数</span><span class="sxs-lookup"><span data-stu-id="60ac9-109">Parameter</span></span>|<span data-ttu-id="60ac9-110">Required</span><span class="sxs-lookup"><span data-stu-id="60ac9-110">Required</span></span>|<span data-ttu-id="60ac9-111">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="60ac9-111">Value</span></span>|  
|---------------|--------------|-----------|  
|<span data-ttu-id="60ac9-112">**/ ApplicationName** (或 **/A**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="60ac9-112">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="60ac9-113">是</span><span class="sxs-lookup"><span data-stu-id="60ac9-113">Yes</span></span>|<span data-ttu-id="60ac9-114">若要添加的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="60ac9-114">Name of the BizTalk application to add.</span></span> <span data-ttu-id="60ac9-115">如果应用程序名称包含空格，则必须放在双引号 （"） 中。</span><span class="sxs-lookup"><span data-stu-id="60ac9-115">If the application name includes spaces, it must be enclosed in double quotation marks (").</span></span>|  
|<span data-ttu-id="60ac9-116">**/ 默认**(或 **/Def**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="60ac9-116">**/Default** (or **/Def**, see Remarks)</span></span>|<span data-ttu-id="60ac9-117">“否”</span><span class="sxs-lookup"><span data-stu-id="60ac9-117">No</span></span>|<span data-ttu-id="60ac9-118">如果指定，使新的应用程序的 BizTalk 组的默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="60ac9-118">When specified, makes the new application the default application for the BizTalk group.</span></span>|  
|<span data-ttu-id="60ac9-119">**/ 描述**(或 **/Des**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="60ac9-119">**/Description** (or **/Des**, see Remarks)</span></span>|<span data-ttu-id="60ac9-120">“否”</span><span class="sxs-lookup"><span data-stu-id="60ac9-120">No</span></span>|<span data-ttu-id="60ac9-121">应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="60ac9-121">Description of the application.</span></span> <span data-ttu-id="60ac9-122">必须将其放在双引号 (") 中。</span><span class="sxs-lookup"><span data-stu-id="60ac9-122">Must be enclosed in double quotation marks (").</span></span>|  
|<span data-ttu-id="60ac9-123">**/ 服务器**(或 **/S**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="60ac9-123">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="60ac9-124">“否”</span><span class="sxs-lookup"><span data-stu-id="60ac9-124">No</span></span>|<span data-ttu-id="60ac9-125">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="60ac9-125">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="60ac9-126">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="60ac9-126">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="60ac9-127">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="60ac9-127">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="60ac9-128">示例：</span><span class="sxs-lookup"><span data-stu-id="60ac9-128">Examples:</span></span><br /><br /> <span data-ttu-id="60ac9-129">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="60ac9-129">Server=MyServer</span></span><br /><br /> <span data-ttu-id="60ac9-130">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="60ac9-130">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="60ac9-131">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="60ac9-131">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="60ac9-132">**/ 数据库**(或 **/Da**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="60ac9-132">**/Database** (or **/Da**, see Remarks)</span></span>|<span data-ttu-id="60ac9-133">“否”</span><span class="sxs-lookup"><span data-stu-id="60ac9-133">No</span></span>|<span data-ttu-id="60ac9-134">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="60ac9-134">Name of the BizTalk Management database.</span></span> <span data-ttu-id="60ac9-135">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="60ac9-135">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="60ac9-136">示例</span><span class="sxs-lookup"><span data-stu-id="60ac9-136">Sample</span></span>  
 <span data-ttu-id="60ac9-137">**AddApp /ApplicationName:MyApplication /Description:"我 BizTalk 应用程序"**</span><span class="sxs-lookup"><span data-stu-id="60ac9-137">**AddApp /ApplicationName:MyApplication /Description:"My BizTalk application"**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60ac9-138">Remarks</span><span class="sxs-lookup"><span data-stu-id="60ac9-138">Remarks</span></span>  
 <span data-ttu-id="60ac9-139">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="60ac9-139">Parameters are not case-sensitive.</span></span> <span data-ttu-id="60ac9-140">指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。</span><span class="sxs-lookup"><span data-stu-id="60ac9-140">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60ac9-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="60ac9-141">See Also</span></span>  
 <span data-ttu-id="60ac9-142">[BTSTask 命令行参考](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="60ac9-142">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="60ac9-143">如何创建应用程序</span><span class="sxs-lookup"><span data-stu-id="60ac9-143">How to Create an Application</span></span>](../core/how-to-create-an-application.md)