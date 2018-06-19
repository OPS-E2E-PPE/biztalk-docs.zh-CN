---
title: 消息扩充教程 |Microsoft 文档
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
ms.openlocfilehash: 532fc0e8a9aeefbc35a892277c68be8d640b5588
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205229"
---
# <a name="message-enrichment-tutorial"></a>消息扩充教程
本教程提供了分步过程使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]以解决特定业务问题： 消息扩充问题。 消息扩充教程介绍你需要在其中将添加到，或使更为丰富的情况下，一条消息，不符合 HL7 和/或不完整。 这可能会出现应用程序，如患者注册应用程序，或当您在安装的 XML 数据从一条消息，它就可以会发生[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]。  
  
 在本教程中，可以捕获 BTAHL7，使用的消息和提供任何缺少的数据，例如，从患者记录数据库。 然后将消息转换并将其发送到实验室、 保险或任何旧的业务线 (LOB) 应用程序使用 MLLP （最小较低层协议） 适配器。  
  
 在本教程中，你使用 Web 服务客户端 (WSClient.exe) 应用程序发送 XML 格式的消息，在此情况下的"门铃"注册耐心等待触发器事件，通过 SOAP 适配器到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]与 BTAHL7。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]在 SOAP 接收的消息接收端口和作为 Web 服务发布到 orchestration 消息的路由。 该 XML 消息包含患者的名称和身份证号。 你增加消息，并使用架构、 映射和转换来将消息转换为 HL7 格式。 然后，你将向实验室，insurance 通过 MLLP 适配器发送它或 LOB 应用程序。  
  
 下图显示了本教程的处理流程。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-msgenrichtutarch.gif "hl7_msgenrichtutarch")  
  
> [!NOTE]
>  本教程需要安装 Windows Server Standard、 Enterprise、 Datacenter、 或 Web Edition 和自定义的 BTAHL7 安装包含 MLLP 测试工具。 此外，你应熟悉[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]中的开发[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]中找到的信息和[了解 HL7 快捷键和提供的 BizTalk 工具](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)。  
  
> [!NOTE]
>  你可以避免的正在取消部署的程序集，停止发送端口的错误，禁用接收你在前面的教程中使用的位置。  
  
## <a name="in-this-section"></a>在本节中  
  
-   [步骤 1： 配置应用程序池标识](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-application-pool-identity.md)  
  
-   [步骤 2： 创建新项目](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)  
  
-   [步骤 3： 向程序集分配强名称](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)  
  
-   [步骤 4： 创建架构](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)  
  
-   [步骤 5： 升级架构中的属性](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)  
  
-   [步骤 6： 验证架构](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)  
  
-   [步骤 7： 登录和生成项目](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md)  
  
-   [步骤 8： 创建 BizTalk 映射程序的映射](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)  
  
-   [步骤 9： 验证并生成映射项目](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)  
  
-   [步骤 10： 创建业务流程](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)  
  
-   [步骤 11： 创建业务流程变量](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)  
  
-   [步骤 12： 配置业务流程形状](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)  
  
-   [步骤 13： 创建并配置端口](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)  
  
-   [步骤 14： 发布作为 Web 服务业务流程](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)  
  
-   [步骤 15： 配置发送和接收端口](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)  
  
-   [步骤 16： 启动业务流程](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)  
  
-   [步骤 17： 创建 WSClient 应用程序](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)  
  
-   [步骤 18： 测试您的新消息扩充解决方案](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)