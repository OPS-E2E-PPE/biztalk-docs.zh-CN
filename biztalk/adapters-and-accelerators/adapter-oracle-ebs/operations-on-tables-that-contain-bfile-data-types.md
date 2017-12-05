---
title: "对包含 BFILE 数据类型的表的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d7ebeb9-c2d6-4024-a169-263b947eeeb1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5096539b86512e51756d3a872ff566872ff520f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="operations-on-tables-that-contain-bfile-data-types"></a>对包含 BFILE 数据类型的表的操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]表和存储的过程中支持 BFILE 数据类型。 

## <a name="bfile-data-types"></a>BFILE 数据类型
下表总结了 BFILE 数据类型公开的执行的操作所基于的适配器和 LOB 项目 （表/过程） 访问：  
  
|项目|运算|BFILE 列/param 的公开的数据类型|注释|  
|--------------|---------------|--------------------------------------------|--------------|  
|TABLE|Insert|字符串|表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径<br /><br /> 例如 MYDIR/screen.jpg MYDIR 所在 Oracle 中的逻辑目录|  
|TABLE|UPDATE|字符串|表示要插入 BFILE 列更新的文件的逻辑的 Oracle 目录路径|  
|TABLE|SELECT|byte[]|表示构成 BFILE 的二进制数据|  
|存储的过程|PARAM 中|字符串|表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径<br /><br /> 例如 MYDIR/screen.jpg MYDIR 所在 Oracle 中的逻辑目录|  
|存储的过程|OUT 参数|字符串|表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径<br /><br /> 例如 MYDIR/screen.jpg MYDIR 所在 Oracle 中的逻辑目录|  
|存储的过程|INOUT PARAM|不支持|-|  
  
 特殊操作`Read_<LOBColName>`BFILE 数据类型的表中还支持其中\<LOBColName\>是 LOB 列的名称表中。 `Update_<LOBColName>` BFILE 数据类型不支持操作。 适配器客户端或者可以使用更新操作。  
  
## <a name="more-good-info"></a>良好的详细信息  
  
-   `Read_<LOBColName>`和`Update_<LOBColName>`操作，请参阅[接口表、 界面视图、 表和包含 LOB 数据的视图上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)