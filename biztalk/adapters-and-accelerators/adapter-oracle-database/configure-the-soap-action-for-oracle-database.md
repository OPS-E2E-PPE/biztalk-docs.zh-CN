---
title: 在 BizTalk 中配置 Oracle 数据库的 SOAP 操作 |Microsoft Docs
description: 在 Visual Studio 中，输入 SOAP 操作或使用 BizTalk 适配器包 (BAP) 中的 WCF 自定义或 Wcf-oracledb 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0d21cca-3907-4f99-af76-c1e7286e1bcf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62bb4567a73411c28ba68010b7def22a121ddda2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377004"
---
# <a name="configure-the-soap-action-for-oracle-database"></a>配置 Oracle 数据库的 SOAP 操作
若要完成对使用基于 WCF 的 Oracle 数据库的任何操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，适配器的用户必须输入 SOAP 操作。 SOAP 操作与适配器通信应完成的操作。 您可以输入在设计时或在运行时的 SOAP 操作。 但是，如果输入的 SOAP 操作这两个在设计时和运行时，会覆盖在设计时输入的操作。  
  
 有关指定 SOAP 操作的详细信息，请参阅[对于 WCF 发送适配器指定 SOAP 操作](../../core/specifying-soap-actions-for-wcf-send-adapters.md)。  
  
## <a name="enter-soap-action-from-visual-studio"></a>从 Visual Studio 输入 SOAP 操作  
 从 Visual Studio 中，您必须指定 SOAP 操作作为业务流程的一部分通过使用**表达式**形状。  
  
1.  在 BizTalk 业务流程，包括**表达式**通过将其从拖动形状**BizTalk 业务流程**工具箱。  
  
2.  双击**表达式**形状以打开 BizTalk 表达式编辑器。  
  
3.  在 BizTalk 表达式编辑器中指定的操作。 例如：  
  
    ```
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
    ```  
  
     有关详细信息**表达式**形状和 BizTalk 表达式编辑器中，请参阅[如何创建表达式](../../core/how-to-create-expressions.md)。  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a>从 BizTalk Server 管理输入 SOAP 操作  
 从 BizTalk Server 管理控制台中，您必须指定 SOAP 操作作为 WCF 自定义或 Wcf-oracledb 端口配置的一部分。 

#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>输入 WCF 自定义端口的 SOAP 操作  
 
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用的程序**发送端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  
  
3. 在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
4. 在中**Wcf-custom 传输属性**对话框中，单击**常规**选项卡。  
  
5. 在中**操作**文字框中，指定该操作的 SOAP 操作。 您可以按以下方式指定的操作：  
  
   -   **通过使用单一操作格式**。 如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。 例如：  
  
       ```  
       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
       ```  
  
   -   **通过使用操作映射格式**。 如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。 例如，如果单个 WCF 自定义端口发送和接收消息 （若要在 EMP 表中插入记录） 的 Op1 和 Op2 （若要更新的 EMP 表中的记录），可以按以下方式指定的 SOAP 操作：  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
       </BtsActionMapping>  
       ```  
  
        这种方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过同一端口。  
  
        SOAP 操作的格式是不同的每个操作。 有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)。  
  
#### <a name="enter-a-soap-action-for-the-wcf-oracledb-port"></a>输入 Wcf-oracledb 端口的 SOAP 操作  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 将 Wcf-oracledb 适配器添加到 BizTalk Server 管理控制台。 有关说明，请参阅[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。  
  
3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用的程序**发送端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  
  
4. 在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加的 Wcf-oracledb 端口，然后单击**配置**。  
  
5. 在中**Wcf-custom 传输属性**对话框中，单击**常规**选项卡。  
  
6. 在中**操作**文字框中，指定该操作的 SOAP 操作。 您可以按以下方式指定的操作：  
  
   -   **通过使用单一操作格式**。 如果 Wcf-oracledb 端口发送和接收消息的单个操作，请使用此格式。 例如：  
  
       ```  
       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
       ```  
  
   -   **通过使用操作映射格式**。 如果单个 Wcf-oracledb 端口发送和接收消息的多个操作，请使用此格式。 例如，如果单个 Wcf-oracledb 端口发送和接收消息 （若要在 EMP 表中插入记录） 的 Op1 和 Op2 （若要更新的 EMP 表中的记录），可以按以下方式指定的 SOAP 操作：  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
       </BtsActionMapping>  
       ```  
  
        这种方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过同一端口。  
  
        SOAP 操作的格式是不同的每个操作。 有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)。
  
## <a name="see-also"></a>请参阅  
[若要开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)