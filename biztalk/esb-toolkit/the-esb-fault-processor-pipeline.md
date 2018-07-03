---
title: ESB 故障处理器管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a57752b1-8bca-4534-9e5b-7ce721a9490a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1eb33c091c064c8a94939a8b9f2f0ee37f75881b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015425"
---
# <a name="the-esb-fault-processor-pipeline"></a>ESB 故障处理器管道
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]安装名为所有的发送端口。使用 ESBFaultProcessor 异常发送管道。 图 1 显示所有的属性。异常发送端口。  
  
 ![所有异常发送端口](../esb-toolkit/media/ch4-allexceptionssendport.gif "Ch4-AllExceptionsSendPort")  
  
 **图 1**  
  
 **所有的配置。异常发送端口，包括其使用的 ESBFaultProcessor 管道**  
  
 ESBFaultProcessor 管道包含以下管道组件： ESB 异常编码器、 ESB 业务活动监视 (BAM) 跟踪器和 ESB 转换。  
  
 所有。异常将发送端口订阅到所有 ESB 错误消息和生成的 BizTalk 失败消息路由机制的所有消息。 图 2 显示的筛选器的所有属性设置。异常发送端口。  
  
 ![筛选器发送端口](../esb-toolkit/media/ch4-filtersendport.gif "Ch4-FilterSendPort")  
  
 **图 2**  
  
 **所有筛选器属性。异常将发送端口定义端口订阅**  
  
## <a name="the-fault-processor-pipeline-exception-encoder-component"></a>故障处理器管道异常编码器组件  
 ESB 异常编码器管道组件将规范化 ESB 失败，业务流程异常路由机制和 BizTalk 失败消息路由机制，可为规范化符合 ESB 异常报告的消息中生成的错误消息架构。  
  
 对于失败，路由业务流程的异常的异常，该组件使其更加丰富和序列化所有错误消息属性、 XLANG 消息、 上下文属性和**System.Exception**转换为 XML 消息的信息。  
  
 失败消息路由的异常，该组件通过添加应用程序名称和其他环境属性来丰富数据，它适用于出站 XML 消息内容的架构命名空间。  
  
 （可选） ESB 异常编码器管道组件还可以应用 Microsoft InfoPath 处理指令到出站消息。 可以通过在设计视图中设置管道组件的属性来修改 InfoPath 指令。 以下三个设计时属性会影响 ESB 异常编码器管道组件的运行时行为：  
  
- **EscapeCDATA。** 此属性确定是否该组件将转义任何**CDATA**中找到的部分保留消息，以便可通过 InfoPath 正确显示。  
  
- **FaultDocumentNamespace。** 此属性具有默认值为**http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**。 可以修改此保留的消息使用自定义出站命名空间。  
  
- **ProcessingInstruction。** 此属性可以包含任何符合 ESB 异常报告错误架构的 InfoPath 处理指令。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括符合以下处理指令的 InfoPath 模板。  
  
  ```  
  <?mso-infoPathSolution solutionVersion="1.0.0.346" productVersion="11.0.6565"  
  PIVersion="1.0.0.0"   
  href=file:///\\localhost\publish\Microsoft.Practices.ESB.ExceptionHandling.InfoPath.Reporting.xsn  
  name="urn:schemas-microsoft-com:office:infopath:  
  Microsoft-Practices-ESB-ExceptionHandling-InfoPath-Reporting:  
  http---schemas-microsoft-biztalk-practices-esb-com-exceptionhandling"  
  language="en-us" ?><?mso-application progid="InfoPath.Document"?>  
  ```  
  
## <a name="the-fault-processor-pipeline-bam-tracker-component"></a>故障处理器管道 BAM 跟踪器组件  
 ESB BAM 跟踪器管道组件从 ESB 异常编码器组件接收消息，并将所选的错误数据写入到 ESB 异常管理框架的安装过程中创建的 BAM 主导入表。  
  
 ESB BAM 跟踪器组件使用**GetEventStream**管道上下文将作为活动记录的以下字段添加到 BAM 主导入数据库的方法：  
  
- **应用程序**  
  
- **Description**  
  
- **FaultSeverity**  
  
- **ServiceName**  
  
- **错误类型**  
  
- **FaultCode**  
  
- **MachineName**  
  
- **消息 Id**  
  
- **DateTime**  
  
- **FaultDescription**  
  
- **范围**  
  
- **FailureCategory**  
  
- **FaultGenerator**  
  
- **ServiceInstanceID**  
  
  ESB BAM 跟踪器组件使用的消息标识符 ( **MessageID**属性) 值的 ESB 错误消息作为 BAM 活动 id。 ESB BAM 跟踪器组件公开两个设计时属性，可设置为其运行时行为的更改：  
  
- **已启用。** 此属性确定组件是否将处理该消息并将其写入到 BAM 数据库。 如果设置为**False**，组件只是将消息发送到管道中的下一个组件。  
  
- **FaultDocumentNamespace。** 此属性具有默认值为**http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**。  
  
## <a name="the-fault-processor-pipeline-transform-component"></a>故障处理器管道转换组件  
 ESB 故障处理器管道使用 ESB 转换管道组件执行编码的 ESB 错误消息转换为与架构匹配的 BizTalk SQL 适配器 (ExceptionSql.xsd) 格式的 BizTalk 映射。 然后，组件将转换后的消息传递到 SQL 适配器，ESB 管理门户数据库中插入 ESB 错误消息。  
  
 ESB 转换管道组件公开三个设计时属性，可以修改以更改其运行时行为：  
  
- **已启用。** 此属性启用或禁用该组件。  
  
- **验证。** 此属性指定是否需要验证一条消息。  
  
- **映射名称。** 此属性包含必须在执行转换 ESB 管理门户数据库中存储的消息的映射的名称。 以下是默认值。  
  
  ```  
  Microsoft.Practices.ESB.ExceptionHandling.Maps.FaultMessage_to_ExceptionSql,  
  Microsoft.Practices.ESB.ExceptionHandling.Maps,  
  Version=2.0.0.0,  
  Culture=neutral,  
  PublicKeyToken=c2c8b2b87f54180a  
  ```  
  
  所有管道组件都完成执行后，BizTalk SQL Server 数据库适配器将错误消息插入到 ESB 管理门户数据库。