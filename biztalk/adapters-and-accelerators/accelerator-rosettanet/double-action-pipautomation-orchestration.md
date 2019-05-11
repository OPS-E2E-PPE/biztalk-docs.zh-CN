---
title: 双操作 PIPAutomation 业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9159f7b1-cb83-41f1-8637-39c5ddcc63ae
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 830846dd25bef7748fb6bcf77a112c03c3a152ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283737"
---
# <a name="double-action-pipautomation-orchestration"></a>双操作 PIPAutomation 业务流程
此 DoubleAction.odx 示例演示如何实现为双操作合作伙伴接口流程 (Pip) 自动生成响应的业务流程 0c2、 0c4、 3A2 和 3A4。 您可以扩展此示例项目以支持其他双操作 Pip。  
  
> [!NOTE]
>  示例文件夹中提供的映射是示例。 若要使用它们，你必须更改它们根据具体要求。  
  
> [!NOTE]
>  应将扩展此示例项目以支持双操作 Pip 唯一，不是单操作 Pip。 如果您扩展其可以处理单操作 PIP，此业务流程将返回错误。 若要确保此业务流程不会处理单操作 Pip，请参阅下面的筛选出单操作消息部分。  
  
 默认情况下，Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]安装程序将安装在此示例\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction。  
  
 此示例项目包括：  
  
- 存储的过程 (`PipAutomationGetAction)`检索新操作消息 Pip 0c2、 0c4、 3A2 和 3A4。  
  
- 接收位置 (MessagesToLOB_Receive_Location) 绑定到 SQL 存储过程。  
  
- 处理每个 PIP 的业务流程 (DoubleAction.odx) 生成适当的响应基于在地图上的每个 PIP，并将响应保存在 BTARNDATA 数据库的 MessagesFromLOB 表中。 该业务流程使用`RNIFSubmit`Microsoft.Solutions.BTARN.Shared.dll 提交消息中的方法。  
  
- 一个绑定文件 (DoubleActionBinding.xml)，文件 Setup.bat 使用来创建与 DoubleAction 业务流程的 MessagesToLOB_Receive_Port。  
  
- 要生成并初始化示例的安装程序文件。 如果 BizTalk Server 正在运行的 32 位计算机上，在运行文件 setup.bat\<驱动器\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet \SDK\PIPAutomation\DoubleAction 文件夹。 如果 BizTalk Server 正在运行的 64 位计算机上，运行同一文件夹中的 setupx64.bat。  
  
  业务流程接收消息使用 BTARNData 数据库中的 PipAutomationGetAction 存储过程 （源文件为 DoubleAction 目录中 DoubleAction.sql）。 此存储的过程从 MessagesToLOB 表中检索消息。  
  
  若要扩展此示例项目以支持其他双操作 Pip，双操作 PIP 的业务流程中添加路径。 此路径将包含一个映射，将构造为请求消息的响应消息。 有关示例映射，请参阅[3A2 请求到 3A2 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)并[3A4 请求到 3A4 响应映射示例&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)。  
  
### <a name="to-build-and-initialize-this-sample"></a>若要生成并初始化本示例  
  
1. 在命令提示符处，找到*\<驱动器\>*: \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction 文件夹。  
  
   > [!NOTE]
   >  才能运行安装程序，用记事本打开 DoubleAction.sql （在上面的文件夹中） 的文件。 上**文件**菜单上，单击**另存为**。 在中**编码**列表中，选择**ANSI**，然后单击**保存**。 单击**是**以覆盖现有文件。  
  
2. 如果您的 BizTalk Server 正在运行的 32 位计算机上，在运行文件 setup.bat\<驱动器\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction 文件夹。 如果您的 BizTalk Server 安装在 64 位计算机上运行，请在同一文件夹中运行 setupx64.bat。 批处理文件将执行以下操作：  
  
   - 创建一个 SQL 存储过程 (`PipAutomationGetAction`) 从 MessagesToLOB 表中检索操作消息在 BTARNDATA 数据库中。 这还可以确保不会在重复读取检索到的记录。  
  
   - 编译 HeaderHelper[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]项目，然后在全局程序集缓存中注册该程序集。  
  
   - 创建并绑定 BizTalk Server SQL 接收端口 (MessagesToLOB_Receive_Port)。  
  
   - 启用接收位置 (MessagesToLOB_Receive_Location)。  
  
   - 编译并部署双操作 PIPAutomation 业务流程 (DoubleAction.odx)。  
  
   - 绑定并启动 BizTalk Server 业务流程。  
  
     > [!NOTE]
     >  示例编译时将显示一些警告。 你可以忽略这些警告。  
  
     > [!NOTE]
     >  此示例使用默认主机名**BizTalkServerApplication**部署项目时。 如果你想要运行该示例不同的主机，你将需要编辑下的 DoubleActionBinding.xml 中找到的默认主机名\<SDK\>\PIPAutomation\DoubleAction 文件夹。  
  
### <a name="to-run-the-double-action-pipautomation-sample"></a>若要运行双操作 PIPAutomation 示例  
  
1. 创建的本组织角色为发起方的 3A4 协议。 本组织的 GBI 设置为 123456789，并为 987654321 合作伙伴的 GBI 设置。 这样可以使用 SDK 的 LOBApplication 文件夹下的 SampleInstances 文件夹中提供的示例。  
  
2. 使用 Loopback 协议镜像实用工具，在步骤 1 中创建的 3A4 pip 创建镜像。  
  
3. 使用 LOBApplication.exe SDK 实用工具提交 3A4 PIP 请求消息。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 文件夹中包含一个输入的示例\<*安装目录*\>\SDK\LOBApplication\SampleInstances\3A4_Request.xml。  
  
4. 在 BTARNDATA 数据库运行以下查询：  
  
   ```  
   Select * from MessagesToLOB  
   ```  
  
5. 几秒钟后，在此表中显示了四个新消息。 其中两个消息是确认信号。 另一个信号是 Async 3A4 请求消息。 一个信号是 Async 3A4 响应消息。  
  
   > [!NOTE]
   >  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须再次运行 Setup.bat 前运行 Cleanup.bat。  
  
## <a name="remarks"></a>备注  
 公用业务流程自动生成的确认 （ACK 和 NACK 信号消息）。 业务线 (LOB) 应用程序不必生成它们。  
  
 消息路由到 MessagesFromLOB 表的格式称为 LOBMessage。 架构是 C:\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\RNIFSchemas\GlobalSchemas\LOBMessage.xsd 中可用。 如果使用`RNIFSubmit`方法，您无需使用的消息格式。 只需提交的附加信息的 ServiceContent。 `RNIFSubmit` 填充 MessagesFromLOB 表中的记录。  
  
## <a name="filtering-out-single-action-messages"></a>筛选出单操作消息  
 此业务流程应只接收双操作消息。 不应扩展此示例项目以支持单操作 Pip。 如果使用此业务流程来处理单操作消息，BTARN 将发布错误。 为了防止该业务流程接收单操作消息，将更改 PIPAutomationGetAction 存储过程中的以下行：  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB  
```  
  
 上面的行，将添加一个 WHERE 子句，将筛选出单操作消息。 WHERE 子句中包含的所有单操作消息进行处理。 代码行应如下所示：  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB WHERE PIPCode NOT IN ( '0A1', '3B2', '3C3', '0C1', '0C3' )  
```  
  
## <a name="see-also"></a>请参阅  
 [3A2 请求到 3A2 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)   
 [3A4 请求到 3A4 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)   
 [业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)