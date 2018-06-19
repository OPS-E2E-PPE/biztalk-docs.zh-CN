---
title: 有关数据提供程序类型读取 SAP 连接字符串 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, connection string
- ADO, connection string
ms.assetid: 7a46eaae-604f-4bae-924b-9f6d43a6e8a0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e77219fb74b7af377953a3761c4d9f241b3a8bd0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963339"
---
# <a name="read-about-data-provider-types-for-the-sap-connection-string"></a>有关数据提供程序类型读取 SAP 连接字符串
若要建立到 SAP 系统的连接，ADO.NET 客户端必须在连接字符串的形式指定 SAP 连接属性。 SAP ADO 连接字符串的格式如下所示：  
  
```  
[Property1]=[Value1];[Property2]=[Value2];....  
```  
  
 要连接到 SAP 系统使用的连接字符串[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]可以具有以下类型：  
  
-   **答： 类型**在其中连接 URI 指定通过该应用程序服务器的应用程序基于主机的连接[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连接到 SAP 系统。  
  
-   **类型 b:** 连接 URI 在其中指定了消息和服务器之间的负载平衡的连接[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连接到 SAP 系统。  
  
-   **类型 d:** 在其中连接 URI 指定包含 SAP 系统的连接参数的 saprfc.ini 文件中的目标的基于目标的连接。  
  
 下表介绍如何在连接 URI 中指定这些连接。  
  
|TYPE|属性 1|属性 2|Description|  
|----------|----------------|----------------|-----------------|  
|仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，|ASHOST （应用程序服务器主机）|SYSNR （SAP 系统编号）|指定的应用程序基于主机的连接。|  
|B|MSHOST （消息服务器主机）|R3NAME （SAP R3 名称）|指定负载平衡通过消息服务器的连接。 对于负载平衡连接，可以指定可选的服务器组的步骤。|  
|D|目标 （包含 saprfc.ini 文件中的连接参数的目标）|-|指定基于目标的连接。 SAP 连接参数包含在 saprfc.ini 文件中指定的目标。 目标中，可以指定仅类型 A 和 B 类型的连接。 **注意：** 如果 saprfc.ini 文件中指定的连接值，请确保该文件位于作为访问文件中的.exe 或在所需的 SAP 系统的标准位置的相同文件夹中。 有关详细信息，请参阅 SAP 文档。|  
  
 基于类型的连接，连接字符串以连接到 SAP 系统使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]可以包含以下属性。  
  
|属性|用于类型|Description|  
|--------------|-------------------|-----------------|  
|应用程序服务器主机 (ASHOST)|仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，|SAP 应用程序服务器主机的名称。|  
|系统编号 (SYSNR)|仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，|SAP 系统编号|  
|应用程序服务器组名称 （组）|B|SAP 服务器组的名称。 这是在负载平衡连接的应用程序服务器的可选组。|  
|消息服务器主机 (MSHOST)|B|SAP 消息服务器主机的名称|  
|消息服务器服务 (MSSERV)|B|名称中指定的 SAP 消息服务器服务的\<系统驱动器\>: \WINDOWS\system32\drivers\etc\services 文件。 如果不指定一个值，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]假定此项为"任意\</ 3 系统名称\>"。 例如，如果 / 3 系统名称是 DV1，则适配器会假定要"sapmsDV1"的消息服务器服务名称。<br /><br /> 但是，如果服务文件中的项不同，你必须指定该值。|  
|/ 3 系统名称 (R3NAME)|B|SAP / 3 名称中。|  
|目标 （目标）|D|从 saprfc.ini 文件中选取的连接参数。|  
|客户端 （客户端）|A、 B、 D|SAP 客户端数|  
|语言 (Lang)|A、 B、 D|语言|  
|密码 （密码）|A、 B、 D|SAP 用户密码|  
|用户名 （用户）|A、 B、 D|要连接到 SAP 系统的用户名|  
|启用调试 (AbapDebug) 的 SAP GUI|A、 B、 D|可选参数，用于指定是否从调试的 ABAP[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]启用和适配器是否使用 SAP GUI 进行调试。 该值可以为 True 或 False;如果为 True，则启用 ABAP 调试，并且打开 SAP GUI。 默认值为 False。|  
|跟踪 RFC SDK(RfcSdkTrace)|A、 B、 D|指定是否启用 RFC 库跟踪的可选参数。 该值可以为 True 或 False;如果为 True，则启用 RFC 库跟踪。 默认值为 False。|  
  
> [!NOTE]
>  在属性列中的括号内提供的值是必须同时提供通过编程解决方案连接 URI 指定的连接属性的名称。 但是，如果你使用 DDEX 插件或 SQL Server 导入和导出向导使用 ADO 接口，作为友好名称列出的连接属性。  
  
## <a name="example-connection-string-for-type-a"></a>类型的示例连接字符串 A  
 键入一个示例连接字符串将如下所示：  
  
```  
TYPE=A; ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  
  
> [!NOTE]
>  默认情况下[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]始终会将连接字符串的键入 a.  
  
## <a name="example-connection-string-for-type-b"></a>为类型 B 的示例连接字符串  
 类型 B 的一个示例连接字符串将如下所示：  
  
```  
TYPE=B; R3NAME=NAME1; GROUP=ADAPTER; MSHOST=MSSERVER; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  
  
## <a name="example-connection-string-for-type-d"></a>类型 D 的示例连接字符串  
 类型 D 一个示例连接字符串将如下所示：  
  
```  
TYPE=D; DEST=TESTSAPSRV; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  
  
 示例 saprfc.ini 文件类似于：  
  
```  
DEST=TESTSAPSRV  
TYPE=A  
ASHOST=ADAPSAP47  
SYSNR=00  
```  
  
 Saprfc.ini 文件有关的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=91457](http://go.microsoft.com/fwlink/?LinkId=91457)。  
  
 所有三种连接类型的密码不能包含两个双引号。 但是，如果密码包含任何其他特殊字符，密码必须括在双引号内。 例如：  
  
```  
ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=",@/:;_ \\";  
```  
  
> [!IMPORTANT]
>  你必须为只能有一个连接类型 A、 B 或 d。 指定的连接参数例如，如果连接字符串中指定应用程序服务器主机，你必须指定消息服务器主机名或 R3NAME。  
  
## <a name="see-also"></a>另请参阅  
 [使用 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)