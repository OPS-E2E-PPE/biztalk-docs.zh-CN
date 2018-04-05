---
title: 如何使用作为数据源的数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, data sources
ms.assetid: a68057ed-836f-499f-bb80-f644d81bcfc5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3a9201ee729288a819a3d527a6ecb4fefd32797
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-a-database-as-a-data-source"></a><span data-ttu-id="835b5-102">如何将数据库用作数据源</span><span class="sxs-lookup"><span data-stu-id="835b5-102">How to Use a Database as a Data Source</span></span>
<span data-ttu-id="835b5-103">您可以指定数据库作为数据源。</span><span class="sxs-lookup"><span data-stu-id="835b5-103">You can specify a database as a data source.</span></span> <span data-ttu-id="835b5-104">随后，您可从该数据库中选择表或表列，并将其拖至词汇定义或规则上以用作事实。</span><span class="sxs-lookup"><span data-stu-id="835b5-104">You can subsequently select a table or table column from the database, and drag it onto a vocabulary definition or rule to use as a fact.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="835b5-105">你可以选择将绑定到使用数据库行/表**该组**或**TypedDataTable**通过选择"数据连接"数据库表/行"**数据库绑定类型**性的属性窗口中的下拉列表框**数据库**事实浏览器选项卡。</span><span class="sxs-lookup"><span data-stu-id="835b5-105">You can choose to bind to the database row/table using either **DataConnection** or **TypedDataTable** by selecting "Data connection" or "Database table/row" from the **Database binding type** drop-down box in the Property Window for the **Databases** tab of Fact Explorer.</span></span> <span data-ttu-id="835b5-106">**数据连接**默认情况下使用绑定。</span><span class="sxs-lookup"><span data-stu-id="835b5-106">**DataConnection** binding is used by default.</span></span>  
  
### <a name="to-specify-a-sql-database-as-a-data-source"></a><span data-ttu-id="835b5-107">指定 SQL 数据库作为数据源</span><span class="sxs-lookup"><span data-stu-id="835b5-107">To specify a SQL database as a data source</span></span>  
  
1.  <span data-ttu-id="835b5-108">在事实浏览器窗口中，单击**数据库**选项卡。</span><span class="sxs-lookup"><span data-stu-id="835b5-108">In the Facts Explorer window, click the **Databases** tab.</span></span>  
  
2.  <span data-ttu-id="835b5-109">右键单击**服务器**节点，，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="835b5-109">Right-click the **Servers** node, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="835b5-110">在下拉列表中选择一个可用的数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="835b5-110">In the drop-down list, select an available database server.</span></span>  
  
4.  <span data-ttu-id="835b5-111">选择身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="835b5-111">Select an authentication type.</span></span> <span data-ttu-id="835b5-112">如果您选择 SQL 身份验证，请输入登录名和密码。</span><span class="sxs-lookup"><span data-stu-id="835b5-112">If you select SQL authentication, enter a logon name and password.</span></span> <span data-ttu-id="835b5-113">输入你的身份验证信息后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="835b5-113">When you have entered your authentication information, click **OK**.</span></span>  
  
     <span data-ttu-id="835b5-114">![树浏览器支持的数据库的屏幕截图。] (../core/media/ebiz-dbbrows.gif "ebiz_dbbrows")</span><span class="sxs-lookup"><span data-stu-id="835b5-114">![Screenshot of databases of tree brower.](../core/media/ebiz-dbbrows.gif "ebiz_dbbrows")</span></span>  
<span data-ttu-id="835b5-115">浏览数据库</span><span class="sxs-lookup"><span data-stu-id="835b5-115">Browsing a database</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="835b5-116">不支持 SQL Server 数据库视图。</span><span class="sxs-lookup"><span data-stu-id="835b5-116">SQL Server database views are not supported.</span></span>