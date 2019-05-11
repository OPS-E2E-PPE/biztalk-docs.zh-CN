---
title: 在 BizTalk 中配置 SQL 适配器的 SOAP 操作 |Microsoft Docs
description: 在 Visual Studio 中，输入 SOAP 操作或使用 BizTalk 适配器包 (BAP) 中的 WCF 自定义或 WCF SQL 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acd7f60b-c27f-4988-a67c-e56ef8d38f66
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be22ac1f6e0ebc31b3b2573ce6df0bba84f352b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369962"
---
# <a name="configure-the-soap-action-for-the-sql-adapter"></a>配置 SQL 适配器的 SOAP 操作
若要执行任何操作使用基于 WCF 的 SQL Server 上[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，你必须指定 SOAP 操作。 SOAP 操作通信适配器应执行什么操作。 可以从指定的 SOAP 操作[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 但是，如果指定的 SOAP 操作从这两个位置，指定的操作，从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]将被重写。  
  
 有关指定 SOAP 操作的详细信息，请参阅[对于 WCF 发送适配器指定 SOAP 操作](../../core/specifying-soap-actions-for-wcf-send-adapters.md)。
  
## <a name="enter-the-soap-action-in-visual-studio"></a>在 Visual Studio 中输入的 SOAP 操作  
 从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须使用作为业务流程的一部分指定的 SOAP 操作**表达式**形状。  
  
1.  在 BizTalk 业务流程，包括**表达式**通过将其从拖动形状**BizTalk 业务流程**工具箱。  
  
2.  双击**表达式**形状以打开 BizTalk 表达式编辑器。  
  
3.  在 BizTalk 表达式编辑器中指定的操作。 例如：  
  
    ```  
    OutboundMessage(WCF.Action)="TableOp/Insert/dbo/Employee"  
    ```  
  
     有关详细信息**表达式**形状和 BizTalk 表达式编辑器，请参阅[如何创建表达式](../../core/how-to-create-expressions.md)。
  
## <a name="enter-the-soap-action-from-the-biztalk-server-administration-console"></a>从 BizTalk Server 管理控制台输入 SOAP 操作  
 从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您可以指定 SOAP 操作作为 WCF 自定义或 WCF SQL 端口配置的一部分。  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>输入 WCF 自定义端口的 SOAP 操作  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  
  
3. 在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
4. 在中**Wcf-custom 传输属性**对话框中，单击**常规**选项卡。  
  
5. 在中**操作**文字框中，指定该操作的 SOAP 操作。 您可以按以下方式指定的操作：  
  
   -   **通过使用单一操作格式**。 如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。 例如：  
  
       ```  
       TableOp/Insert/dbo/Employee  
       ```  
  
   -   **通过使用操作映射格式**。 如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。 例如，如果单个 WCF 自定义端口发送和接收消息 （若要在 Employee 表中插入记录） 的 Op1 和 Op2 （若要更新的 Employee 表中的记录），可以按以下方式指定的 SOAP 操作：  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="TableOp/Insert/dbo/Employee" />  
         <Operation Name="Op2" Action="TableOp/Update/dbo/Employee" />  
       </BtsActionMapping>  
       ```  
  
        操作映射方法提供了更加灵活的指定一组操作，并因此启用属于不同的操作类型都通过相同端口的消息。  
  
        SOAP 操作的格式是不同的每个操作。 有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)。
  
### <a name="enter-a-soap-action-for-the-wcf-sql-port"></a>输入 WCF SQL 端口的 SOAP 操作  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。  
  
3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  
  
4. 在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加 WCF SQL 适配器，然后单击**配置**。  
  
5. 在传输属性对话框中，单击**常规**选项卡。  
  
6. 在中**操作**文字框中，指定该操作的 SOAP 操作。 您可以按以下方式指定的操作：  
  
   -   **通过使用单一操作格式**。 如果 WCF SQL 端口发送和接收消息的单个操作，请使用此格式。 例如：  
  
       ```  
       TableOp/Insert/dbo/Employee  
       ```  
  
   -   **通过使用操作映射格式**。 如果单个 WCF SQL 端口发送和接收消息的多个操作，请使用此格式。 例如，如果单个 WCF SQL 端口发送和接收消息 （若要在 Employee 表中插入记录） 的 Op1 和 Op2 （若要更新的 Employee 表中的记录），可以按以下方式指定的 SOAP 操作：  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="TableOp/Insert/dbo/Employee" />  
         <Operation Name="Op2" Action="TableOp/Update/dbo/Employee" />  
       </BtsActionMapping>  
       ```  
  
        操作映射方法提供了更加灵活的指定一组操作，并因此启用属于不同的操作类型都通过相同端口的消息。  
  
        SOAP 操作的格式是不同的每个操作。 有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)。
  
## <a name="see-also"></a>请参阅  
[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)