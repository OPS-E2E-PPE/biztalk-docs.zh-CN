---
title: ListApps 命令 |Microsoft 文档
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
ms.openlocfilehash: 785d98655cbe1ef32c00120dc1e54227717ebcae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262157"
---
# <a name="listapps-command"></a><span data-ttu-id="585af-102">ListApps 命令</span><span class="sxs-lookup"><span data-stu-id="585af-102">ListApps Command</span></span>
<span data-ttu-id="585af-103">用于将指定的 BizTalk 管理数据库中的所有 BizTalk 应用程序的名称和说明输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="585af-103">Prints to the console the name and description of all of the BizTalk applications in the specified BizTalk Management database.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="585af-104">用法</span><span class="sxs-lookup"><span data-stu-id="585af-104">Usage</span></span>  
 <span data-ttu-id="585af-105">**BTSTask ListApps** [**/Server:***值*] [**/数据库：***值*]</span><span class="sxs-lookup"><span data-stu-id="585af-105">**BTSTask ListApps** [**/Server:***value*] [**/Database:***value*]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="585af-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="585af-106">Parameters</span></span>  
  
|<span data-ttu-id="585af-107">参数</span><span class="sxs-lookup"><span data-stu-id="585af-107">Parameter</span></span>|<span data-ttu-id="585af-108">必需</span><span class="sxs-lookup"><span data-stu-id="585af-108">Required</span></span>|<span data-ttu-id="585af-109">Description</span><span class="sxs-lookup"><span data-stu-id="585af-109">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="585af-110">**/ 服务器**(或 **/S**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="585af-110">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="585af-111">是</span><span class="sxs-lookup"><span data-stu-id="585af-111">No</span></span>|<span data-ttu-id="585af-112">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="585af-112">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="585af-113">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="585af-113">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="585af-114">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="585af-114">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="585af-115">示例：</span><span class="sxs-lookup"><span data-stu-id="585af-115">Examples:</span></span><br /><br /> <span data-ttu-id="585af-116">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="585af-116">Server=MyServer</span></span><br /><br /> <span data-ttu-id="585af-117">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="585af-117">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="585af-118">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="585af-118">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="585af-119">**/ 数据库**(或 **/D**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="585af-119">**/Database** (or **/D**, see Remarks)</span></span>|<span data-ttu-id="585af-120">是</span><span class="sxs-lookup"><span data-stu-id="585af-120">No</span></span>|<span data-ttu-id="585af-121">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="585af-121">Name of the BizTalk Management database.</span></span> <span data-ttu-id="585af-122">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="585af-122">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="585af-123">示例</span><span class="sxs-lookup"><span data-stu-id="585af-123">Sample</span></span>  
 <span data-ttu-id="585af-124">**BTSTask ListApps**</span><span class="sxs-lookup"><span data-stu-id="585af-124">**BTSTask ListApps**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="585af-125">注释</span><span class="sxs-lookup"><span data-stu-id="585af-125">Remarks</span></span>  
 <span data-ttu-id="585af-126">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="585af-126">Parameters are not case-sensitive.</span></span> <span data-ttu-id="585af-127">指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。</span><span class="sxs-lookup"><span data-stu-id="585af-127">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="585af-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="585af-128">See Also</span></span>  
 [<span data-ttu-id="585af-129">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="585af-129">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)