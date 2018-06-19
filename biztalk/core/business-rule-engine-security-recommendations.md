---
title: 业务规则引擎安全建议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, business rules
- Business Rules Framework, security
- business rules, security
ms.assetid: d5df1cd0-112a-4c72-b95d-cbcd1bc6a2c3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d7402a1cc36ef3d9473c3303da79b0c23f46bf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231941"
---
# <a name="business-rule-engine-security-recommendations"></a><span data-ttu-id="eb674-102">业务规则引擎安全建议</span><span class="sxs-lookup"><span data-stu-id="eb674-102">Business Rule Engine Security Recommendations</span></span>
<span data-ttu-id="eb674-103">业务规则引擎是业务规则框架的运行时组件。</span><span class="sxs-lookup"><span data-stu-id="eb674-103">The Business Rule Engine is the runtime component of the Business Rule Framework.</span></span> <span data-ttu-id="eb674-104">使用业务规则框架，可以将可读性高、声明性强和语义丰富的规则连接到任何业务对象（.NET 组件）、XML 文档或数据库表。</span><span class="sxs-lookup"><span data-stu-id="eb674-104">With the Business Rule Framework, you can connect highly readable, declarative, semantically rich rules to any business objects (.NET components), XML documents, or database tables.</span></span> <span data-ttu-id="eb674-105">业务规则框架有关的详细信息，请参阅[创建和使用业务规则](../core/creating-and-using-business-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="eb674-105">For more information about the Business Rule Framework, see [Creating and Using Business Rules](../core/creating-and-using-business-rules.md).</span></span> <span data-ttu-id="eb674-106">有关业务规则引擎的详细信息，请参阅[规则引擎](../core/rule-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="eb674-106">For more information about the Business Rule Engine, see [Rule Engine](../core/rule-engine.md).</span></span>  
  
 <span data-ttu-id="eb674-107">业务规则引擎没有 Windows 用户组，而只有单个帐户。</span><span class="sxs-lookup"><span data-stu-id="eb674-107">There are no Windows user groups for the Business Rule Engine, only individual accounts.</span></span> <span data-ttu-id="eb674-108">BizTalk Server 使用两个 SQL Server 角色来限制对业务规则引擎资源的访问：</span><span class="sxs-lookup"><span data-stu-id="eb674-108">BizTalk Server restricts access to the Business Rule Engine resources by using two SQL Server roles:</span></span>  
  
 <span data-ttu-id="eb674-109">RE_Admin_Users SQL Server 角色是供需要在业务规则引擎中执行管理任务（如部署规则）的用户使用的。</span><span class="sxs-lookup"><span data-stu-id="eb674-109">The RE_Admin_Users SQL Server role is for users that need to perform administrative tasks in the Business Rule Engine, such as deploying rules.</span></span> <span data-ttu-id="eb674-110">RE_Admin_Users SQL Server 角色的成员包括 BizTalk 管理员。</span><span class="sxs-lookup"><span data-stu-id="eb674-110">Members of the RE_Admin_Users SQL Server role include BizTalk administrators.</span></span>  
  
 <span data-ttu-id="eb674-111">RE_Host_Users 组是供业务规则引擎的不需要管理用户权限并且执行读取和执行规则等任务的所有其他用户使用的。</span><span class="sxs-lookup"><span data-stu-id="eb674-111">The RE_Host_Users group is for all other users of the Business Rule Engine that do not require administrative user rights, and perform tasks such as reading and executing rules.</span></span> <span data-ttu-id="eb674-112">RE_Host_Users 角色的成员包括 BizTalk_Host_Users 角色。</span><span class="sxs-lookup"><span data-stu-id="eb674-112">Members of the RE_Host_Users role include the BizTalk_Host_Users role.</span></span> <span data-ttu-id="eb674-113">您可使用 SQL Server 角色来实现与 BizTalk Server 权限无关的针对业务规则引擎的权限。</span><span class="sxs-lookup"><span data-stu-id="eb674-113">You can use the SQL Server roles to implement permissions to the Business Rule Engine independent from the BizTalk Server permissions.</span></span> <span data-ttu-id="eb674-114">有关使用业务规则引擎所需的最小权限的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。</span><span class="sxs-lookup"><span data-stu-id="eb674-114">For more information about the minimum permission needed to use the Business Rule Engine, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span> <span data-ttu-id="eb674-115">建议您按照这些准则在您的环境中保护和部署业务规则引擎。</span><span class="sxs-lookup"><span data-stu-id="eb674-115">It is recommended you follow these guidelines for securing and deploying the Business Rule Engine in your environment.</span></span>  
  
-   <span data-ttu-id="eb674-116">BizTalk Server 为您用来安装更新服务的帐户授予“作为服务登录”权限，并将该帐户添加到业务规则数据库的 RE_Host_Users SQL Server 角色中。</span><span class="sxs-lookup"><span data-stu-id="eb674-116">BizTalk Server gives the account you used to install the update service logon as service rights and adds it to the RE_Host_Users SQL Server role on the Business Rule Engine database.</span></span> <span data-ttu-id="eb674-117">如果您安装时所用的帐户与将用以运行更新服务的帐户不同，则您必须从 RE_Host_Users SQL Server 角色删除该安装帐户。</span><span class="sxs-lookup"><span data-stu-id="eb674-117">If the account you use for installation is not the same you are going to use for running the update service, you must remove the installation account from the RE_Host_Users SQL Server role.</span></span>  
  
-   <span data-ttu-id="eb674-118">如果使用更新服务组件，则必须将其安装到所有 BizTalk 运行时计算机上。</span><span class="sxs-lookup"><span data-stu-id="eb674-118">If you use the Update service component, you must install it on all BizTalk runtime computers.</span></span> <span data-ttu-id="eb674-119">为了从规则引擎数据库检索规则，该更新服务需要模拟服务调用方。</span><span class="sxs-lookup"><span data-stu-id="eb674-119">In order to retrieve a rule from the Rule Engine database, the update service impersonates the caller of the service.</span></span>  
  
-   <span data-ttu-id="eb674-120">默认情况下，所有 BizTalk 主机对规则引擎项目具有相同的访问级别。</span><span class="sxs-lookup"><span data-stu-id="eb674-120">By default, all BizTalk Hosts have the same level of access to rules engine artifacts.</span></span> <span data-ttu-id="eb674-121">并没有为了安全而授予各个主机不同的访问级别。</span><span class="sxs-lookup"><span data-stu-id="eb674-121">There is not per-host segregation of security.</span></span> <span data-ttu-id="eb674-122">您可使用规则引擎 API 来配置基于策略的安全性。</span><span class="sxs-lookup"><span data-stu-id="eb674-122">You can configure per-policy security by using the rule engine APIs.</span></span> <span data-ttu-id="eb674-123">有关如何配置每个策略安全性的详细信息，请参阅[业务规则 Framework 安全性](../core/business-rules-framework-security.md)。</span><span class="sxs-lookup"><span data-stu-id="eb674-123">For more information about how to configure per-policy security, see [Business Rules Framework Security](../core/business-rules-framework-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb674-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb674-124">See Also</span></span>  
 [<span data-ttu-id="eb674-125">处理服务器的端口</span><span class="sxs-lookup"><span data-stu-id="eb674-125">Ports for the Processing Servers</span></span>](../core/ports-for-the-processing-servers.md)