---
title: "从 Orchestration 表达式示例 BAM API |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 341bc333-9bfc-484c-b431-9a71f9188792
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5413940eaba97e6f68d5e068e26625f320e6e817
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="bam-api-from-an-orchestration-expression-biztalk-server-sample"></a>业务流程表达式中的 BAM API（BizTalk Server 示例）
此示例演示如何：  
  
-   使用从 BizTalk Server 业务流程表达式 BAM API。  
  
-   跟踪消息内部作为单独活动实例的重复项。  
  
-   在使用跟踪配置文件跟踪的 BAM 数据和使用 BAM API 跟踪的 BAM 数据之间创建关系。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 你可以找到在此示例*\<示例路径\>*\BAM\BamFromExpression。  
  
 下表列出了本示例中的文件及其用途说明。  
  
|文件|Description|  
|----------|-----------------|  
|BamDefinition.xls|BAM 定义样式表。|  
|BamDefinition.xml|BAM 定义。|  
|BamFromExpression.btproj|跟踪文件项目的 visual Studio。|  
|BamFromExpression.sln|Visual Studio 解决方案。|  
|Cleanup.bat|用于取消部署本示例的批处理文件。|  
|InputMessage.xml|输入消息。|  
|Orchestration1.odx|业务流程。|  
|PoSchema.xsd|采购订单架构。|  
|PropertySchema.xsd|属性架构。|  
|Setup.bat|用于编译和部署本示例的批处理文件。|  
|QueryBam.sql|SQL 脚本|  
  
## <a name="create-the-tracking-profile"></a>创建跟踪配置文件  
  
1.  打开命令提示符以管理员身份，并运行*\<示例路径\>*\BAM\BAMFromExpression\Setup.bat。 Setup.bat 可初始化此示例的 BAM 基础结构，并部署 BAM 活动。  
  
2.  从你**程序** > **Microsoft BizTalk Server**，右键单击**跟踪配置文件编辑器**，和**以管理员身份运行**.
  
3.  在左窗格中 **跟踪配置文件编辑器** 窗口中，单击 **单击此处以导入 BAM 活动定义**。  
  
4.  在 **BAM 活动定义名称** 部分 **导入 BAM 活动定义** 对话框中，选择 **FromExpressionPo**, ，然后单击 **确定**。  
  
5.  在右窗格中 **跟踪配置文件编辑器** 窗口中，单击 **单击此处选择的事件源**。  
  
6.  在 **程序集名称** 部分 **选择事件源父程序集** 对话框中，选择 **Microsoft.Samples.BizTalk.BamFromExpression**, ，然后单击 **下一步**。  
  
7.  在 **Orchestration 名称** 部分 **选择业务流程** 对话框中，选择 **BamFromExpression.Orchestration1**, ，然后单击 **确定**。  
  
8.  右键单击 **Receive_1** 形状，并依次 **消息负载架构**。  
  
9. 展开**\<架构\>**，展开**PurchaseOrder**，展开**从**，然后拖动**PoID**方窗格**ActivityID**的左窗格中。  
  
10. 拖动右窗格中的以下元素，并将它们放到左窗格中已命名节点上：  
  
    |From|若要|  
    |----------|--------|  
    |名称|From|  
    |State|State|  
    |City|City|  
    |Phone|Phone|  
    |总计|PoTotal|  
  
11. 单击文件夹图标带有箭头 (![使用文件夹和向上按钮 &#45; 箭头](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) 以显示业务流程。  
  
12. 拖动 **Receive_1** 到右窗格中的形状 **Received** 的左窗格中。  
  
13. 拖动 **Send_1** 到右窗格中的形状 **发送** 的左窗格中。  
  
14. 保存跟踪配置文件到*\<示例路径\>*\BAM\BamFromExpression\ BamFromExpression.btt。  
  
15. 上 **工具** 菜单上，单击 **应用跟踪配置文件**。  
  
## <a name="build-and-initialize-this-sample"></a>生成并初始化此示例  
  
部署 BamFromExpression.btt 跟踪配置文件。 请参阅[如何部署跟踪配置文件使用跟踪配置文件管理实用工具](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)。  
  
## <a name="run-this-sample"></a>运行此示例  
  
将文件复制*\<示例路径\>*到 \BamFromExpression\InputMessage.xml *\<示例路径\>*\BamFromExpression\Input。  
  
在大约 10 秒输出消息将出现在*\<示例路径\>*\BamFromExpression\Output。  
  
## <a name="view-the-bam-data"></a>查看 BAM 数据  
  
1.  打开 SQL Server Management Studio。  
  
2.  在 SQL Server Management Studio，展开服务器，展开 **数据库**, ，展开 **BAMPrimaryImport**, ，然后展开 **表**。  
  
3.  右键单击 **dbo.bam_FromExpressionPo_Completed**, ，然后单击 **打开表**。 如果你使用的 SQL Server，请单击**选择前 1000年行**。  
  
     将在右窗格中显示 bam_FromExpressionPo_Completed 表中的内容。 具有活动 ID 123 的一行，表示包含在输入消息中 345 美元的采购订单。  
  
4.  右键单击 **dbo.bam_FromExpressionPoItem_Completed**, ，然后单击 **打开表**。 如果你使用的 SQL Server，请单击**选择前 1000年行**。  
  
     将在右窗格中显示 bam_FromExpressionPoItem_Completed 表中的内容。 两个行，它有活动 Id 123_0 和 123_1，表示该采购订单中的项︰ Flash MC 和红外的解码器。  
  
5.  右键单击 **dbo.bam_FromExpressionPoItem_CompletedRelationships**, ，然后单击 **打开表**。 如果你使用的 SQL Server，请单击**选择前 1000年行**。  
  
     将在右窗格中显示 bam_FromExpressionPoItem_CompletedRelationships 表中的内容。 表中的每一行，都表示 FromExpressionPoItem 活动和 FromExpressionPo 活动之间的一种关系。 中的值 **ActivityID** 列是指 FromExpressionPoItem 活动的活动 ID。 中的值 **ReferenceData** 列是指 FromExpressionPo 活动的活动 ID。 在这种情况下，这两个记录表示 Flash MC 和红外解码器项与 345 美元的采购订单相关。  
  
## <a name="re-run-the-sample"></a>重新运行此示例  
  
1.  打开命令提示符以管理员身份，并运行*\<示例路径\>*\BAM\BamFromExpression\Cleanup.bat 若要删除的跟踪配置文件和其他 BAM 基础结构。 
  
2.  运行*\<示例路径\>*\BAM\BamFromExpression\Setup.bat 编译该示例并将其部署。  
  
## <a name="see-also"></a>另请参阅  
 [业务活动监视 （BizTalk Server 示例文件夹中）](../core/business-activity-monitoring-biztalk-server-samples-folder.md)   
 [活动关系](../core/activity-relationships.md)