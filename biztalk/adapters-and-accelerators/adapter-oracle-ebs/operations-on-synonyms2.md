---
title: 对 Synonyms2 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bc9b2c4-ac22-491b-bc64-95e08a39b74d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce9b6ef6415778f0c5d894f2fb4e14b4da87ffdc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005710"
---
# <a name="operations-on-synonyms"></a>对同义词的操作
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使您能够对同义词的操作。 同义词是别名或友好名称 （如表、 视图、 存储的过程、 函数和包） 的数据库对象。 有关在 Oracle 中的同义词的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=138058 ](http://go.microsoft.com/fwlink/?LinkId=138058)。  
  
## <a name="advantages-of-using-synonyms"></a>使用同义词的优点  
 同义词是在以下情况下有用：  
  
-   **使用不同的架构**： 如果你正在使用不同的架构，并且需要在架构之间访问的对象，您必须使用不同的 SQL 语句来访问这些对象。 可以在架构中创建对象的同义词，并在 SQL 语句中使用同义词，若要访问的对象。 如果需要访问不同架构中的基础对象，修改同义词以指向不同的架构中的对象的定义。 因此，基于针对同义词的应用程序仍然有效的 SQL 语句中未进行修改。  
  
     例如，假设测试和生产环境中有两个完全相同的架构:"Test"和"Prod"。 若要访问名为"Test"架构中的"Employee"的表，必须使用`Test.Employee`或`Employee`（如果"Test"的默认架构） 中 SQL 语句。 如果你想要在生产架构中使用"Employee"表，则现在必须使用`Prod.Employee`或`Employee`（将默认架构更改为"Prod"） 在 SQL 语句中。 若要解决此问题，可以创建"Test.Employee"表 (假设"EMP") 的同义词，然后在您的 SQL 语句中使用它。 无论何时需要对"Prod.Employee"表执行的操作，修改"EMP"同义词，使其指向"Prod.Employee"表的定义。 这可确保不需要修改您的 SQL 语句来执行不同的架构中的对象上的操作。  
  
-   **基础对象中的更改**: 同义词使您免受中的名称或在其正在执行的操作的基础对象的位置的任何更改。 您可以修改同义词定义以适应的名称或位置的基础对象中的任何更改。  
  
     例如，假设使用一个表中其中一个存储过程。 现在，如果表名称更改或表移动到其他某个位置然后你的存储的过程将停止工作。 若要解决此问题，可以在存储过程中，表使用同义词和更新同义词定义，如果中的名称或位置的表的更改。  
  
-   **简化、 安全地访问**： 在分布式环境中，您必须使用架构名称和对象名称以确保访问正确的对象。 此外，还必须确保用户拥有所需的目标对象的权限。 若要简化此操作，可以通过创建具有该对象的完全限定的路径的同义词来分配对象的简单名称，然后授予针对同义词的适当权限。  
  
## <a name="working-with-synonyms-in-the-adapter"></a>该适配器中使用同义词  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开在 Oracle 中的同义词：  
  
- 表  
  
- 视图  
  
- 存储过程  
  
- 函数  
  
- 包  
  
  这些项目的每个同义词公开与在各自的基础项目一起[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 例如，**表**节点下的**基于架构的视图**将显示在架构中，以及数据库表的表的所有同义词**视图**下的节点**基于架构的视图**将显示在架构中，以及数据库视图的视图的所有同义词，依此类推。  
  
- 创建表和视图的同义词，相同的操作公开基础表和视图分别。 例如，如果基础表和视图包含 LOB 列，这些表和视图的同义词将还公开 Read_\<LOBColName\>和 Update_\<LOBColName\>表同义词的操作和 Read_\<LOBColName\>视图同义词的操作。  
  
- 在存储的过程、 函数和包创建的同义词，同义词被称为操作以及各自的基础存储的过程、 函数和架构中的包。  
  
> [!NOTE]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持仅本地同义词。 这意味着仅这些同义词受目标本地服务器上的项目的适配器。  
  
 此外，针对同义词的消息操作都是相同的基础对象对其执行操作的项目名称除外。 例如，对于消息操作**选择**SCOTT 架构中的表上的操作是： `Tables/Select/SCOTT/[TABLE_NAME]`。 如果你执行针对同义词的选择操作，为相同表 SCOTT 架构中的消息操作将为： `Tables/Select/SCOTT/[SYNONYM_NAME]`。  
  
 当您调用在适配器中的同义词上的操作时，适配器将调用以执行此操作的 Oracle 数据库中的同义词。 但是，适配器使用的基础对象名称同义词定义中提取元数据。  
  
 可在正常的出站操作、 复合操作和轮询的同义词。  
  
> [!NOTE]
>  可以搜索中的同义词[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]就像其他对象。 但是，不能搜索过程中跳过级别节点中的同义词包就像在包内的过程。 有关搜索中适配器的操作的信息，请参阅[浏览、 搜索和获取 SQL 操作使用 SQL 适配器的元数据](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)