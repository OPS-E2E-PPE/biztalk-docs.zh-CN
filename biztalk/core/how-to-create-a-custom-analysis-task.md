---
title: 如何创建自定义分析任务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, DTS tasks
- DTS tasks
- DTS packages, tasks
- BAM, processing
ms.assetid: 6046c113-fb58-4e72-8f48-5470e52be9a8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3566e40deaa05886ead701e1871634cf6fb94e2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969227"
---
# <a name="how-to-create-a-custom-analysis-task"></a>如何创建自定义分析任务
创建自定义的 DTS 任务来处理 BAM 数据的最简单方法是从 BAM 由自动生成的包启动，并将所有实际的数据处理。  
  
### <a name="to-create-a-custom-dts-task"></a>若要创建自定义 DTS 任务  
  
1.  创建需要的 OLAP 多维数据集的 BAM 定义。 例如使用 Excel 向导中，并将作为非 RTA 视图的一个 PivotTable® 报表。  
  
2.  打开 BAM 创建的多维数据集处理的 DTS 包。 BAM 创建一个此类包中的每个视图中，称为 BAM_AN_\<*视图名称*\>。  
  
3.  在 DTS 设计器中打开该包并删除除前两个步骤和最后一步以外的所有步骤。 你可能还想要保留到主导入数据库的连接。  
  
4.  编辑的第一个 ActiveX® 任务的属性。 删除包含 DTSGlobalVariables.Parent.Steps 的所有行，因为它们是指已删除的步骤。 该脚本开头：  
  
    ```  
    serverName = "<your server here>"   
    databaseName = "<your analysis database here>"  
    cubeName = "<your cube name here>"  
    ```  
  
    > [!NOTE]
    >  任务“开始数据分析”（即包中的第二个任务）非常重要，因为它赋予您的包以下功能：  
    >   
    >  -   以进行增量处理的已完成的活动 （动态 SQL 视图名为 bam_ (BamView) 查看 （_v) （活动） _CompletedInstancesWindow 移动窗口  
    > -   进度-一个名为 bam 表中的活动的快照\_(BamView) 查看 （_v) （活动） _ActiveInstancesSnapshot。  
  
5.  获取视图和表在短事务中，在此期间你插入任何数据，以便为数据表示主导入数据库的实际即时的快照。 实现执行操作的视图和表作为输入数据的实际数据转换的一个或多个步骤。 如果您的分析任务不是为了填充 OLAP 多维数据集，而是执行其他操作，请记住保留您的作业最后一次提交时的时间戳，并使用将此时间戳分配给全局变量“CompletedCubeLastProcessTime”的代码来替换第一个 ActiveX 任务。 第二个任务使用此变量以确保没有丢失的数据和任何数据处理两次发生崩溃并重新启动的 DTS 包。  
  
6.  最后，必须调用最后一个任务，即“结束数据分析”。 此任务释放已处理，以便他们可以存档和在这些联机的时段之外删除从主导入已完成的活动。  
  
## <a name="see-also"></a>另请参阅  
 [使用业务活动监视](../core/using-business-activity-monitoring.md)