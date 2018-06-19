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
# <a name="operations-on-plsql-apis"></a>PL/SQL api 的操作
Oracle E-business Suite 提供一组形式的已打包的函数和存储的过程的 PL/SQL Api。 这些打包函数和过程作为中的操作进行展示[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。 

## <a name="plsql-apis-are-grouped-by-schema-names"></a>PL/SQL Api 分组的架构名称 
按下的架构名称分组 PL/SQL Api**基于项目的视图**和**基于架构的视图**节点时连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. 璝惠浏览中的 PL/SQL Api [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[浏览，搜索，以及元数据用于 Oracle E-business 操作](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]显示与 Oracle 数据库，以及在 Oracle E-business Suite 中的应用程序关联的 PL/SQL Api**基于项目的视图**和**基于架构的视图**节点。  
  
## <a name="important-info"></a>重要信息
  -   你可以执行与 Oracle E-business Suite 中的应用程序关联的 PL/SQL api 的操作之前，必须设置应用程序上下文。 这是因为设置应用程序上下文通过 Oracle E-business Suite 中的安全事务来促进设置 （例如责任、 组织和语言设置） 的用户首选项和项目的访问控制。 但是，它是可选若要将应用程序上下文设置为与 Oracle 数据库相关联的 PL/SQL Api。 请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  

-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]无法确定是否在 Oracle 中一个 PL/SQL API 中的参数分配默认值。  此外，该适配器还不能确定是否为必需或可选在 Oracle 中一个 PL/SQL API 中定义参数。 适配器将每个参数视为可选参数，并且如果没有值指定为参数的：  

    -   有一个 default 值中指定的 Oracle，则使用默认值。  
    -   被定义为引发 Oracle 然后异常中的必需参数。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)