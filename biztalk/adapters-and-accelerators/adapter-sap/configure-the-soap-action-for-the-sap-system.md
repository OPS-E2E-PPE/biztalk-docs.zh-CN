---
title: 在 BizTalk 中配置 SAP 系统的 SOAP 操作 |Microsoft Docs
description: 在表达式形状中，输入 SOAP 操作或使用 BizTalk 适配器包 (BAP) 中的 WCF 自定义或 WCF SAP 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76084bc5-7a10-4c4c-be22-bee83779a011
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 963c4b3c8d8287b430774813487e924837880a01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004870"
---
# <a name="configure-the-soap-action-for-the-sap-system"></a>配置用于 SAP 系统的 SOAP 操作
若要对使用基于 WCF 的 SAP 系统执行任何操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，适配器的用户必须指定 SOAP 操作。 SOAP 操作通信适配器应执行什么操作。 可以指定在设计时或在运行时的 SOAP 操作。 但是，如果指定的 SOAP 操作这两个在设计时和运行时，将替代在设计时指定的操作。  
  
 有关指定 SOAP 操作的详细信息，请参阅[对于 WCF 发送适配器指定 SOAP 操作](../../core/specifying-soap-actions-for-wcf-send-adapters.md)。
  
## <a name="enter-soap-action-at-design-time"></a>输入在设计时的 SOAP 操作  
 为设计时，你必须指定 SOAP 操作作为业务流程的一部分包括的表达式形状。  
  
 
1.  在 BizTalk 业务流程，包括的表达式形状将其从拖**BizTalk 业务流程**工具箱。  
  
2.  双击**表达式**形状以打开 BizTalk 表达式编辑器。  
  
3.  在 BizTalk 表达式编辑器中指定的操作。 例如：  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET"  
    ```  
  
     有关详细信息**表达式**形状和 BizTalk 表达式编辑器中，请参阅[如何创建表达式](../../core/how-to-create-expressions.md)。
  
## <a name="enter-soap-action-at-run-time"></a>输入在运行时的 SOAP 操作  
 对于运行时，可以为 WCF 自定义或 WCF SAP 端口配置的一部分来指定 SOAP 操作。  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>输入 WCF 自定义端口的 SOAP 操作  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  
  
3. 在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
4. 在中**Wcf-custom 传输属性**对话框中，单击**常规**选项卡。  
  
5. 在中**操作**文字框中，指定该操作的 SOAP 操作。 您可以按以下方式指定的操作：  
  
   -   **通过使用单一操作格式**。 如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。 例如：  
  
       ```  
       http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
       ```  
  
   -   **通过使用操作映射格式**。 如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。 例如，如果单个 WCF 自定义端口发送和接收 （若要调用 RFC_CUSTOMER_GET RFC） 的 Op1 和 Op2 （若要调用 BAPI_SALESORDER_CREATEFROMDAT2 BAPI） 的消息，可以按以下方式指定的 SOAP 操作：  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
       </BtsActionMapping>  
       ```  
  
        这种方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过同一端口。  
  
        SOAP 操作的格式是不同的每个操作。 有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。
  
### <a name="enter-a-soap-action-for-the-wcf-sap-port"></a>输入 WCF SAP 端口的 SOAP 操作  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。  
  
3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  
  
4. 在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加的 WCF-SAP 适配器，然后单击**配置**。  
  
5. 在传输属性对话框中，单击**常规**选项卡。  
  
6. 在中**操作**文字框中，指定该操作的 SOAP 操作。 您可以按以下方式指定的操作：  
  
   -   **通过使用单一操作格式**。 如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。 例如：  
  
       ```  
       http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
       ```  
  
   -   **通过使用操作映射格式**。 如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。 例如，如果单个 WCF 自定义端口发送和接收 （若要调用 RFC_CUSTOMER_GET RFC） 的 Op1 和 Op2 （若要调用 BAPI_SALESORDER_CREATEFROMDAT2 BAPI） 的消息，可以按以下方式指定的 SOAP 操作：  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
       </BtsActionMapping>  
       ```  
  
        这种方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过同一端口。  
  
        SOAP 操作的格式是不同的每个操作。 有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。
  
## <a name="see-also"></a>请参阅  
[生成块以创建 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)