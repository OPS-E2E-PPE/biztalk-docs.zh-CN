---
title: 对包含 BFILE 数据类型的表的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d7ebeb9-c2d6-4024-a169-263b947eeeb1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62ca4cecbc218497d18772103e538e71b32981bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375290"
---
# <a name="operations-on-tables-that-contain-bfile-data-types"></a>对包含 BFILE 数据类型的表的操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]表和存储的过程中支持 BFILE 数据类型。 

## <a name="bfile-data-types"></a>BFILE 数据类型
下表总结了由适配器基于执行的操作公开的 BFILE 数据类型和访问 LOB 项目 （表/过程）：  
  
|项目|操作|BFILE col/param 公开的数据类型|注释|  
|--------------|---------------|--------------------------------------------|--------------|  
|TABLE|Insert|String|表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径<br /><br /> 例如 MYDIR/screen.jpg MYDIR 其中是 Oracle 中的逻辑目录|  
|TABLE|UPDATE|String|表示要更新到 BFILE 列的文件的逻辑的 Oracle 目录路径|  
|TABLE|SELECT|byte[]|表示二进制数据构成 BFILE|  
|存储的过程|在参数中|String|表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径<br /><br /> 例如 MYDIR/screen.jpg MYDIR 其中是 Oracle 中的逻辑目录|  
|存储的过程|OUT 参数|String|表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径<br /><br /> 例如 MYDIR/screen.jpg MYDIR 其中是 Oracle 中的逻辑目录|  
|存储的过程|INOUT 参数|不支持|-|  
  
 特殊操作`Read_<LOBColName>`BFILE 数据类型的表中也支持其中\<LOBColName\>是 LOB 列的名称表中。 `Update_<LOBColName>` BFILE 数据类型不支持操作。 适配器客户端或者可以使用更新操作。  
  
## <a name="more-good-info"></a>更多有用信息  
  
-   `Read_<LOBColName>`并`Update_<LOBColName>`操作，请参阅[对界面表、 界面视图、 表和包含 LOB 数据的视图的操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)