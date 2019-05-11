---
title: BatchTerminator 实用工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 771241fa-7df5-4882-8430-c2f36200cc9d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e64c14cc2c1ff7538f96275bb452f0ef643327c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358253"
---
# <a name="batchterminator-utility"></a>BatchTerminator 实用工具
BatchTerminator 实用工具，可终止所有的批处理业务流程用于批量处理 EDI 交换。 如果有大量的批处理业务流程实例运行，并且需要终止所有批处理，以便 BizTalk server 系统上执行维护，此实用工具将非常有用。  
  
 BatchTerminator 实用工具位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator 文件夹。 当您运行此实用工具以终止批处理业务流程实例时，该实用工具会将结果记录的 batchterminator.log 文件中\<*驱动器*\>: \Documents and 设置\\<*用户名*\>\Application Data 文件夹。  
  
> [!NOTE]
>  32 位系统才支持 BatchTerminator 实用工具。  BatchTerminator 使用 Microsoft.BizTalk.ExplorerOM 命名空间，它才支持使用从 32 位进程中的组件。  
  
 **重新启动终止的业务流程实例**  
  
 终止批处理业务流程的一组后，可以执行这些业务流程实例的批量重新启动。 请使用 /Activate 开关的名称和指示被停止批处理文件的路径。 当您运行该实用工具终止一组业务流程实例时，该实用程序将创建此停止批处理文件。 停止批处理文件为 batchSettings-\<GUID\>中的.xml \<*驱动器*\>: \Documents and 设置\\<*用户名* \>\Application data 文件夹。 路径和停止批处理文件的名称也保存在日志文件。 该实用工具使用的运行时 / 激活开关，它会验证根据架构对输入的文件。  
  
 **语法**  
  
 使用以下语法的命令行窗口中运行 BatchTerminator 实用工具：  
  
```  
BatchTerminator /<switch>  
```  
  
 可以使用以下开关运行 BatchTerminator 实用工具。 如果未不提供任何开关，终止 / 使用选项。 如下所示，您可以输入开关的完整名称，例如 / 终止，或使用缩写形式，在这种情况下，/t。  
  
|||  
|-|-|  
|开关|函数|  
|/?|显示帮助|  
|/ 终止-log:\<*日志文件*\><br /><br /> 或 /t-log:\<*日志文件*\>|发送终止控制消息向所有活动的 X12 或 EDIFACT 批处理业务流程实例。 它将显示该操作，包括它终止的所有活动批处理业务流程实例的列表、 活动批处理业务流程所找到的数量和它所发送的终止控制消息数的结果。 它将结果记录到的 batchterminator.log 文件中\<*驱动器*\>: \Documents and 设置\\<*用户名*\>\应用程序数据文件夹。<br /><br /> 选择的 – log： 参数使你可以指定日志文件的名称和/或你想要保存到的日志文件的文件夹的路径。 使用参数来指定的路径和文件名称的一个示例是以下： `BatchTerminator.exe /terminate -log:"C:\logs\log.txt"`。 使用参数来指定文件名称的示例只是以下： `BatchTerminator.exe /terminate -log:log.txt`。 如果指定的路径无效，该实用工具将使用默认路径： \<*驱动器*\>: \Documents and 设置\\<*用户名*\>\Application 数据。 -Log： 无论是否可以使用参数 /terminate 开关。|  
|/print<br /><br /> or /p|显示当前活动批处理业务流程实例的列表，不发送终止控制消息|  
|/activate:\<*path*\>\\<br />batchSettings-\<*GUID*\>.xml-log:\<*日志文件*\><br /><br /> 或 /a:\<*路径*\>\\<br />batchSettings-\<*GUID*\>.xml-log:\<*日志文件*\>|重新激活先前终止的业务流程实例中 batchSettings-列出\<GUID\>.xml 文件。 该实用程序将验证根据代码中嵌入的架构对输入的文件。 如果输入的文件与架构不匹配，将显示在屏幕上一条错误消息并退出程序。<br /><br /> 此操作将有关重新启动操作的信息写入日志文件中如果包含-log： 开关。|  
  
 **批处理激活文件的格式**  
  
 若要重新激活先前终止批处理业务流程实例使用 /activate 开关，必须提供批处理激活文件 (batchSettings-\<GUID\>.xml)。 此文件必须采用以下格式：  
  
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
 以下是执行本主题中的过程的先决条件：  
  
-   您必须以 BizTalk Server Administrators 组的成员身份登录。  
  
### <a name="to-run-the-batchterminator-utility"></a>若要运行 BatchTerminator 实用工具  
  
1. 在 Windows 资源管理器，转到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator 文件夹。  
  
2. Enter **BatchTerminator**，包括任何所需的开关，然后单击**Enter**。  
  
3. 在 Windows 资源管理器，转至\<*驱动器*\>: \Documents and 设置\\<*用户名*\>\Application Data 文件夹，并打开 batchterminator.log 文件以查看结果的日志。  
  
## <a name="see-also"></a>请参阅  
 [SDK 中的实用工具](../core/utilities-in-the-sdk.md)