---
title: AddApp 命令 |Microsoft 文档
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
ms.openlocfilehash: 2a6b91faa406181db3e4195bf57baeb086a0b69e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229997"
---
# <a name="addapp-command"></a><span data-ttu-id="2691d-102">AddApp 命令</span><span class="sxs-lookup"><span data-stu-id="2691d-102">AddApp Command</span></span>
<span data-ttu-id="2691d-103">在 BizTalk 管理数据库中创建新的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2691d-103">Creates a new BizTalk application in the BizTalk Management database.</span></span> <span data-ttu-id="2691d-104">在 BizTalk Server 管理控制台的“应用程序”节点中可查看该应用程序。</span><span class="sxs-lookup"><span data-stu-id="2691d-104">You can view the application in the Applications node of the BizTalk Server Administration console.</span></span> <span data-ttu-id="2691d-105">你可以添加项目到应用程序使用 AddResource 命令中所述[AddResource 命令](../core/addresource-command.md)。</span><span class="sxs-lookup"><span data-stu-id="2691d-105">You can add artifacts to the application by using the AddResource command, as described in [AddResource Command](../core/addresource-command.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="2691d-106">用法</span><span class="sxs-lookup"><span data-stu-id="2691d-106">Usage</span></span>  
 <span data-ttu-id="2691d-107">**BTSTask AddApp /ApplicationName:** *值*[**/Description:***值*] [**/默认**] [**/服务器：***值*] [**/数据库：***值*]</span><span class="sxs-lookup"><span data-stu-id="2691d-107">**BTSTask AddApp /ApplicationName:** *value* [**/Description:***value*] [**/Default**] [**/Server:***value*] [**/Database:***value*]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="2691d-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="2691d-108">Parameters</span></span>  
  
|<span data-ttu-id="2691d-109">参数</span><span class="sxs-lookup"><span data-stu-id="2691d-109">Parameter</span></span>|<span data-ttu-id="2691d-110">必需</span><span class="sxs-lookup"><span data-stu-id="2691d-110">Required</span></span>|<span data-ttu-id="2691d-111">值</span><span class="sxs-lookup"><span data-stu-id="2691d-111">Value</span></span>|  
|---------------|--------------|-----------|  
|<span data-ttu-id="2691d-112">**/ ApplicationName** (或 **/A**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="2691d-112">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="2691d-113">是</span><span class="sxs-lookup"><span data-stu-id="2691d-113">Yes</span></span>|<span data-ttu-id="2691d-114">要添加的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="2691d-114">Name of the BizTalk application to add.</span></span> <span data-ttu-id="2691d-115">如果应用程序名称包含空格，它必须括在双引号 （"） 中。</span><span class="sxs-lookup"><span data-stu-id="2691d-115">If the application name includes spaces, it must be enclosed in double quotation marks (").</span></span>|  
|<span data-ttu-id="2691d-116">**/ 默认**(或 **/Def**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="2691d-116">**/Default** (or **/Def**, see Remarks)</span></span>|<span data-ttu-id="2691d-117">是</span><span class="sxs-lookup"><span data-stu-id="2691d-117">No</span></span>|<span data-ttu-id="2691d-118">如果指定，使新的应用程序的默认应用程序的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="2691d-118">When specified, makes the new application the default application for the BizTalk group.</span></span>|  
|<span data-ttu-id="2691d-119">**/ 说明**(或 **/Des**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="2691d-119">**/Description** (or **/Des**, see Remarks)</span></span>|<span data-ttu-id="2691d-120">是</span><span class="sxs-lookup"><span data-stu-id="2691d-120">No</span></span>|<span data-ttu-id="2691d-121">应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="2691d-121">Description of the application.</span></span> <span data-ttu-id="2691d-122">必须将其放在双引号 (") 中。</span><span class="sxs-lookup"><span data-stu-id="2691d-122">Must be enclosed in double quotation marks (").</span></span>|  
|<span data-ttu-id="2691d-123">**/ 服务器**(或 **/S**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="2691d-123">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="2691d-124">是</span><span class="sxs-lookup"><span data-stu-id="2691d-124">No</span></span>|<span data-ttu-id="2691d-125">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="2691d-125">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="2691d-126">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="2691d-126">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="2691d-127">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="2691d-127">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="2691d-128">示例：</span><span class="sxs-lookup"><span data-stu-id="2691d-128">Examples:</span></span><br /><br /> <span data-ttu-id="2691d-129">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="2691d-129">Server=MyServer</span></span><br /><br /> <span data-ttu-id="2691d-130">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="2691d-130">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="2691d-131">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="2691d-131">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="2691d-132">**/ 数据库**(或 **/Da**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="2691d-132">**/Database** (or **/Da**, see Remarks)</span></span>|<span data-ttu-id="2691d-133">是</span><span class="sxs-lookup"><span data-stu-id="2691d-133">No</span></span>|<span data-ttu-id="2691d-134">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="2691d-134">Name of the BizTalk Management database.</span></span> <span data-ttu-id="2691d-135">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="2691d-135">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="2691d-136">示例</span><span class="sxs-lookup"><span data-stu-id="2691d-136">Sample</span></span>  
 <span data-ttu-id="2691d-137">**AddApp /ApplicationName:MyApplication /Description:"我 BizTalk 应用程序"**</span><span class="sxs-lookup"><span data-stu-id="2691d-137">**AddApp /ApplicationName:MyApplication /Description:"My BizTalk application"**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2691d-138">注释</span><span class="sxs-lookup"><span data-stu-id="2691d-138">Remarks</span></span>  
 <span data-ttu-id="2691d-139">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="2691d-139">Parameters are not case-sensitive.</span></span> <span data-ttu-id="2691d-140">指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。</span><span class="sxs-lookup"><span data-stu-id="2691d-140">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2691d-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2691d-141">See Also</span></span>  
 <span data-ttu-id="2691d-142">[BTSTask 命令行参考](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2691d-142">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="2691d-143">如何创建应用程序</span><span class="sxs-lookup"><span data-stu-id="2691d-143">How to Create an Application</span></span>](../core/how-to-create-an-application.md)