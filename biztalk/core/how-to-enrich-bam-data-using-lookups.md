---
title: 如何丰富 BAM 数据使用查找 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, data lookups
ms.assetid: 8d10659e-97d6-4cd1-9b4d-307afd43c763
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43b42b42158bc3b3c179d624340a97a890072a17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enrich-bam-data-using-lookups"></a>如何使用查找 BAM 数据扩充
在某些情况下，操作时可用的数据并不包含报告所需的全部信息。 例如，在运行时，可能有 ProductID 但没有 ProductName。 由于 BAM 活动表示的是与数据的实际收集方式无关的抽象概念，因此应包含要在报告“ProductName”中看到的称为最终数据的项。 与任何其他项一样，您也可以在解释性结构（如里程碑组、持续时间、维度和度量）中使用此项。 由于 ProductName 运行时不可用，因此您必须获得其他执行查找所需的数据，如 ProductID。  
  
 您应该收集同一列中的数据，而不是报告所需的数据。 例如，应该在运行时收集 ProductID 而不是 ProductName。 如果需要多列，可以在活动中创建多个项，但不要在任何视图中使用它们。  
  
### <a name="to-enrich-bam-data-via-lookups"></a>通过查找丰富 BAM 数据  
  
1.  部署 BAM 定义。  
  
2.  在 SQL Server Management Studio 中，添加包含感兴趣数据的服务器作为远程服务器。  
  
3.  找到名为 BAM_AN_`<View Name>` 的数据分析包。 例如，如果视图为 SalesMgr，则该包名为 BAM_AN_SalesMgr。  
  
4.  设置包视图的放大比例（例如 100%）  
  
5.  添加要在查找中使用的 SQL 连接。  
  
6.  完成“清除过渡数据库”步骤后，找到相应的转换数据任务。 过渡数据库是将数据从主导入数据库移至星型架构数据库过程中需要使用的位置。 有两个实例，此任务-一个用于已完成的活动，另一个正在进行。 为这两项任务执行下述其余步骤。  
  
7.  单击“转换”。  
  
8.  选择“查找”；使用查找连接添加查找“LookupProductByID”（有关查找的信息，请参阅《SQL 联机丛书》）。 例如，如果查找的是一个包含 ProductID 列和 ProductName 列的简单表“LookupProduct”，则查找的文本将为：  
  
    ```  
    SELECT ProductName  
    FROM   LookupProduct  
    WHERE ProductID=?  
    ```  
  
9. 单击“转换”选项卡。删除默认数据转换“Transform”，创建 ActiveX 转换。 单击“源列”，然后添加所有列。 单击“目标列”，然后添加所有列。  
  
10. 常规选项卡上，依次单击和属性。 这将自动生成如下所示的、执行不太重要的复制转换的脚本：  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("ProductName") = DTSSource("ProductName")  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
11. 使用查找更改值，如下所示：  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("Product")= _  
                      DTSLookups( "LookupProductByID" ).Execute(  _                                  DTSSource("Product"))  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
12. 保存并运行该程序包。  
  
13. 确保正确的数据在 OLAP 多维数据集中结束。 应该将该程序包保存为 VBScript 或结构化存储文件，因为它还包含您自定义的代码，而不仅仅是 BAM 自动生成的步骤。  
  
> [!NOTE]
>  查找仅适用于使用 DTS 和 OLAP 执行的计划报告。 如果需要实时聚合收集的数据以外的其他数据，则在调用 BAM API 之前必须检索这些数据。  
  
## <a name="see-also"></a>另请参阅  
 [使用业务活动监视](../core/using-business-activity-monitoring.md)   
 [部署本地化的 BAM XML 文件](../core/deploying-localized-bam-xml-files.md)