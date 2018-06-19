---
title: ImportBindings 命令 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b8dd1ee-1719-4cd1-b503-b004f312daeb
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 576f9055e7b70ab43cc150f208f8c55789f28da8
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
ms.locfileid: "22257997"
---
# <a name="importbindings-command"></a>ImportBindings 命令
用于将绑定从基于 XML 的绑定文件导入到 BizTalk 应用程序或组中。 绑定可能已导出从程序集，应用程序或组中, 所述[导出绑定](../core/exporting-bindings6.md)。 根据绑定的导出位置，ApplicationName 和 GroupLevel 参数具有不同的作用。 有关详细信息，请参阅本主题后面的“备注”。  
  
> [!NOTE]
>  绑定中生成文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]没有指定的应用程序。 它们被导入到默认的应用程序中。  
  
## <a name="usage"></a>用法  
 **BTSTask ImportBindings-源**:*值* [**-GroupLevel** & #124; **-ApplicationName**:*值*] [**-服务器**:*值*] [**-数据库**:*值*] [**-ImportTrackingSettings**:*值*] [**-ExcludeParties**]
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|“值”|  
|---------------|--------------|-----------|  
|**-源** (或 **-因此**, ，请参阅备注)|必需|要导入的绑定文件的完整路径，包含文件名。 包含空格的路径必须放在引号 (") 中。|  
|**-GroupLevel** (或 **-G**, ，请参阅备注)|可选|将绑定文件导入到当前组的选项。 如果指定此参数，则请不要指定 /ApplicationName。|  
|**-ApplicationName** (或 **-A**, ，请参阅备注)|可选|绑定要导入到的 BizTalk 应用程序的名称。 如果名称包含空格，则必须将它用双引号 （"）。 该应用程序必须存在，否则导入操作将失败。 如果未指定此参数，则使用默认 BizTalk 应用程序。 如果指定此参数，则请不要指定 /GroupLevel。|  
|**服务器** (或 **-Se**, ，请参阅备注)|可选|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**-数据库** (或 **-D**, ，请参阅备注)|可选|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
| **-ImportTrackingSettings** | 可选 | 新开头[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。 <br /><br />此设置将替代全局跟踪设置导入选项。 "True"值允许导入的跟踪设置。 False 会禁用跟踪设置导入。 |
| **-ExcludeParties** | 可选 | 新开头[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。 <br /><br />如果指定，将从绑定文件排除方信息。 |
  
## <a name="sample"></a>示例  
 以下命令将绑定导入到默认 BizTalk 组中名为 MyApplication 的应用程序中。  
  
`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml`
  
 以下命令将绑定导入到 BizTalk 管理数据库中所定义的组，该 BizTalk 管理数据库运行在名为 MY_Server 的 SQL Server 实例上。  
  
 `BTSTask ImportBindings -GroupLevel -Server:MY_Server -Database:BiztalkMgmtDb -Source:C:\Bindings\Binding1.xml`
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
 绑定可能已从程序集、应用程序或组中导出。 根据绑定的导出位置，ApplicationName 和 GroupLevel 参数具有不同的作用，如下表所示。  
  
|绑定源|ApplicationName 参数的作用|GroupLevel 参数的作用|  
|----------------------------|-----------------------------------------------|------------------------------------------|  
|从程序集导出的绑定|ApplicationName 中指定的应用程序必须包含与从中导出绑定文件的程序集同名的程序集。 否则，导入操作将失败。|当前组必须包含与从中导出绑定文件的程序集和应用程序同名的程序集和应用程序。 否则，导入操作将失败。|  
|从应用程序导出的绑定|从中导出绑定文件的应用程序必须与 ApplicationName 指定的应用程序同名。 否则，导入操作将失败。|从中导出绑定文件的应用程序必须与要将绑定导入的组中的应用程序同名。 否则，导入操作将失败。|  
|从组导出的绑定|从中导出绑定文件的组必须包含与 ApplicationName 指定的应用程序同名的应用程序。 否则，导入操作将失败。|绑定将导入对应的应用程序中。 换言之，从中导出绑定的组中的应用程序的绑定将导入到当前组中同名的应用程序内。|  
  
## <a name="see-also"></a>另请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [如何将绑定导入到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)   
 [如何将绑定导入 BizTalk 应用程序](../core/how-to-import-bindings-into-a-biztalk-application.md)