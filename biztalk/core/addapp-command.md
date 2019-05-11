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
ms.openlocfilehash: 4adefbfa2e2f9e92b606c9d46bd881b64ddd0864
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360988"
---
# <a name="addapp-command"></a><span data-ttu-id="73a94-102">AddApp 命令</span><span class="sxs-lookup"><span data-stu-id="73a94-102">AddApp Command</span></span>
<span data-ttu-id="73a94-103">在 BizTalk 管理数据库中创建新的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="73a94-103">Creates a new BizTalk application in the BizTalk Management database.</span></span> <span data-ttu-id="73a94-104">您可以在 BizTalk Server 管理控制台的应用程序节点中查看应用程序。</span><span class="sxs-lookup"><span data-stu-id="73a94-104">You can view the application in the Applications node of the BizTalk Server Administration console.</span></span> <span data-ttu-id="73a94-105">您可以将项目添加到应用程序使用 AddResource 命令，如中所述[AddResource 命令](../core/addresource-command.md)。</span><span class="sxs-lookup"><span data-stu-id="73a94-105">You can add artifacts to the application by using the AddResource command, as described in [AddResource Command](../core/addresource-command.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="73a94-106">用法</span><span class="sxs-lookup"><span data-stu-id="73a94-106">Usage</span></span>  
 <span data-ttu-id="73a94-107">**BTSTask AddApp /ApplicationName:** *value* [**/Description:**<em>value</em>] [**/Default**] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="73a94-107">**BTSTask AddApp /ApplicationName:** *value* [**/Description:**<em>value</em>] [**/Default**] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="73a94-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="73a94-108">Parameters</span></span>  
  
|<span data-ttu-id="73a94-109">参数</span><span class="sxs-lookup"><span data-stu-id="73a94-109">Parameter</span></span>|<span data-ttu-id="73a94-110">Required</span><span class="sxs-lookup"><span data-stu-id="73a94-110">Required</span></span>|<span data-ttu-id="73a94-111">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="73a94-111">Value</span></span>|  
|---------------|--------------|-----------|  
|<span data-ttu-id="73a94-112">**/ ApplicationName** (或 **/A**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="73a94-112">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="73a94-113">是</span><span class="sxs-lookup"><span data-stu-id="73a94-113">Yes</span></span>|<span data-ttu-id="73a94-114">若要添加的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="73a94-114">Name of the BizTalk application to add.</span></span> <span data-ttu-id="73a94-115">如果应用程序名称包含空格，则必须放在双引号 （"） 中。</span><span class="sxs-lookup"><span data-stu-id="73a94-115">If the application name includes spaces, it must be enclosed in double quotation marks (").</span></span>|  
|<span data-ttu-id="73a94-116">**/ 默认**(或 **/Def**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="73a94-116">**/Default** (or **/Def**, see Remarks)</span></span>|<span data-ttu-id="73a94-117">否</span><span class="sxs-lookup"><span data-stu-id="73a94-117">No</span></span>|<span data-ttu-id="73a94-118">如果指定，使新的应用程序的 BizTalk 组的默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="73a94-118">When specified, makes the new application the default application for the BizTalk group.</span></span>|  
|<span data-ttu-id="73a94-119">**/ 描述**(或 **/Des**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="73a94-119">**/Description** (or **/Des**, see Remarks)</span></span>|<span data-ttu-id="73a94-120">否</span><span class="sxs-lookup"><span data-stu-id="73a94-120">No</span></span>|<span data-ttu-id="73a94-121">应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="73a94-121">Description of the application.</span></span> <span data-ttu-id="73a94-122">必须括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="73a94-122">Must be enclosed in double quotation marks (").</span></span>|  
|<span data-ttu-id="73a94-123">**/ 服务器**(或 **/S**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="73a94-123">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="73a94-124">否</span><span class="sxs-lookup"><span data-stu-id="73a94-124">No</span></span>|<span data-ttu-id="73a94-125">承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="73a94-125">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="73a94-126">实例名称仅是所需的实例名称不同于服务器名称时。</span><span class="sxs-lookup"><span data-stu-id="73a94-126">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="73a94-127">端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。</span><span class="sxs-lookup"><span data-stu-id="73a94-127">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="73a94-128">示例：</span><span class="sxs-lookup"><span data-stu-id="73a94-128">Examples:</span></span><br /><br /> <span data-ttu-id="73a94-129">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="73a94-129">Server=MyServer</span></span><br /><br /> <span data-ttu-id="73a94-130">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="73a94-130">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="73a94-131">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="73a94-131">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="73a94-132">**/ 数据库**(或 **/Da**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="73a94-132">**/Database** (or **/Da**, see Remarks)</span></span>|<span data-ttu-id="73a94-133">否</span><span class="sxs-lookup"><span data-stu-id="73a94-133">No</span></span>|<span data-ttu-id="73a94-134">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="73a94-134">Name of the BizTalk Management database.</span></span> <span data-ttu-id="73a94-135">如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="73a94-135">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="73a94-136">示例</span><span class="sxs-lookup"><span data-stu-id="73a94-136">Sample</span></span>  
 <span data-ttu-id="73a94-137">**AddApp /ApplicationName:MyApplication /Description:"My BizTalk application"**</span><span class="sxs-lookup"><span data-stu-id="73a94-137">**AddApp /ApplicationName:MyApplication /Description:"My BizTalk application"**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73a94-138">备注</span><span class="sxs-lookup"><span data-stu-id="73a94-138">Remarks</span></span>  
 <span data-ttu-id="73a94-139">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="73a94-139">Parameters are not case-sensitive.</span></span> <span data-ttu-id="73a94-140">不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。</span><span class="sxs-lookup"><span data-stu-id="73a94-140">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a94-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="73a94-141">See Also</span></span>  
 <span data-ttu-id="73a94-142">[BTSTask 命令行参考](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="73a94-142">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="73a94-143">如何创建应用程序</span><span class="sxs-lookup"><span data-stu-id="73a94-143">How to Create an Application</span></span>](../core/how-to-create-an-application.md)