---
title: 对 PL SQL Api 的操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d47b894d-1047-48ed-8f8c-865c343a12db
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5462bc4b4d6ee6a55e0e14d3ca9fccabc4dc2daf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216005"
---
# <a name="operations-on-plsql-apis"></a><span data-ttu-id="98cc7-102">PL/SQL api 的操作</span><span class="sxs-lookup"><span data-stu-id="98cc7-102">Operations on PL/SQL APIs</span></span>
<span data-ttu-id="98cc7-103">Oracle E-business Suite 提供一组形式的已打包的函数和存储的过程的 PL/SQL Api。</span><span class="sxs-lookup"><span data-stu-id="98cc7-103">Oracle E-Business Suite provides a set of PL/SQL APIs in the form of packaged functions and stored procedures.</span></span> <span data-ttu-id="98cc7-104">这些打包函数和过程作为中的操作进行展示[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="98cc7-104">These packaged functions and procedures are surfaced as operations in [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].</span></span> 

## <a name="plsql-apis-are-grouped-by-schema-names"></a><span data-ttu-id="98cc7-105">PL/SQL Api 分组的架构名称</span><span class="sxs-lookup"><span data-stu-id="98cc7-105">PL/SQL APIs are grouped by schema names</span></span> 
<span data-ttu-id="98cc7-106">按下的架构名称分组 PL/SQL Api**基于项目的视图**和**基于架构的视图**节点时连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98cc7-106">The PL/SQL APIs are grouped by schema names under the **Artifact-Based View** and **Schema-Based View** nodes when you connect to Oracle E-Business Suite using [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] or  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="98cc7-107">璝惠浏览中的 PL/SQL Api [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[浏览，搜索，以及元数据用于 Oracle E-business 操作](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="98cc7-107">For information about browsing the PL/SQL APIs in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [Browse, Search, and get Metadata for Oracle E-Business Operations](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).</span></span>  
  
 <span data-ttu-id="98cc7-108">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]显示与 Oracle 数据库，以及在 Oracle E-business Suite 中的应用程序关联的 PL/SQL Api**基于项目的视图**和**基于架构的视图**节点。</span><span class="sxs-lookup"><span data-stu-id="98cc7-108">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] displays the PL/SQL APIs associated with the Oracle database as well as the applications in Oracle E-Business Suite under the **Artifact-Based View** and **Schema-Based View** nodes.</span></span>  
  
## <a name="important-info"></a><span data-ttu-id="98cc7-109">重要信息</span><span class="sxs-lookup"><span data-stu-id="98cc7-109">Important info</span></span>
  -   <span data-ttu-id="98cc7-110">你可以执行与 Oracle E-business Suite 中的应用程序关联的 PL/SQL api 的操作之前，必须设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="98cc7-110">Before you can perform operations on PL/SQL APIs associated with applications in Oracle E-Business Suite, you must set the applications context.</span></span> <span data-ttu-id="98cc7-111">这是因为设置应用程序上下文通过 Oracle E-business Suite 中的安全事务来促进设置 （例如责任、 组织和语言设置） 的用户首选项和项目的访问控制。</span><span class="sxs-lookup"><span data-stu-id="98cc7-111">This is because setting applications context facilitates secure transactions in Oracle E-Business Suite by setting user preferences (such as responsibility, organization, and language settings) and access control for an artifact.</span></span> <span data-ttu-id="98cc7-112">但是，它是可选若要将应用程序上下文设置为与 Oracle 数据库相关联的 PL/SQL Api。</span><span class="sxs-lookup"><span data-stu-id="98cc7-112">However, it is optional to set the applications context for PL/SQL APIs associated with Oracle database.</span></span> <span data-ttu-id="98cc7-113">请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="98cc7-113">See [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  

-   <span data-ttu-id="98cc7-114">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]无法确定是否在 Oracle 中一个 PL/SQL API 中的参数分配默认值。</span><span class="sxs-lookup"><span data-stu-id="98cc7-114">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] cannot ascertain whether or not a default value is assigned for a parameter in a PL/SQL API in Oracle.</span></span>  <span data-ttu-id="98cc7-115">此外，该适配器还不能确定是否为必需或可选在 Oracle 中一个 PL/SQL API 中定义参数。</span><span class="sxs-lookup"><span data-stu-id="98cc7-115">Moreover, the adapter also cannot ascertain whether a parameter is defined as mandatory or optional in a PL/SQL API in Oracle.</span></span> <span data-ttu-id="98cc7-116">适配器将每个参数视为可选参数，并且如果没有值指定为参数的：</span><span class="sxs-lookup"><span data-stu-id="98cc7-116">The adapter treats every parameter as an optional parameter, and if no value is specified for a parameter that:</span></span>  

    -   <span data-ttu-id="98cc7-117">有一个 default 值中指定的 Oracle，则使用默认值。</span><span class="sxs-lookup"><span data-stu-id="98cc7-117">Has a default value specified in Oracle then the default value is used.</span></span>  
    -   <span data-ttu-id="98cc7-118">被定义为引发 Oracle 然后异常中的必需参数。</span><span class="sxs-lookup"><span data-stu-id="98cc7-118">Is defined as a mandatory parameter in Oracle then an exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98cc7-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98cc7-119">See Also</span></span>  
 <span data-ttu-id="98cc7-120">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="98cc7-120">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>