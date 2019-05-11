---
title: 进度维度 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], progress dimensions
- Progress dimension [BAM]
ms.assetid: 472fcbf6-502f-4c81-bf48-f7eec98e391b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf49090260b2765620e3b968ee5dd3e70f4c2d01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395621"
---
# <a name="progress-dimension"></a>进度维度
使用进度维度将 BAM 活动的已达到的里程碑。 这是最好通过举例说明。  
  
 请考虑从教程 1 中处理项目请求的业务流程。 (请参阅[教程 1:企业应用程序集成](../core/tutorial-1-enterprise-application-integration.md)有关此业务流程的详细信息。)业务流程包含两个分支后跟一个决策形状。 在[教程 4:业务活动监视](http://msdn.microsoft.com/library/81d5e768-f8a6-4eb0-8e6c-64db47455476)将业务里程碑 Denied 映射到表示要拒绝的请求的分支中的形状，并将业务里程碑 Approved 映射到代表被批准请求的分支中的形状。 然后，创建包含业务里程碑 Approved 和 Denied 的进度维度。 当在数据透视表中使用进度维度时，可以显示已批准还是拒绝按分组的 BAM 活动。 下图所示。  
  
 ![Approved 和 Denied 的列的数据透视表](../core/media/bts-view-with-approved-denieds.gif "bts_view-与-批准-denieds")  
  
 尽管这不是在教程中，你可以定义子里程碑 Denied 里程碑中。 例如，如果业务流程确定拒绝的原因，您可以创建子里程碑 Denied 里程碑中名为不佳的信用额度和扩展的股票。 如果在数据透视表中使用进度维度，您可以向下钻取到 Denied 里程碑，以查看已达到了 Poor credit 里程碑的 BAM 活动和已达到缺货的里程碑的 BAM 活动。  
  
 在 BAM 中的进度维度组成*进度里程碑*并*进度阶段*。 进度里程碑表示分类，将 BAM 活动所需的方式。 批准和拒绝，例如，是进度里程碑，因为将对为已批准或拒绝的请求活动进行分类。  
  
> [!NOTE]
>  遗憾的是"里程碑"一词用于两个概念。 一个*业务里程碑*是 BAM 活动; 中的活动项它表示日期和应用程序中的某些事件发生的时间。 一个*进度里程碑*是一种方法对活动实例进行分组。 每个进度里程碑对应于业务里程碑。 若要尽量减少混淆，请考虑将进度里程碑和业务里程碑，它对应于相同的名称。  
  
 进度阶段是对等里程碑组。 我们的示例中使用子里程碑包含两个进度阶段。 第一个进度阶段包含，进度里程碑 Approved 和 Denied。 第二个进度阶段包含，进度里程碑 Poor credit 和扩展的股票。  
  
 进度维度作为其根开头进度里程碑。 此进度里程碑通常表示正在接收的原始消息。 每个进度里程碑可以包含一个进度阶段和任意数量的其他进度里程碑。 进度阶段中的所有进度里程碑必须都是互相排斥。 在下图中，处理和原因是进度阶段，而 Received、 Approved、 Denied、 不佳信用额度，并从存货中转出是进度里程碑。  
  
 ![定义两个&#45;级进度维度](../core/media/bts-progress-dimension-two-levelss.gif "bts_progress 维度的两个 levelss")  
  
## <a name="how-to-create-progress-dimensions"></a>如何创建进度维度  
 设计进度维度，然后使用 BAM 视图向导来创建它。 下表标识设计进度维度的过程，并还包括每个步骤的示例。  
  
|Process|示例|  
|-------------|-------------|  
|绘制类别和你想要报告的子类别的层次的结构。<br /><br /> 这些级别将成为进度里程碑。|接收到：<br /><br /> 批准<br /><br /> 被拒绝<br /><br /> -不佳的信用额度<br /><br /> -共库存|  
|为每个集的同一级别的类别，选择表示这些类别的名称。<br /><br /> 这些组名称将成为进度阶段。|包含 Approved 和 Denied 的级别是名为"处理"。<br /><br /> 包含不佳的信用额度和外出时的库存级别称为"原因"。|  
|确定代表每个进度里程碑的业务里程碑。<br /><br /> **注意：** BAM 活动必须包含这些业务里程碑的每个活动项。|接收到：收到<br /><br /> 已审批：已批准<br /><br /> 已拒绝：拒绝<br /><br /> 不佳的信用额度：Denied-poor-credit<br /><br /> 脱销情况下：拒绝--脱销|  
  
 创建进度维度时，将使用这些进度里程碑、 阶段和业务里程碑。  
  
> [!NOTE]
>  在要创建一个维度的点开始以下过程。 您必须已创建的 BAM 活动并开始创建 BAM 视图。  
  
#### <a name="to-create-a-progress-dimension"></a>若要创建进度维度  
  
1.  单击**外接程序**选项卡，然后选择**BAM 视图**从**BAM**下拉列表中的**菜单命令**组。  
  
2.  在 BAM 视图向导中，单击**下一步**直到您看到**新建 BAM 视图：聚合维度和度量值**页。  
  
3.  单击**新的维度**。  
  
4.  在中**新的维度**对话框中，键入一个名称中的维度**维度名称**框，并选择**进度维度**从**维度类型**下拉列表。  
  
5.  单击**新建里程碑**。  
  
6.  在中**进度里程碑**的框**新建进度里程碑**对话框框中，在您设计的层次结构的顶级键入进度里程碑的名称。 正在运行的示例中，您需要键入`Received`。  
  
7.  选择对应于进度里程碑，业务里程碑，然后单击**确定**。 对于正在运行的示例中，将选择**Received (\<活动名称\>)**。  
  
8.  在中**新的维度**对话框中，单击**新阶段**。  
  
9. 在中**进度阶段**的框**新建进度阶段**对话框中，键入的最高级别的阶段的名称，然后单击**确定**。  对于正在运行的示例中，应键入**处置**。  
  
10. 在中**新的维度**对话框中，单击**新建里程碑**。  
  
11. 在中**进度里程碑**的框**新建进度里程碑**对话框框中，键入一个第一级里程碑的名称。 我们将使用的示例中，您需要键入`Approved`。  
  
12. 在中**业务里程碑**下拉列表框中，选择对应于进度里程碑，业务里程碑，然后单击**确定**。 对于正在运行的示例中，将选择**已批准 (\<活动名称\>)**。  
  
13. 重复前面的三个步骤添加相同的进度阶段内的任何其他里程碑。  
  
14. 如果业务里程碑包含子里程碑，选择中的父里程碑**新的维度**对话框中，单击**新阶段**，然后重复前面的五个步骤来定义子阶段并将其里程碑。  
  
     下图显示**新的维度**创建进度维度示例后的对话框。  
  
     ![定义两个&#45;级进度维度](../core/media/bts-progress-dimension-two-levelss.gif "bts_progress 维度的两个 levelss")  
  
## <a name="see-also"></a>请参阅  
 [在 Excel 中定义业务活动和视图](../core/defining-business-activities-and-views-in-excel.md)   
 [数据维度](../core/data-dimension.md)   
 [时间维度](../core/time-dimension.md)   
 [数值范围维度](../core/numeric-range-dimension.md)   
 [定义维度](../core/defining-dimensions.md)