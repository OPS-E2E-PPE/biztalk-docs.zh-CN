---
title: "BatchTerminator 实用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 771241fa-7df5-4882-8430-c2f36200cc9d
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64bfb6e708122623040e013d512580beaa37c050
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="batchterminator-utility"></a>BatchTerminator 实用工具
使用 BatchTerminator 实用工具，您可以终止所有正在运行的用于批量处理 EDI 交换的批处理业务流程。 如果您正在运行大量批处理业务流程实例，并且需要终止所有这些批处理，以便对 BizTalk Server 系统执行维护，此时本实用工具将非常有用。  
  
 BatchTerminator 实用工具位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator 文件夹中。 该实用工具运行实用程序来终止批处理的业务流程实例时，将 batchterminator.log 文件中记录结果\<*驱动器*>: \Documents and 设置\\<*用户名*> \Application 数据文件夹。  
  
> [!NOTE]
>  只有 32 位系统才支持 BatchTerminator 实用工具。  BatchTerminator 使用 Microsoft.BizTalk.ExplorerOM 命名空间中的组件，该组件仅在从 32 位进程中使用时才受到支持。  
  
 **重新启动终止的 Orchestration 实例**  
  
 终止一组批处理业务流程后，可以批量重新启动这些业务流程实例。 您需要使用 /Activate 开关和指示被停止批处理的文件的名称和路径执行此操作。 运行本实用工具终止一组业务流程实例时，它将创建此停止批处理文件。 停止批处理文件是 batchSettings-\<GUID > 中的.xml \<*驱动器*>: \Documents and 设置\\<*用户名*> \应用程序数据文件夹。 同时会将停止批处理文件的路径和名称保存在日志文件中。 使用 /activate 开关运行本实用工具时，它将根据架构对输入文件进行验证。  
  
 **语法**  
  
 使用以下语法，在命令行窗口中运行 BatchTerminator 实用工具：  
  
```  
BatchTerminator /<switch>  
```  
  
 在运行 BatchTerminator 实用工具时，可以使用以下开关。 如果未提供任何开关，则使用 /terminate 选项。 如下所示，您可以输入开关的完整名称，例如 /terminate，也可以使用缩写形式，在本例中，可使用 /t。  
  
|||  
|-|-|  
|开关|函数|  
|/?|显示帮助|  
|/ 终止的日志：\<*日志文件*><br /><br /> 或 /t-日志：\<*日志文件*>|向所有活动的 X12 或 EDIFACT 批处理业务流程实例发送终止控制消息。 该实用工具将显示操作的结果，包括它所终止的所有活动批处理业务流程实例的列表、它所找到的活动批处理业务流程数，以及它所发送的终止控制消息数。 它将结果记录到文件中，batchterminator.log \<*驱动器*>: \Documents and 设置\\<*用户名*> \Application 数据文件夹。<br /><br /> 可选的-日志： 参数使你可以指定日志文件的名称和/或你想要保存到的日志文件的文件夹的路径。 使用参数指定的路径和文件名称的一个示例是以下： `BatchTerminator.exe /terminate -log:"C:\logs\log.txt"`。 使用参数来指定文件名称的示例只是以下： `BatchTerminator.exe /terminate -log:log.txt`。 如果指定的路径无效，该实用工具将使用默认路径： \<*驱动器*>: \Documents and 设置\\<*用户名*> \Application 数据。 -日志： 可以使用参数，可以使用或不 / 终止交换机。|  
|/print<br /><br /> 或 /p|只显示当前活动批处理业务流程实例的列表，不发送终止控制消息|  
|/ 激活：\<*路径*>\\<br />batchSettings-\<*GUID*>.xml-日志：\<*日志文件*><br /><br /> 或 /a:\<*路径*>\\<br />batchSettings-\<*GUID*>.xml-日志：\<*日志文件*>|重新激活以前终止的业务流程实例中的 batchSettings-列出\<GUID >.xml 文件。 本实用工具将根据代码中嵌入的架构对输入文件进行验证。 如果输入的文件与架构不匹配，将在屏幕上显示错误消息，并退出程序。<br /><br /> 如果在命令中包含 -log: 开关，则此操作会将有关重新启动操作的信息写入日志文件。|  
  
 **批处理激活文件的格式**  
  
 若要重新激活以前通过使用终止 batch orchestration 实例 / 激活开关，你必须提供一个批处理激活文件 (batchSettings-\<GUID >.xml)。 此文件必须采用以下格式：  
  
```  
<?xml version="1.0"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" elementFormDefault="qualified" id="BatchInfo" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="BatchTerminator">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element minOccurs="1" maxOccurs="unbounded" name="Batch">  
          <xs:complexType>  
            <xs:attribute name="PartyName" type="xs:string" />  
            <xs:attribute name="PartyID" type="xs:int" use="required" />  
            <xs:attribute name=”BatchName” type=”xs:string” />  
            <xs:attribute name=”BatchID” type=”xs:int” use=”required” />  
            <xs:attribute name="EdiMessageType" type="xs:string" use="required" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="prerequisites"></a>先决条件  
 以下为执行本主题中步骤的前提条件：  
  
-   必须以 BizTalk Server Administrators 组成员的身份登录。  
  
### <a name="to-run-the-batchterminator-utility"></a>运行 BatchTerminator 实用工具  
  
1.  在 Windows 资源管理器中，转至 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator 文件夹。  
  
2.  Enter **BatchTerminator**，包括任何所需的开关，然后单击**Enter**。  
  
3.  在 Windows 资源管理器，移动到\<*驱动器*>: \Documents and 设置\\<*用户名*> \Application 数据文件夹，然后打开 batchterminator.log若要查看结果的日志的文件。  
  
## <a name="see-also"></a>另请参阅  
 [SDK 中的实用程序](../core/utilities-in-the-sdk.md)