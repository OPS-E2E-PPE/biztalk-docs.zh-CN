---
title: 如何创建自定义分析任务 |Microsoft Docs
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
ms.openlocfilehash: 2afeae7dba801e1724e30e88d68ea454d87b228f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340083"
---
# <a name="how-to-create-a-custom-analysis-task"></a>如何创建自定义分析任务
创建用于处理 BAM 数据的自定义 DTS 任务的最简单方法是从是 bam 自动生成的包开始，并将为所有实际的数据处理。  
  
### <a name="to-create-a-custom-dts-task"></a>若要创建自定义 DTS 任务  
  
1. 创建 BAM 定义所需的 OLAP 多维数据集。 例如使用 Excel 向导中，并将一个 PivotTable® 报表作为非 RTA 视图。  
  
2. 打开 BAM 创建的多维数据集处理的 DTS 包。 BAM 将创建一个此类包为每个视图，称为 BAM_AN_\<*视图名称*\>。  
  
3. 在 DTS 设计器中打开该包并删除除前两个步骤和最后一步外的所有步骤。 您可能想要保留到主导入数据库的连接。  
  
4. 编辑第一项 ActiveX® 任务的属性。 删除包含 DTSGlobalVariables.Parent.Steps，所有行，因为它们是指已删除的步骤。 该脚本开头如下：  
  
   ```  
   serverName = "<your server here>"   
   databaseName = "<your analysis database here>"  
   cubeName = "<your cube name here>"  
   ```  
  
   > [!NOTE]
   >  任务"开始数据分析"（包中的第二个任务） 是非常重要，因为它赋予您的包：  
   > 
   > - 增量处理已完成的活动 （动态 SQL 视图名为 bam_ (BamView) 查看 （_v) （活动） _CompletedInstancesWindow 移动窗口  
   >   -   正在进行的名为 bam 的表中的活动的快照\_(BamView) 查看 （_v) （活动） _ActiveInstancesSnapshot。  
  
5. 获取视图和表在短事务中，在此期间您插入任何数据，以便数据表示实际即时主导入数据库的快照。 实现一个或多个步骤执行操作的视图和表作为输入数据的实际数据转换。 如果您的分析任务的目的是填充 OLAP 多维数据集以外的内容，请注意，使你的作业时提交最后一次和第一个 ActiveX 任务替换为将此时间戳分配给全局变量的代码的时间戳"CompletedCubeLastProcessTime"。 第二个任务使用此变量来确保没有丢失的数据和任何数据处理两次在崩溃时，DTS 包的重新启动。  
  
6. 最后，您必须调用最后一个任务，即"结束数据分析"。 此任务中释放，以便他们可以存档和之外的联机时段后从主导入数据库中删除已处理的已完成的活动。  
  
## <a name="see-also"></a>请参阅  
 [使用业务活动监视](../core/using-business-activity-monitoring.md)