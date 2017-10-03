---
title: "对 Oracle 数据库中的 BFILE 数据类型的表的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- operations, on tables with BFILE data types
- BFILE data type
- BFILE
ms.assetid: 7937564e-4423-459f-9824-6a27113ebfb3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c236651e6c44248ea8f6cf0f73f0c9bc17e46ac5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-tables-with-bfile-data-types-in-oracle-database"></a>对 Oracle 数据库中的 BFILE 数据类型的表的操作
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表和存储的过程中支持 BFILE 数据类型。 下表总结了 BFILE 数据类型公开的执行的操作所基于的适配器和 LOB 项目 （表/过程） 访问：  
  
|项目|运算|BFILE 列/param 的公开的数据类型|注释|  
|--------------|---------------|--------------------------------------------|--------------|  
|TABLE|Insert|字符串|表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径<br /><br /> 例如 MYDIR/screen.jpg MYDIR 所在 Oracle 中的逻辑目录|  
|TABLE|UPDATE|字符串|表示要插入 BFILE 列更新的文件的逻辑的 Oracle 目录路径|  
|TABLE|SELECT|byte[]|表示构成 BFILE 的二进制数据|  
|存储的过程|PARAM 中|字符串|表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径<br /><br /> 例如 MYDIR/screen.jpg MYDIR 所在 Oracle 中的逻辑目录|  
|存储的过程|OUT 参数|字符串|表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径<br /><br /> 例如 MYDIR/screen.jpg MYDIR 所在 Oracle 中的逻辑目录|  
|存储的过程|INOUT PARAM|不支持|-|  
  
 BFILE 数据类型的表上还支持特殊操作 ReadLOB。 不支持 UpdateLOB 操作。 适配器客户端或者可以使用更新操作。  
  
 有关详细信息：  
  
-   在通过使用包含 BFILE 数据类型的表上执行操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[BFILE 数据类型，使用 BizTalk Server 的 Oracle 数据库中使用运行对表的操作](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)