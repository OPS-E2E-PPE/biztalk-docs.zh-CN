---
title: 如何使用查找的 BAM 数据扩充 |Microsoft Docs
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
ms.openlocfilehash: d27a44d67ce7b95e06e07fd2be425688733b7bc8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385064"
---
# <a name="how-to-enrich-bam-data-using-lookups"></a>如何使用查找的 BAM 数据扩充
有些情况下在其中在操作时可用的数据不包含出于报告目的所需的一切。 例如，你可能会在运行时有 ProductID 但没有 ProductName。 由于 BAM 活动表示独立于数据的实际收集方式的抽象，它应包含名为你想要查看报告"ProductName"中的最后一个数据的项。 就像任何其他项，您可以使用此如里程碑组、 持续时间、 维度和度量值的解释性结构中。 由于 ProductName 不在运行时可用，则必须获取足以执行查找，如 ProductID 一些其他数据。  
  
 您应该收集同一列中，而不是报告所需的数据中的数据。 例如，应该在运行时收集 ProductID 而不是 ProductName。 如果需要更多的列，也可以在活动中创建多个项，但不是在任何视图中使用它们。  
  
### <a name="to-enrich-bam-data-via-lookups"></a>通过查找的 BAM 数据扩充  
  
1.  部署 BAM 定义。  
  
2.  在 SQL Server Management Studio 中，添加包含所需服务器作为远程服务器的数据的服务器。  
  
3.  找到名为 BAM_AN_ 的数据分析包`<View Name>`。 例如如果视图为 SalesMgr，这将为 BAM_AN_SalesMgr。  
  
4.  设置缩放放大的视图的包 （例如 100%)  
  
5.  在查找中添加要使用的 SQL 连接。  
  
6.  在步骤"清除过渡数据库"后找到转换数据任务。 这是在其中将数据从主导入到星数据库。 有两个实例的此任务 — 一个用于已完成的活动，另一个正在进行中。 适用于这两项任务的所有剩余的步骤。  
  
7.  单击转换。  
  
8.  选择查找;添加查找"LookupProductByID"，然后使用查找连接 （请参阅 SQL 联机丛书查找）。 例如，查找是一个简单的表"LookupProduct"，如果具有 ProductID 和 ProductName 列，则查找的文本将是：  
  
    ```  
    SELECT ProductName  
    FROM   LookupProduct  
    WHERE ProductID=?  
    ```  
  
9. 单击转换选项卡。删除默认数据转换"Transform"，并改为创建 ActiveX 转换。 单击源列，然后添加所有列。 单击目标列并添加所有列。  
  
10. 单击常规选项卡，然后属性。 这将自动生成的脚本的执行普通复制转换所示：  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("ProductName") = DTSSource("ProductName")  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
11. 使用查找，如所示更改值：  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("Product")= _  
                      DTSLookups( "LookupProductByID" ).Execute(  _                                  DTSSource("Product"))  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
12. 保存并运行包。  
  
13. 请确保正确的数据最终都会在 OLAP 多维数据集。 你应将包保存为 VBScript 或结构化的存储文件，因为它包含自定义代码，而不仅仅是自动生成步骤，可从 BAM。  
  
> [!NOTE]
>  查找仅适用于使用 DTS 和 OLAP 执行计划的报表。 如果需要比在实时聚合收集了哪些信息不同的数据，然后必须调用 BAM API 之前检索数据。  
  
## <a name="see-also"></a>请参阅  
 [使用业务活动监视](../core/using-business-activity-monitoring.md)   
 [部署已本地化的 BAM XML 文件](../core/deploying-localized-bam-xml-files.md)