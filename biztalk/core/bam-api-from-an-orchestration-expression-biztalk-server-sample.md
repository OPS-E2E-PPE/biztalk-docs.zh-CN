---
title: 从业务流程表达式示例的 BAM API |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 341bc333-9bfc-484c-b431-9a71f9188792
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acecbaff45eb7fd3e7197a27de5ae9911c174012
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358631"
---
# <a name="bam-api-from-an-orchestration-expression-biztalk-server-sample"></a>BAM API （BizTalk Server 示例） 业务流程表达式中
此示例演示如何：  
  
-   使用 BizTalk Server 业务流程表达式中的 BAM API。  
  
-   重复消息内的项作为单独活动实例的跟踪。  
  
-   创建使用跟踪配置文件，跟踪的 BAM 数据和使用 BAM API 跟踪的 BAM 数据之间的关系。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 您可以找到在此示例*\<示例路径\>* \BAM\BamFromExpression。  
  
 下表列出了在此示例中的文件，并描述其用途。  
  
|文件|Description|  
|----------|-----------------|  
|BamDefinition.xls|BAM 定义样式表。|  
|BamDefinition.xml|BAM 定义。|  
|BamFromExpression.btproj|跟踪文件项目的 visual Studio。|  
|BamFromExpression.sln|Visual Studio 解决方案。|  
|Cleanup.bat|若要取消部署本示例的批处理文件。|  
|InputMessage.xml|输入的消息。|  
|Orchestration1.odx|业务流程。|  
|PoSchema.xsd|采购订单架构。|  
|PropertySchema.xsd|属性架构。|  
|Setup.bat|若要编译并部署示例的批处理文件。|  
|QueryBam.sql|SQL 脚本。|  
  
## <a name="create-the-tracking-profile"></a>创建跟踪配置文件  
  
1.  打开命令提示符下以管理员身份，并运行*\<示例路径\>* \BAM\BAMFromExpression\Setup.bat。 Setup.bat 初始化此示例中，BAM 基础结构，并部署 BAM 活动。  
  
2.  从你**程序** > **Microsoft BizTalk Server**，右键单击**跟踪配置文件编辑器**，和**以管理员身份运行**.
  
3.  在左窗格中**跟踪配置文件编辑器**窗口中，单击**单击此处可导入 BAM 活动定义**。  
  
4.  中**BAM 活动定义名称**一部分**导入 BAM 活动定义**对话框中，选择**FromExpressionPo**，然后单击**确定**.  
  
5.  在右窗格中**跟踪配置文件编辑器**窗口中，单击**单击此处可选择事件源**。  
  
6.  在中**程序集名称**一部分**选择事件源父程序集**对话框中，选择**Microsoft.Samples.BizTalk.BamFromExpression**，然后单击**下一步**。  
  
7.  中**业务流程名称**一部分**选择业务流程**对话框中，选择**BamFromExpression.Orchestration1**，然后单击**确定**.  
  
8.  右键单击**Receive_1**形状，然后依次**消息负载架构**。  
  
9. 展开**\<架构\>**，展开**PurchaseOrder**，展开**从**，然后将拖**PoID**方窗格**ActivityID**的左窗格中。  
  
10. 从右窗格中，以下元素拖放到左窗格中已命名的节点上：  
  
    |From|若要|  
    |----------|--------|  
    |“属性”|From|  
    |State|State|  
    |City|City|  
    |Phone|Phone|  
    |总计|PoTotal|  
  
11. 单击带箭头的文件夹图标 (![与文件夹按钮，然后向上&#45;箭头](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) 以显示业务流程。  
  
12. 拖动**Receive_1**到右窗格中的形状**Received**的左窗格中。  
  
13. 拖动**Send_1**到右窗格中的形状**发送**的左窗格中。  
  
14. 保存到跟踪配置文件*\<示例路径\>* \BAM\BamFromExpression\ BamFromExpression.btt。  
  
15. 上**工具**菜单上，单击**应用跟踪配置文件**。  
  
## <a name="build-and-initialize-this-sample"></a>生成并初始化本示例  
  
部署 BamFromExpression.btt 跟踪配置文件。 请参阅[如何部署跟踪配置文件与跟踪配置文件管理实用程序](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)。  
  
## <a name="run-this-sample"></a>运行此示例  
  
将文件复制*\<示例路径\>* 到 \BamFromExpression\InputMessage.xml *\<示例路径\>* \BamFromExpression\Input。  
  
在大约 10 秒的输出消息将出现在*\<示例路径\>* \BamFromExpression\Output。  
  
## <a name="view-the-bam-data"></a>查看 BAM 数据  
  
1.  打开 SQL Server Management Studio。  
  
2.  在 SQL Server Management Studio 中，展开服务器，展开**数据库**，展开**BAMPrimaryImport**，然后展开**表**。  
  
3.  右键单击**dbo.bam_FromExpressionPo_Completed**，然后单击**打开表**。 如果使用 SQL Server，请单击**选择前 1000年行**。  
  
     在右窗格中显示 bam_FromExpressionPo_Completed 表的内容。 具有活动 ID 123，一行表示 345 美元与输入消息中所包含的采购订单。  
  
4.  右键单击**dbo.bam_FromExpressionPoItem_Completed**，然后单击**打开表**。 如果使用 SQL Server，请单击**选择前 1000年行**。  
  
     在右窗格中显示 bam_FromExpressionPoItem_Completed 表的内容。 具有活动 Id 123_0 和 123_1，两个行表示采购订单中的项：Flash MC 和红外解码器。  
  
5.  右键单击**dbo.bam_FromExpressionPoItem_CompletedRelationships**，然后单击**打开表**。 如果使用 SQL Server，请单击**选择前 1000年行**。  
  
     在右窗格中显示 bam_FromExpressionPoItem_CompletedRelationships 表的内容。 在表中的每一行都表示 FromExpressionPoItem 活动和 FromExpressionPo 活动之间的关系。 中的值**ActivityID**列是指 FromExpressionPoItem 活动的活动 ID。 中的值**ReferenceData**列是指 FromExpressionPo 活动的活动 ID。 在这种情况下，两个记录表示 Flash MC 和红外解码器项与 345 美元的采购订单相关联。  
  
## <a name="re-run-the-sample"></a>重新运行该示例  
  
1.  打开命令提示符下以管理员身份，并运行*\<示例路径\>* \BAM\BamFromExpression\Cleanup.bat，以删除跟踪配置文件和其他 BAM 基础结构。 
  
2.  运行*\<示例路径\>* \BAM\BamFromExpression\Setup.bat，以编译该示例并将其部署。  
  
## <a name="see-also"></a>请参阅  
 [业务活动监视 （BizTalk Server 示例文件夹）](../core/business-activity-monitoring-biztalk-server-samples-folder.md)   
 [活动关系](../core/activity-relationships.md)