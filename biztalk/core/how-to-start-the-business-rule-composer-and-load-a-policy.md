---
title: "如何启动业务规则编辑器和加载策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, loading
- opening, Busines Rule Composer
- Business Rule Composer, policies
- Business Rule Composer, opening
ms.assetid: 34a6034d-90b3-4ce0-9770-3790763affe3
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 420517c51fd6c7a6c854afe161a11a58f952db83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-start-the-business-rule-composer-and-load-a-policy"></a><span data-ttu-id="43397-102">如何启动业务规则编辑器和加载策略</span><span class="sxs-lookup"><span data-stu-id="43397-102">How to Start the Business Rule Composer and Load a Policy</span></span>
<span data-ttu-id="43397-103">本部分将介绍如何启动业务规则编辑器和加载策略。</span><span class="sxs-lookup"><span data-stu-id="43397-103">This section describes how to start the Business Rule Composer and load a policy.</span></span>  
  
### <a name="to-start-the-business-rule-composer"></a><span data-ttu-id="43397-104">启动业务规则编辑器</span><span class="sxs-lookup"><span data-stu-id="43397-104">To start the Business Rule Composer</span></span>  
  
-   <span data-ttu-id="43397-105">上**启动**菜单上，指向**所有程序**，指向 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="43397-105">On the **Start** menu, point to **All Programs**, point to Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then click **Business Rule Composer**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="43397-106">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="43397-106">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="43397-107">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="43397-107">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
### <a name="to-load-a-policy"></a><span data-ttu-id="43397-108">加载策略</span><span class="sxs-lookup"><span data-stu-id="43397-108">To load a policy</span></span>  
  
1.  <span data-ttu-id="43397-109">业务规则编辑器，在上**规则存储**菜单上，单击**负载**。</span><span class="sxs-lookup"><span data-stu-id="43397-109">In the Business Rule Composer, on the **Rule Store** menu, click **Load**.</span></span>  
  
2.  <span data-ttu-id="43397-110">在**规则存储**对话框中，在**SQL Server**下拉列表中，选择你想要连接的 SQL Server™ 计算机。</span><span class="sxs-lookup"><span data-stu-id="43397-110">In the **Rule Store** dialog box, in the **SQL Server** drop-down list, select the SQL Server™ computer to which you want to connect.</span></span>  
  
3.  <span data-ttu-id="43397-111">在**数据库**下拉列表中，选择包含你想要打开规则存储的数据库。</span><span class="sxs-lookup"><span data-stu-id="43397-111">In the **Database** drop-down list, select the database that contains the rule store you want to open.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43397-112">安装的规则存储的默认数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是**BizTalkRuleEngineDb**。</span><span class="sxs-lookup"><span data-stu-id="43397-112">The default database for the rule store installed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is **BizTalkRuleEngineDb**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43397-113">如果你使用新创建的 SQL Server 帐户具有**强制密码过期**和**用户必须更改密码在下次登录**选项集，业务规则编辑器将无法连接到该规则引擎数据库。</span><span class="sxs-lookup"><span data-stu-id="43397-113">If you use a newly created SQL Server account that has the **Enforce password expiration** and **User must change password at next login** options set, the business rule composer will fail to connect to the Rule Engine database.</span></span>