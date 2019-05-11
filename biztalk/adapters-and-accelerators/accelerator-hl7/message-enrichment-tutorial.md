---
title: 消息充实教程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial
- message enrichment tutorial, about the tutorial
- messages, tutorial
- tutorials, message enrichment tutorial
ms.assetid: 4ffb047f-457a-4a80-b7ec-4b61ae16f35f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2760cfa52fc7e761829d3005bfecbb8bb40a728
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303691"
---
# <a name="message-enrichment-tutorial"></a>消息充实教程
本教程提供了分步过程使用 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]解决特定业务问题： 消息充实问题。 消息充实教程介绍了需要添加或丰富的情况下，一条消息，不符合 HL7 和/或不完整。 这可能会出现应用程序，如患者注册应用程序，或您在安装消息与来自 Microsoft 的 XML 数据时可能发生[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]。  
  
 在本教程中，将捕获与 BTAHL7，消息和提供任何缺失的数据，例如，从患者记录数据库。 然后将消息转换，并将其发送到实验室、 保險、 或任何旧的业务线 (LOB) 应用程序使用 （最少的较低层协议） 处的 MLLP 适配器。  
  
 在本教程中，您使用 Web 服务客户端 (WSClient.exe) 应用程序发送 XML 格式的消息，在此情况下"门铃"注册患者触发器事件，通过 SOAP 适配器到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BTAHL7 使用。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 接收的消息中 SOAP 接收端口和消息与业务流程发布为 Web 服务的路由。 XML 消息包含患者的名称和社会安全号码。 增加消息，并使用架构、 映射和转换该消息转换为 HL7 格式。 然后会将其通过 MLLP 适配器发送到实验室，保险，，或 LOB 应用程序。  
  
 下图显示了本教程的处理流程。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-msgenrichtutarch.gif "hl7_msgenrichtutarch")  
  
> [!NOTE]
>  本教程需要安装 Windows Server Standard、 Enterprise、 Datacenter、 或 Web Edition 和自定义的 BTAHL7 安装包含 MLLP 的测试工具。 此外，您应熟悉[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]中的开发[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]和中找到的信息[了解 HL7 加速器及可用的 BizTalk 工具](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)。  
> 
> [!NOTE]
>  则可以避免由正在取消部署程序集，停止发送端口的错误和禁用接收位置在前面的教程中使用。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：配置应用程序池标识](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-application-pool-identity.md)  
  
-   [步骤 2：创建一个新项目](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)  
  
-   [步骤 3：为程序集分配强名称](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)  
  
-   [步骤 4：创建架构](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)  
  
-   [步骤 5：提升架构属性](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)  
  
-   [步骤 6：验证架构](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)  
  
-   [步骤 7：登录和生成项目](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md)  
  
-   [步骤 8：使用 BizTalk 映射器创建映射](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)  
  
-   [步骤 9：验证和生成映射项目](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)  
  
-   [步骤 10：创建业务流程](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)  
  
-   [步骤 11:创建业务流程变量](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)  
  
-   [步骤 12：配置业务流程形状](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)  
  
-   [步骤 13：创建和配置端口](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)  
  
-   [步骤 14：将业务流程作为 Web 服务发布](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)  
  
-   [步骤 15：配置发送端口和接收端口](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)  
  
-   [步骤 16：启动业务流程](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)  
  
-   [步骤 17：创建 WSClient 应用程序](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)  
  
-   [步骤 18：测试新消息充实解决方案](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)