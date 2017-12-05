---
title: "进度维度 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], progress dimensions
- Progress dimension [BAM]
ms.assetid: 472fcbf6-502f-4c81-bf48-f7eec98e391b
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2e4764071beb2aa94aac738e8f1cec2377dd1d8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="progress-dimension"></a>进度维度
可以使用进度维度来按照 BAM 活动所到达的里程碑对这些活动进行分组。 此功能通过示例得到了最好的说明。  
  
 请考虑一下教程 1 中处理项目请求的业务流程。 (请参阅[教程 1： 企业应用程序集成](../core/tutorial-1-enterprise-application-integration.md)有关此业务流程的详细信息。)该业务流程包含一个决策形状，后面带有两个分支。 在[教程 4： 业务活动监视](http://msdn.microsoft.com/library/81d5e768-f8a6-4eb0-8e6c-64db47455476)将业务里程碑拒绝映射到表示请求被拒绝的分支中的一个形状并将已批准的业务里程碑映射到表示的分支中的一个形状审批请求。 然后您将创建一个包含业务里程碑 Approved 和 Denied 的进度维度。 在数据透视表中使用进度维度时，您可以按 BAM 活动是被批准还是被拒绝来分组显示这些活动。 如下图所示。  
  
 ![包含已批准和拒绝的列数据透视表](../core/media/bts-view-with-approved-denieds.gif "bts_view-与-批准-denieds")  
  
 您可以在 Denied 里程碑中定义子里程碑，尽管本教程中并未这样定义。 例如，如果业务流程标识拒绝的原因，你可以创建子拒绝里程碑中名为较差的信用额度和扩展的股票的里程碑。 如果您在数据透视表中使用了进度维度，则可以深入探查 Denied 里程碑，以查看达到了“Poor credit”里程碑和“Out-of-stock”里程碑的 BAM 活动。  
  
 BAM 进度维度组成*进度里程碑*和*进度阶段*。 进度里程碑表示一个分类，希望组 BAM 活动的方式。 批准和拒绝，例如，是进度里程碑，因为你将分类请求活动： 批准或拒绝。  
  
> [!NOTE]
>  对两个概念都使用“里程碑”一词是不合适的。 A*业务里程碑*是 BAM 活动; 中的活动项它表示的日期和时间的应用程序中的某些事件的发生。 A*进度里程碑*是一种分组活动实例。 每个进度里程碑对应于业务里程碑。 若要尽量减少混淆，请考虑使用进度里程碑和的业务里程碑，它对应于相同的名称。  
  
 进度阶段是一组的对等里程碑。 与子里程碑我们的示例包含两个进度阶段。 第一个进度阶段包含已批准和拒绝的进度里程碑。 第二个进度阶段包含差信用额度和扩展的股票的进度里程碑。  
  
 进度维度作为其根开头进度里程碑。 此进度里程碑通常表示正在接收的原始消息。 每个进度里程碑只能包含一个进度阶段和任意数量的其他进度里程碑。 进度阶段中的所有进度里程碑都必须互相排斥。 在下图中，处理和原因包括进度阶段，而接收时间、 已批准、 拒绝、 很差信用额度，执行和跳出执行 stock 进度里程碑。  
  
 ![定义两个 &#45; 级别进度维度](../core/media/bts-progress-dimension-two-levelss.gif "bts_progress 维度的两个 levelss")  
  
## <a name="how-to-create-progress-dimensions"></a>如何创建进度维度  
 设计进度维度，然后使用 BAM 视图向导来创建它。 下表标识设计进度维度的过程，并还包括每个步骤的示例。  
  
|处理|示例|  
|-------------|-------------|  
|绘制类别和你想要报告的子类别的层次结构。<br /><br /> 这些级别将成为进度里程碑。|接收到：<br /><br /> 批准<br /><br /> 拒绝<br /><br /> -不佳的信用额度<br /><br /> -Out 股票的|  
|对于在同一级别的类别每组，选择表示这些类别的名称。<br /><br /> 这些集名称将成为进度阶段。|包含已批准和拒绝的级别被称为"处理"。<br /><br /> 包含不佳的信用额度和外出时的库存级别称为"原因"。|  
|标识表示每个进度里程碑的业务里程碑。<br /><br /> **注意：** BAM 活动必须为每个这些业务里程碑包括活动项。|收到： 收到<br /><br /> 批准： 批准<br /><br /> 拒绝： 拒绝<br /><br /> 较差的信用额度： 拒绝的质量较差的信用额度<br /><br /> 超出 Stock： 拒绝-的脱销|  
  
 当你创建进度维度时，将使用这些进度里程碑、 阶段和业务里程碑。  
  
> [!NOTE]
>  在要创建一个维度的点开始下列过程。 你必须已创建 BAM 活动并开始创建 BAM 视图。  
  
#### <a name="to-create-a-progress-dimension"></a>若要创建进度维度  
  
1.  单击**外接程序**选项卡上，然后选择**BAM 视图**从**BAM**下拉列表中的**菜单命令**组。  
  
2.  在 BAM 视图向导中，单击**下一步**直到你看到**新 BAM 视图： 聚合维度和度量值**页。  
  
3.  单击**新维度**。  
  
4.  在**新维度**对话框中，键入的名称中的维度**维度名称**框中，，然后选择**进度维度**从**维度类型**下拉列表。  
  
5.  单击**新里程碑**。  
  
6.  在**进度里程碑**框**新进度里程碑**对话框框中，键入层次结构设计的最高层进度里程碑的名称。 有关正在运行的示例中，你需要键入`Received`。  
  
7.  选择对应于进度里程碑，业务里程碑，然后单击**确定**。 对于正在运行的示例中，你将选择**Received (\<活动名称\>)**。  
  
8.  在**新维度**对话框中，单击**新阶段**。  
  
9. 在**进度阶段**框**新进度阶段**对话框中，键入最高级别的阶段的名称，然后单击**确定**。  有关正在运行的示例中，你需要键入**处置**。  
  
10. 在**新维度**对话框中，单击**新里程碑**。  
  
11. 在**进度里程碑**框**新进度里程碑**对话框框中，键入第一级里程碑之一的名称。 我们将使用的示例中，您需要键入`Approved`。  
  
12. 在**业务里程碑**下拉列表框中，选择对应于进度里程碑，业务里程碑，然后单击**确定**。 对于正在运行的示例中，你将选择**已批准 (\<活动名称\>)**。  
  
13. 重复前面的三个步骤以添加相同的进度阶段内的任何其他里程碑。  
  
14. 如果业务里程碑包含子里程碑，选择中的父里程碑**新维度**对话框中，单击**新阶段**，然后重复前面的五个步骤定义子阶段及其里程碑。  
  
     下图显示**新维度**对话框中创建示例进度维度后。  
  
     ![定义两个 &#45; 级别进度维度](../core/media/bts-progress-dimension-two-levelss.gif "bts_progress 维度的两个 levelss")  
  
## <a name="see-also"></a>另请参阅  
 [在 Excel 中定义的业务活动和视图](../core/defining-business-activities-and-views-in-excel.md)   
 [数据维度](../core/data-dimension.md)   
 [时间维度](../core/time-dimension.md)   
 [数值范围维度](../core/numeric-range-dimension.md)   
 [定义维度](../core/defining-dimensions.md)