---
title: 对包含 BFILE 数据类型在 Oracle 数据库中的表的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, on tables with BFILE data types
- BFILE data type
- BFILE
ms.assetid: 7937564e-4423-459f-9824-6a27113ebfb3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab9885497468f91b309eb51ac0abbf4c0807ca76
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998254"
---
# <a name="operations-on-tables-with-bfile-data-types-in-oracle-database"></a>对包含 BFILE 数据类型在 Oracle 数据库中的表的操作
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表和存储的过程中支持 BFILE 数据类型。 下表总结了由适配器基于执行的操作公开的 BFILE 数据类型和访问 LOB 项目 （表/过程）：  
  
|项目|运算|BFILE col/param 公开的数据类型|注释|  
|--------------|---------------|--------------------------------------------|--------------|  
|TABLE|Insert|String|表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径<br /><br /> 例如 MYDIR/screen.jpg MYDIR 其中是 Oracle 中的逻辑目录|  
|TABLE|UPDATE|String|表示要更新到 BFILE 列的文件的逻辑的 Oracle 目录路径|  
|TABLE|SELECT|byte[]|表示二进制数据构成 BFILE|  
|存储的过程|在参数中|String|表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径<br /><br /> 例如 MYDIR/screen.jpg MYDIR 其中是 Oracle 中的逻辑目录|  
|存储的过程|OUT 参数|String|表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径<br /><br /> 例如 MYDIR/screen.jpg MYDIR 其中是 Oracle 中的逻辑目录|  
|存储的过程|INOUT 参数|不支持|-|  
  
 在包含 BFILE 数据类型的表上还支持特殊操作 ReadLOB。 不支持 UpdateLOB 操作。 适配器客户端或者可以使用更新操作。  
  
 有关详细信息：  
  
- 对包含 BFILE 数据类型使用的表执行操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[包含 BFILE 数据类型在 Oracle 数据库中使用 BizTalk Server 运行操作表](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)