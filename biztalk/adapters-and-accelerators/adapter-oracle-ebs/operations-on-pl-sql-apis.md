---
title: 对 PL-SQL Api 操作 |Microsoft Docs
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
ms.openlocfilehash: c65a1a6313b70b03894c2d4adc41d7679d71b82c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375329"
---
# <a name="operations-on-plsql-apis"></a><span data-ttu-id="04a75-102">对 PL/SQL Api 的操作</span><span class="sxs-lookup"><span data-stu-id="04a75-102">Operations on PL/SQL APIs</span></span>
<span data-ttu-id="04a75-103">Oracle E-business Suite 提供了一组封装的函数和存储的过程的窗体中的 PL/SQL Api。</span><span class="sxs-lookup"><span data-stu-id="04a75-103">Oracle E-Business Suite provides a set of PL/SQL APIs in the form of packaged functions and stored procedures.</span></span> <span data-ttu-id="04a75-104">这些打包函数和过程空间中的操作作为[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="04a75-104">These packaged functions and procedures are surfaced as operations in [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].</span></span> 

## <a name="plsql-apis-are-grouped-by-schema-names"></a><span data-ttu-id="04a75-105">按架构名称分组 PL/SQL Api</span><span class="sxs-lookup"><span data-stu-id="04a75-105">PL/SQL APIs are grouped by schema names</span></span> 
<span data-ttu-id="04a75-106">按下的架构名称分组 PL/SQL Api**基于项目的视图**并**基于架构的视图**节点连接到 Oracle E-business Suite 使用时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04a75-106">The PL/SQL APIs are grouped by schema names under the **Artifact-Based View** and **Schema-Based View** nodes when you connect to Oracle E-Business Suite using [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] or  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="04a75-107">有关浏览中的 PL/SQL Api 信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[浏览、 搜索和获取 Oracle E-business 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="04a75-107">For information about browsing the PL/SQL APIs in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [Browse, Search, and get Metadata for Oracle E-Business Operations](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).</span></span>  
  
 <span data-ttu-id="04a75-108">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]显示与 Oracle 数据库，以及下的 Oracle E-business Suite 中的应用程序关联的 PL/SQL Api**基于项目的视图**并**基于架构的视图**节点。</span><span class="sxs-lookup"><span data-stu-id="04a75-108">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] displays the PL/SQL APIs associated with the Oracle database as well as the applications in Oracle E-Business Suite under the **Artifact-Based View** and **Schema-Based View** nodes.</span></span>  
  
## <a name="important-info"></a><span data-ttu-id="04a75-109">重要信息</span><span class="sxs-lookup"><span data-stu-id="04a75-109">Important info</span></span>
  -   <span data-ttu-id="04a75-110">在可以执行对 Oracle E-business Suite 中的应用程序与关联的 PL/SQL Api 的操作之前，必须设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="04a75-110">Before you can perform operations on PL/SQL APIs associated with applications in Oracle E-Business Suite, you must set the applications context.</span></span> <span data-ttu-id="04a75-111">这是因为设置应用程序上下文通过设置 （如责任、 组织和语言设置） 的用户首选项和某一项目的访问控制来帮助实现 Oracle E-business Suite 中的安全事务。</span><span class="sxs-lookup"><span data-stu-id="04a75-111">This is because setting applications context facilitates secure transactions in Oracle E-Business Suite by setting user preferences (such as responsibility, organization, and language settings) and access control for an artifact.</span></span> <span data-ttu-id="04a75-112">但是，是可选的设置与 Oracle 数据库相关联的 PL/SQL Api 的应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="04a75-112">However, it is optional to set the applications context for PL/SQL APIs associated with Oracle database.</span></span> <span data-ttu-id="04a75-113">请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="04a75-113">See [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  

- <span data-ttu-id="04a75-114">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不能确定是否在 Oracle 中的 PL/SQL API 中的参数分配默认值。</span><span class="sxs-lookup"><span data-stu-id="04a75-114">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] cannot ascertain whether or not a default value is assigned for a parameter in a PL/SQL API in Oracle.</span></span>  <span data-ttu-id="04a75-115">此外，适配器也不能确定是否为必需或可选在 Oracle 中的 PL/SQL API 中定义参数。</span><span class="sxs-lookup"><span data-stu-id="04a75-115">Moreover, the adapter also cannot ascertain whether a parameter is defined as mandatory or optional in a PL/SQL API in Oracle.</span></span> <span data-ttu-id="04a75-116">该适配器将每个参数视为可选参数，如果为某个参数指定任何值的：</span><span class="sxs-lookup"><span data-stu-id="04a75-116">The adapter treats every parameter as an optional parameter, and if no value is specified for a parameter that:</span></span>  

  -   <span data-ttu-id="04a75-117">具有默认值中指定的 Oracle，则使用默认值。</span><span class="sxs-lookup"><span data-stu-id="04a75-117">Has a default value specified in Oracle then the default value is used.</span></span>  
  -   <span data-ttu-id="04a75-118">定义为引发 Oracle 然后异常中的必需参数。</span><span class="sxs-lookup"><span data-stu-id="04a75-118">Is defined as a mandatory parameter in Oracle then an exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a75-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="04a75-119">See Also</span></span>  
 <span data-ttu-id="04a75-120">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="04a75-120">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>