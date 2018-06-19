---
title: 在 BizTalk 中配置用于 Siebel 适配器的 SOAP 操作 |Microsoft 文档
description: 在 Visual Studio 中，输入 SOAP 操作或使用 BizTalk 适配器包 (BAP) 中的 WCF 自定义或 WCF Siebel 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f22a4691-0355-4f08-a14e-e90a3c987ac0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b851aa0b26d80a43f5a839232298ace5507f471b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222557"
---
# <a name="configure-the-soap-action-for-siebel"></a>配置用于 Siebel 的 SOAP 操作
若要对使用基于 WCF 的 Siebel 系统执行任何操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，适配器用户必须指定 SOAP 操作。 SOAP 操作进行通信的适配器应执行什么操作。 你可以指定在设计时或在运行时的 SOAP 操作。 但是，如果你指定的 SOAP 操作这两个在设计时和运行时，将替代在设计时指定的操作。  
  
 有关指定 SOAP 操作的详细信息，请参阅[指定 WCF 发送适配器的 SOAP 操作](../../core/specifying-soap-actions-for-wcf-send-adapters.md)。
  
## <a name="enter-soap-action-at-design-time"></a>输入在设计时的 SOAP 操作  
 为设计时，你必须指定的 SOAP 操作的业务流程的一部分包括表达式形状。  
  
1.  在 BizTalk 业务流程是表达式形状包含通过拖动从**BizTalk 业务流程**工具箱。  
  
2.  双击**表达式**形状以打开 BizTalk 表达式编辑器。  
  
3.  在 BizTalk 表达式编辑器中指定的操作。 例如：  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"  
    ```  
  
     有关详细信息**表达式**形状和 BizTalk 表达式编辑器，请参阅[如何创建表达式](../../core/how-to-create-expressions.md)。  
  
## <a name="enter-soap-action-at-run-time"></a>在运行时输入 SOAP 操作  
 运行时，你必须作为 WCF 自定义或 WCF Siebel 端口属性对话框中的一部分来指定的 SOAP 操作。  
  
#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>输入 WCF 自定义端口的 SOAP 操作  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
3.  在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
4.  在**WCF 自定义传输属性**对话框中，单击**常规**选项卡。  
  
5.  在**操作**文本框中，指定该操作的 SOAP 操作。 你可以通过以下方式指定的操作：  
  
    -   **通过单个操作格式**。 如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。 例如：  
  
        ```  
        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
        ```  
  
    -   **通过使用操作映射格式**。 如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。 例如，如果单个 WCF 自定义端口发送和接收 Op1 （即执行插入操作帐户在业务组件上的） 和 Op2 （即执行更新操作帐户在业务组件上的） 的消息，SOAP 操作可以指定以下方式：  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
        </BtsActionMapping>  
        ```  
  
         此方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过相同端口。  
  
         SOAP 操作的格式为每个操作不同。 有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)。
  
#### <a name="enter-a-soap-action-for-the-wcf-siebel-port"></a>输入 WCF Siebel 端口的 SOAP 操作  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  添加到在 WCF Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。  
  
3.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
4.  在端口属性对话框中，从**类型**下拉列表中，选择 WCF Siebel 适配器更早版本，添加，然后单击**配置**。  
  
5.  在端口属性对话框中，单击**常规**选项卡。  
  
6.  在**操作**文本框中，指定该操作的 SOAP 操作。 你可以通过以下方式指定的操作：  
  
    -   **通过单个操作格式**。 如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。 例如：  
  
        ```  
        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
        ```  
  
    -   **通过使用操作映射格式**。 如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。 例如，如果单个 WCF 自定义端口发送和接收 Op1 （即执行插入操作帐户在业务组件上的） 和 Op2 （即执行更新操作帐户在业务组件上的） 的消息，SOAP 操作可以指定以下方式：  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
        </BtsActionMapping>  
        ```  
  
         此方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过相同端口。  
  
         SOAP 操作的格式为每个操作不同。 有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)。
  
## <a name="see-also"></a>另请参阅  
[构建基块创建带有 Siebel 适配器 BizTalk 应用程序](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)