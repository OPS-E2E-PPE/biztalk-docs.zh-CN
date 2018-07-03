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
ms.openlocfilehash: 5719d74517331b30de986424bc14e7d01d128cf3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999342"
---
# <a name="operations-on-plsql-apis"></a>对 PL/SQL Api 的操作
Oracle E-business Suite 提供了一组封装的函数和存储的过程的窗体中的 PL/SQL Api。 这些打包函数和过程空间中的操作作为[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。 

## <a name="plsql-apis-are-grouped-by-schema-names"></a>按架构名称分组 PL/SQL Api 
按下的架构名称分组 PL/SQL Api**基于项目的视图**并**基于架构的视图**节点连接到 Oracle E-business Suite 使用时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. 有关浏览中的 PL/SQL Api 信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[浏览、 搜索和获取 Oracle E-business 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]显示与 Oracle 数据库，以及下的 Oracle E-business Suite 中的应用程序关联的 PL/SQL Api**基于项目的视图**并**基于架构的视图**节点。  
  
## <a name="important-info"></a>重要信息
  -   在可以执行对 Oracle E-business Suite 中的应用程序与关联的 PL/SQL Api 的操作之前，必须设置应用程序上下文。 这是因为设置应用程序上下文通过设置 （如责任、 组织和语言设置） 的用户首选项和某一项目的访问控制来帮助实现 Oracle E-business Suite 中的安全事务。 但是，是可选的设置与 Oracle 数据库相关联的 PL/SQL Api 的应用程序上下文。 请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  

- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不能确定是否在 Oracle 中的 PL/SQL API 中的参数分配默认值。  此外，适配器也不能确定是否为必需或可选在 Oracle 中的 PL/SQL API 中定义参数。 该适配器将每个参数视为可选参数，如果为某个参数指定任何值的：  

  -   具有默认值中指定的 Oracle，则使用默认值。  
  -   定义为引发 Oracle 然后异常中的必需参数。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)