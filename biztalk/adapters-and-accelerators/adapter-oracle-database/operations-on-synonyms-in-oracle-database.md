---
title: 对 Oracle 数据库中的同义词的操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 608e8c36-ac78-4d7d-aca4-be552505fc2b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 006107f5f21d017a79b7aa11f70fb1728bb5639a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214957"
---
# <a name="operations-on-synonyms-in-oracle-database"></a>对 Oracle 数据库中的同义词的操作
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]允许你执行对同义词的操作。 同义词是一个别名或数据库对象 （如表、 视图、 存储的过程、 函数和包） 的友好名称。 有关 Oracle 中的同义词的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=138058](http://go.microsoft.com/fwlink/?LinkId=138058)。  
  
## <a name="advantages-of-using-synonyms"></a>使用同义词的优点  
 同义词是在以下情况下有用：  
  
-   **使用不同的架构**： 如果你正在使用不同的架构，并需要在架构中访问的对象，你必须使用不同的 SQL 语句来访问这些对象。 可以在架构中创建对象的同义词，还可以在你的 SQL 语句中使用同义词访问的对象。 如果你需要访问不同架构中的基础对象，请修改该同义词以指向不同架构中对象的定义。 因此，基于该同义词的应用程序仍然有效的 SQL 语句中未进行修改。  
  
     例如，假设你有两个相同的架构针对你的测试和生产环境:"Test"和"Prod。" 若要访问"Test"架构中名为"Employee"的表，必须使用`Test.Employee`或`Employee`（如果"Test"的默认架构） 在 SQL 语句。 如果你想要在生产架构中使用"员工"表，则现在必须使用`Prod.Employee`或`Employee`（将默认架构更改为"Prod"） 在 SQL 语句。 若要获取解决此问题，可以创建"Test.Employee"表 (假设"EMP") 的同义词，然后在您的 SQL 语句中使用它。 无论何时需要对"Prod.Employee"表执行操作，修改"EMP"同义词，使其指向"Prod.Employee"表的定义。 这可确保不需要修改您的 SQL 语句来执行不同的架构中的对象上的操作。  
  
-   **基础对象中的更改**: 同义词使您免受中的名称或在其正在执行的操作的基础对象位置的任何更改。 你可以修改同义词定义以适应中的名称或基础对象的位置的任何更改。  
  
     例如，假设您使用其中一个存储过程中的表。 现在，如果表名称更改或表移到其他位置然后你的存储的过程将停止工作。 若要解决此问题，可以用于在存储过程中，表的同义词，并更新同义词定义，如果没有名称或表的位置中的更改。  
  
-   **简化、 安全地访问**： 在分布式环境中，必须使用以及对象名称的架构名称，以确保访问正确的对象。 此外，你还必须确保用户具有所需的目标对象的权限。 若要简化此操作，可以通过创建具有该对象的完整限定的路径的同义词将分配一个对象的简单名称，然后授予同义词上的适当权限。  
  
## <a name="working-with-synonyms-in-the-adapter"></a>适配器中使用同义词  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开中用于 Oracle 的同义词：  
  
-   表  
  
-   视图  
  
-   存储过程  
  
-   函数  
  
-   包  
  
 这些项目的每个同义词公开与中的相应基础项目一起[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 例如，**表**架构下的节点将显示在架构中，以及数据库表的表的所有同义词**视图**架构下的节点将都显示沿视图的所有同义词使用中的架构和等等的数据库视图。  
  
-   在表和视图上创建的同义词，相同的操作公开与基础表和视图分别。 例如，如果基础表和视图包含 LOB 列，这些表和视图的同义词将还会公开 ReadLOB 和 UpdateLOB 操作。  
  
-   创建存储的过程、 函数和包上的同义词，同义词作为以及各自的基础存储的过程、 函数和架构中的包的操作公开。  
  
> [!NOTE]
>  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持仅本地同义词。 这意味着仅这些同义词受目标本地服务器上的项目的适配器。  
  
 此外，同义词的消息操作并对其执行操作的项目名称除外的基础对象相同。 例如，有关的消息操作**选择**SCOTT 架构中的表上的操作是： `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/[TABLE_NAME]/Select`。 如果您正在执行同义词选择操作的相同的表在 SCOTT 架构中的消息操作将会： `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/[SYNONYM_NAME]/Select`。  
  
 在调用时执行的操作与适配器中的同义词，适配器将调用以执行此操作的 Oracle 数据库中的同义词。 但是，适配器使用的基础对象名称同义词定义中提取元数据。  
  
 可在正常的出站操作、 复合操作和轮询同义词。  
  
> [!NOTE]
>  你可以搜索中的同义词[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]就像其他对象。 但是，你不能搜索同义词包从跳过级别节点内的过程与可以在包内的过程一样的方式。 搜索与适配器中的操作有关的信息，请参阅[浏览，搜索，并为 Oracle 数据库操作获取元数据](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)