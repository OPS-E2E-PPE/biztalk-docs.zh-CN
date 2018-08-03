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
ms.openlocfilehash: 4f04b04d20189307c3d42e60c43c2c4c9254ffb7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008422"
---
# <a name="double-action-pipautomation-orchestration"></a>双操作 PIPAutomation 业务流程
此 DoubleAction.odx 示例演示如何实现为双操作合作伙伴接口流程 (PIP) 0C2、0C4、3A2 和 3A4 自动生成响应的业务流程。 你可将此示例项目扩展为支持其他双操作 PIP。  
  
> [!NOTE]
>  该示例文件夹中提供的映射为示例映射。 若要使用这些映射，必须根据你的具体要求来更改它们。  
  
> [!NOTE]
>  在扩展此示例项目时，只能扩展为支持其他双操作 PIP，而不能扩展为支持单操作 PIP。 如果将此业务流程扩展为处理单操作 PIP，则它将返回一个错误。 若要确保此业务流程不处理单操作 PIP，请参阅下面的“筛选单操作消息”部分。  
  
 默认情况下，Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]安装程序将安装在此示例\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction。  
  
 此示例项目包含以下内容：  
  
- 存储的过程 (`PipAutomationGetAction)`检索新操作消息 Pip 0c2、 0c4、 3A2 和 3A4。  
  
- 一个绑定到 SQL 存储过程的接收位置 (MessagesToLOB_Receive_Location)。  
  
- 一个业务流程 (DoubleAction.odx)，用于处理每个 PIP，根据映射生成每个 PIP 的相应响应，以及将响应保存到 BTARNDATA 数据库的 MessagesFromLOB 表中。 该业务流程使用 Microsoft.Solutions.BTARN.Shared.dll 中的 `RNIFSubmit` 方法来提交消息。  
  
- 一个绑定文件 (DoubleActionBinding.xml)，文件 Setup.bat 使用该绑定文件创建用于 DoubleAction 业务流程的 MessagesToLOB_Receive_Port。  
  
- 一个生成和初始化该示例的安装文件。 如果 BizTalk Server 正在运行的 32 位计算机上，在运行文件 setup.bat\<驱动器\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet \SDK\PIPAutomation\DoubleAction 文件夹。 如果 BizTalk Server 正在运行的 64 位计算机上，运行同一文件夹中的 setupx64.bat。  
  
  该业务流程使用 BTARNData 数据库中的 PipAutomationGetAction 存储过程（源文件为 DoubleAction 目录中的 DoubleAction.sql）来接收消息。 此存储过程从 MessagesToLOB 表中检索消息。  
  
  若要扩展此示例项目以支持其他双操作 PIP，可在该双操作 PIP 的业务流程中添加路径。 此路径应包含一个映射，将响应消息构造为请求消息。 有关示例映射，请参阅[3A2 请求到 3A2 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)并[3A4 请求到 3A4 响应映射示例&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)。  
  
### <a name="to-build-and-initialize-this-sample"></a>构建和初始化此示例  
  
1. 在命令提示符处，找到*\<驱动器\>*: \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction 文件夹。  
  
   > [!NOTE]
   >  在运行安装程序之前，用记事本打开 DoubleAction.sql 文件（在上面所述的文件夹中）。 上**文件**菜单上，单击**另存为**。 在中**编码**列表中，选择**ANSI**，然后单击**保存**。 单击**是**以覆盖现有文件。  
  
2. 如果您的 BizTalk Server 正在运行的 32 位计算机上，在运行文件 setup.bat\<驱动器\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction 文件夹。 如果您的 BizTalk Server 安装在 64 位计算机上运行，请在同一文件夹中运行 setupx64.bat。 该批处理文件将执行以下操作：  
  
   - 在 BTARNDATA 数据库中创建一个 SQL 存储过程 (`PipAutomationGetAction`)，用于从 MessagesToLOB 表中检索操作消息。 这还可以确保不会重复读取检索到的记录。  
  
   - 编译 HeaderHelper [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 项目，并在全局程序集缓存中注册此程序集。  
  
   - 创建并绑定 BizTalk Server SQL 接收端口 (MessagesToLOB_Receive_Port)。  
  
   - 启用接收位置 (MessagesToLOB_Receive_Location)。  
  
   - 编译并部署双操作 PIPAutomation 业务流程 (DoubleAction.odx)。  
  
   - 绑定并启动 BizTalk Server 业务流程。  
  
     > [!NOTE]
     >  编译时示例将显示一些警告。 你可以忽略这些警告。  
  
     > [!NOTE]
     >  此示例使用默认主机名**BizTalkServerApplication**部署项目时。 如果你想要运行该示例不同的主机，你将需要编辑下的 DoubleActionBinding.xml 中找到的默认主机名\<SDK\>\PIPAutomation\DoubleAction 文件夹。  
  
### <a name="to-run-the-double-action-pipautomation-sample"></a>运行双操作 PIPAutomation 示例  
  
1. 创建本组织角色为发起方的 3A4 协议。 将本组织的 GBI 设置为 123456789，将合作伙伴的 GBI 设置为 987654321。 这允许您使用 SampleInstances 文件夹中的示例，该文件夹位于 SDK 中的 LOBApplication 文件夹下。  
  
2. 使用 Loopback 协议镜像实用工具，为在步骤 1 中创建的 3A4 PIP 创建镜像。  
  
3. 使用 LOBApplication.exe SDK 实用工具提交 3A4 PIP 请求消息。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 文件夹中包含一个输入的示例\<*安装目录*\>\SDK\LOBApplication\SampleInstances\3A4_Request.xml。  
  
4. 在 BTARNDATA 数据库运行以下查询：  
  
   ```  
   Select * from MessagesToLOB  
   ```  
  
5. 几秒钟后，会有四个新消息出现在此表中。 其中两个消息是确认信号。 一个信号是 Async 3A4 请求消息。 另一个信号是 Async 3A4 响应消息。  
  
   > [!NOTE]
   >  若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 再次运行 Setup.bat 前，必须先运行 Cleanup.bat。  
  
## <a name="remarks"></a>Remarks  
 公用业务流程自动生成确认消息（ACK 和 NACK 信号消息）。 业务线 (LOB) 应用程序不需要生成它们。  
  
 路由到 MessagesFromLOB 表的消息的格式称为 LOBMessage。 架构是 C:\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\RNIFSchemas\GlobalSchemas\LOBMessage.xsd 中可用。 如果使用 `RNIFSubmit` 方法，则不必处理消息格式。 只需提交的附加信息的 ServiceContent。 `RNIFSubmit` 填充 MessagesFromLOB 表中的记录。  
  
## <a name="filtering-out-single-action-messages"></a>筛选单操作消息  
 此业务流程应只接收双操作消息。 你不应将此示例项目扩展为支持单操作 PIP。 如果使用此业务流程来处理单操作消息，BTARN 将出现错误。 为了防止该业务流程接收单操作消息，请更改 PIPAutomationGetAction 存储过程中的以下行：  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB  
```  
  
 在上面的行中添加用于筛选单操作消息的 WHERE 子句。 该 WHERE 子句中包含将要处理的所有单操作消息。 代码行应如以下所示：  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB WHERE PIPCode NOT IN ( '0A1', '3B2', '3C3', '0C1', '0C3' )  
```  
  
## <a name="see-also"></a>请参阅  
 [3A2 请求到 3A2 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)   
 [3A4 请求到 3A4 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)   
 [业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)